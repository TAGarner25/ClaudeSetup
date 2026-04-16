---
title: Desktop notification when Claude needs input
description: Notification hook that pops a native desktop alert when Claude is waiting on you.
created: 2026-04-16
updated: 2026-04-16
topics: [hooks, notification, desktop, quality-of-life]
---

# Desktop notifications

Claude Code fires a `Notification` event whenever it's waiting for you — permission prompts, elicitation dialogs, idle prompts. Hook into it to get a native desktop alert so you can switch tasks without watching the terminal.

## Windows (PowerShell)

Add to `~/.claude/settings.json`:

```json
{
  "hooks": {
    "Notification": [
      {
        "matcher": "",
        "hooks": [
          {
            "type": "command",
            "command": "powershell.exe -Command \"[System.Reflection.Assembly]::LoadWithPartialName('System.Windows.Forms'); [System.Windows.Forms.MessageBox]::Show('Claude Code needs your attention', 'Claude Code')\""
          }
        ]
      }
    ]
  }
}
```

For a less intrusive toast instead of a modal box, install [BurntToast](https://github.com/Windos/BurntToast) and use:

```json
"command": "powershell.exe -Command \"Import-Module BurntToast; New-BurntToastNotification -Text 'Claude Code', 'Needs your attention'\""
```

## macOS

```json
{
  "hooks": {
    "Notification": [
      {
        "matcher": "",
        "hooks": [
          {
            "type": "command",
            "command": "osascript -e 'display notification \"Claude Code needs your attention\" with title \"Claude Code\"'"
          }
        ]
      }
    ]
  }
}
```

If nothing appears, grant Script Editor notification permission — run `osascript -e 'display notification \"test\"'` once, then enable notifications for **Script Editor** in System Settings → Notifications.

## Linux

```json
{
  "hooks": {
    "Notification": [
      {
        "matcher": "",
        "hooks": [
          {
            "type": "command",
            "command": "notify-send 'Claude Code' 'Claude Code needs your attention'"
          }
        ]
      }
    ]
  }
}
```

## Filtering by notification type

The `Notification` matcher accepts the notification type:

- `permission_prompt` — permission dialog
- `idle_prompt` — Claude has been idle
- `auth_success` — login completed
- `elicitation_dialog` — MCP server asked for input

Only alert on permission prompts:

```json
{ "matcher": "permission_prompt", "hooks": [ ... ] }
```

## Push to phone / Slack instead

The hook can call any CLI. A few common targets:

- **ntfy**: `curl -d 'Claude needs you' ntfy.sh/your-topic`
- **Pushover**: `curl -s -F token=... -F user=... -F message='Claude needs you' https://api.pushover.net/1/messages.json`
- **Slack webhook**: `curl -X POST -d '{"text":"Claude needs you"}' $SLACK_WEBHOOK`

Remember to put secrets in env vars and, for HTTP hooks, list them in `allowedEnvVars`.
