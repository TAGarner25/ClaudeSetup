---
title: Require tests to pass before Claude stops
description: Stop hook using an agent-based evaluator to verify the test suite before ending a turn.
created: 2026-04-16
updated: 2026-04-16
topics: [hooks, stop, agent-hook, testing]
---

# Require tests to pass before stopping

`Stop` hooks fire when Claude is about to end a turn. Block the stop, and Claude keeps working — using your `reason` as the next instruction. Useful for "always run the test suite before saying you're done."

Two ways to implement: a fast `prompt` hook (LLM-only, judgment-based) or an `agent` hook (LLM with tool access, can actually run the tests).

## Agent hook (recommended)

An agent hook spawns a subagent with tool access. It can run `npm test`, inspect failures, and return a structured verdict. Default timeout 60s — bump it for longer suites.

```json
{
  "hooks": {
    "Stop": [
      {
        "hooks": [
          {
            "type": "agent",
            "prompt": "Verify that all unit tests pass. Run `npm test` (or the project's test command from package.json) and report whether every test passed. Respond with {\"ok\": true} if all green, or {\"ok\": false, \"reason\": \"<what failed>\"} otherwise. $ARGUMENTS",
            "timeout": 300
          }
        ]
      }
    ]
  }
}
```

When the agent returns `{"ok": false, "reason": "..."}`, Claude resumes with the reason as its next instruction and won't stop until tests pass.

## Prompt hook (lighter)

For checks that don't need tool access — e.g. "did you actually address every TODO in the user's last message?" — use a prompt hook:

```json
{
  "hooks": {
    "Stop": [
      {
        "hooks": [
          {
            "type": "prompt",
            "prompt": "Review the transcript. If any task the user requested is not yet complete, respond with {\"ok\": false, \"reason\": \"<what remains>\"}. Otherwise {\"ok\": true}."
          }
        ]
      }
    ]
  }
}
```

## Command hook (manual)

If you prefer full control, use a command hook. Critical: check `stop_hook_active` and exit `0` when it's `true`, or you'll loop forever.

```bash
#!/bin/bash
# .claude/hooks/require-tests.sh
INPUT=$(cat)

# If we've already forced a continuation, let Claude stop.
if [ "$(echo "$INPUT" | jq -r '.stop_hook_active')" = "true" ]; then
  exit 0
fi

if ! npm test --silent > /tmp/claude-test.log 2>&1; then
  echo "Tests failed. See /tmp/claude-test.log. Fix and re-run before stopping." >&2
  exit 2
fi

exit 0
```

```json
{
  "hooks": {
    "Stop": [
      {
        "hooks": [
          {
            "type": "command",
            "command": "\"$CLAUDE_PROJECT_DIR\"/.claude/hooks/require-tests.sh",
            "timeout": 300
          }
        ]
      }
    ]
  }
}
```

## When not to use this

- `Stop` fires on **every** turn end, not only at "task completion." If you just want Claude to pause for a question, this hook will force it to keep running.
- `Stop` does not fire when the user interrupts (`Esc`). API errors fire `StopFailure` instead.
- Long-running test suites will eat into the hook timeout — cap with `timeout`.
- Don't combine multiple `Stop` hooks that can each force continuation; the most restrictive wins and you'll be harder to debug.
