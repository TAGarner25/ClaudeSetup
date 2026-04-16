---
title: Enterprise Wiki Rollout Plan
description: Plan to turn this repo into a polished, private, auto-deploying wiki for non-technical employees using enterprise Claude licenses.
created: 2026-04-16
updated: 2026-04-16
topics: [wiki, mkdocs, azure, entra-id, rollout]
---

# Enterprise Wiki Rollout Plan

## Context

This repo is a 285-file markdown knowledge base rolling out alongside enterprise Claude licenses. The intended audience is **non-technical business users** who won't be comfortable navigating GitHub. The goal is a polished, themed, searchable wiki hosted at a clean URL, auto-deployed on `git push`, and gated to employees — **without** forcing content into SharePoint and **without** breaking the Obsidian vault workflow.

The content is ideal for a static-site generator: pure markdown with YAML frontmatter on every file, only 2 binary assets, only 47 `[[wikilinks]]` in 14 files. No build system exists yet, so this is greenfield.

## Recommended Approach

**MkDocs Material** (generator) → **GitHub Actions** (CI build) → **Azure Static Web Apps, Standard tier ~$9/mo** (hosting) → **Entra ID single-tenant app** (SSO with employees' M365 accounts).

Why this stack:

- **Markdown-native and git-native** — Obsidian continues to work untouched; edits still happen in `.md` files.
- **Polish out of the box** — Material has a mature theme system (brand colors, logo, fonts, dark mode, full-text search, mobile nav) configured via `mkdocs.yml` + an `overrides/` directory.
- **Auto-deploy** — push to `main`, GitHub Actions runs `mkdocs build --strict`, Azure SWA deploy action ships the `site/` artifact. ~60–90s build.
- **Employees-only auth without SharePoint** — Azure SWA Standard supports custom OIDC providers; an Entra app registration in the company tenant set to "single tenant" automatically rejects non-employees at login.
- **Preserves folder structure** — the `mkdocs-awesome-pages-plugin` lets us display clean sidebar titles ("Skills", "Prompts") while the on-disk folders stay `5 - Skills/`, `4 - Prompts/`, etc. No renames, Obsidian stays happy.
- **Handles wikilinks** — `mkdocs-roamlinks-plugin` resolves `[[filename]]` at build time with zero authoring changes.

One design decision worth flagging: use a **custom Entra OIDC provider** in `staticwebapp.config.json` rather than the built-in `aad` provider. The built-in one is multi-tenant and would let any Microsoft account in; single-tenant requires a custom provider pointed at your tenant's OIDC metadata.

### Alternatives Considered

| Option | Verdict |
|---|---|
| **Docusaurus** | Better if you need React/versioned docs. Worse here — JSX in markdown breaks Obsidian. |
| **Starlight (Astro)** | Beautiful and modern, but weaker plugin ecosystem for wiki-style features (no roamlinks equivalent). |
| **GitBook** | Polished UX and built-in auth, but pulls authoring *out* of markdown/Git into their editor. Kills the Obsidian workflow. $8/user/month. |
| **Obsidian Publish** | One-click, preserves Obsidian semantics perfectly. **But no SSO** — only password gating. Disqualified by the employees-only requirement. |
| **Public GitHub Pages first, auth later** | Tempting but means a mid-rollout migration and exposes content to Google indexing. Skip. |
| **Wiki.js / Outline / BookStack self-hosted** | Database-backed, not git-backed. Kills Obsidian sync and adds ops overhead. |

**MkDocs Material wins** because it's markdown-native, git-native, has the exact plugin ecosystem this repo needs, and Azure SWA gives free-tier auth that most alternatives match only at higher cost.

## Files to Create

| File | Purpose |
|---|---|
| `mkdocs.yml` | Site config: theme, palette, plugins (`search`, `awesome-pages`, `roamlinks`, `glightbox`, `git-revision-date-localized`, `redirects`, `tags`), markdown extensions, `docs_dir: .`, `use_directory_urls: true`, `strict: true`, excludes for `.claude/`, `Todo/`, `XX_ZipFolders/`, `.github/`. |
| `requirements.txt` | Pinned Python deps so CI builds are reproducible. |
| `.github/workflows/deploy.yml` | Push-to-`main` → Python setup → `pip install` → `mkdocs build --strict` → `Azure/static-web-apps-deploy@v1`. PR trigger runs build only (no deploy). Needs `fetch-depth: 0` for the git-date plugin. |
| `staticwebapp.config.json` | Defines the custom Entra OIDC provider, routes `/*` to role `authenticated`, rewrites 401 → `/.auth/login/entraID`. Copied into `site/` during build. |
| `index.md` | New homepage with `template: home.html` frontmatter. Replaces README-style TOC with a hero + search bar + 8-card grid + "Start Here" curated list. README.md stays as-is for GitHub repo visitors. |
| `overrides/home.html` | Custom homepage template (hero, search partial, CSS Grid of cards). |
| `overrides/main.html` | Extends base to add Azure SWA logout link and optional launch announcement bar. |
| `overrides/assets/stylesheets/brand.css` | Overrides Material CSS variables for brand palette, fonts, and card styles. Pull palette from `5 - Skills/22_EricksonGroup_BrandGuidelines/`. |
| `overrides/assets/images/logo.svg`, `favicon.png` | Brand assets. |
| `.pages` (one per top-level folder) | `awesome-pages` plugin file defining clean sidebar titles (e.g. `title: Skills` on `5 - Skills/.pages`) and hide rules. **This is the key trick that avoids renaming folders.** |

### Required Plugins (requirements.txt)

- `mkdocs-material`
- `mkdocs-awesome-pages-plugin` — clean sidebar titles without renaming folders
- `mkdocs-roamlinks-plugin` — resolves `[[wikilinks]]`
- `mkdocs-glightbox` — image lightbox
- `mkdocs-git-revision-date-localized-plugin` — "last updated" footer from git history
- `mkdocs-redirects` — handle URL changes without breaking bookmarks
- `pymdown-extensions` — tabs, admonitions, callouts, task lists

## Folder & URL Strategy (no renames)

MkDocs with `use_directory_urls: true` produces URL-encoded paths like `/5%20-%20Skills/14_Financial_Analysis/DCF_Valuation_Model/`. That's ugly in a URL bar but **every existing internal link and wikilink continues to work and Obsidian is untouched**. Since the audience is non-technical and navigates via sidebar/search (not URL-typing), URL aesthetics are a low priority.

`.pages` files give clean sidebar titles ("Skills" instead of "5 - Skills"). If pretty URLs later matter, a MkDocs `hooks.py` can rewrite page URLs at build time without touching source paths. Defer until someone complains.

## Theme & Homepage

### Branding

- Primary + accent palette via CSS variables in `brand.css` (override `--md-primary-fg-color`, `--md-accent-fg-color`, etc.).
- Typography: override Material's default Roboto via `theme.font.text` and `theme.font.code` (e.g., `Inter` + `JetBrains Mono`).
- Favicon + logo in `overrides/assets/images/`.
- Dark/light toggle via palette `scheme: slate` / `default`.
- Announcement bar on launch via Material's `announce` block.

### Homepage (replace the README TOC)

Build `index.md` with a `template: home.html` frontmatter, `hide: [navigation, toc]`. In `overrides/home.html`:

- **Hero block** — site title, one-sentence purpose, two CTA buttons ("Getting Started", "Browse Skills").
- **Large search bar** directly under the hero (reuse Material's search partial).
- **Card grid** — 8 cards matching the top-level sections, each with icon, title, one-line description, link.
- **Featured / "Start Here" row** — Setup Guide, Claude Code master guide, top finance prompts.
- **Recent updates** section — auto-populated from the `git-revision-date-localized` plugin or a small `hooks.py` reading frontmatter `updated:`.

Turns the homepage from "giant table of contents" (scary) into "one search box + 8 big tiles + top picks" (airline-website feel).

## Auth Setup Sequence (Entra ID + Azure SWA)

1. Create Azure resource group (`rg-claudewiki-prod`) + Static Web App (Standard tier). Copy deployment token to GitHub Secrets as `AZURE_STATIC_WEB_APPS_API_TOKEN`.
2. Register Entra ID app:
   - **Single-tenant** — this is the gate that restricts to employees.
   - Redirect URI: `https://<swa>.azurestaticapps.net/.auth/login/entraID/callback`.
   - API permissions: `User.Read` (delegated) is sufficient.
   - Generate a client secret.
3. Store client secret as an SWA application setting (`ENTRA_CLIENT_SECRET`). Optionally reference via Azure Key Vault.
4. Add a `customOpenIdConnectProviders.entraID` block to `staticwebapp.config.json` pointing at `https://login.microsoftonline.com/<TENANT_ID>/v2.0/.well-known/openid-configuration`.
5. Route protection: `"routes": [{"route": "/*", "allowedRoles": ["authenticated"]}]` with `responseOverrides` 401 → `/.auth/login/entraID`.
6. Optional later: custom domain `wiki.<company>.com` (add to Entra app redirect URIs).

**Why not the built-in `aad` provider?** Its default registration is multi-tenant and would let any Microsoft account log in. Going custom from day one keeps the gate tight.

## Wikilinks (47 occurrences, 14 files)

**Use `mkdocs-roamlinks-plugin`. Do not rewrite.** The plugin resolves `[[filename]]` at build time. `mkdocs build --strict` in CI will fail on any unresolvable link, so broken wikilinks can't ship. Only migrate to standard links if the plugin is ever abandoned.

## Gotchas to Fix During Setup

- **`.mdx` files** (`5 - Skills/Overview/what-are-skills.mdx`) — MkDocs won't render. Rename to `.md` if contents are pure markdown.
- **Two `Prompts` folders** (`4 - Prompts` and `8 - Prompts`). `.pages` titles must differentiate: "Text Prompts" vs "Media Prompts".
- **Typo filename** `Guide to Claude Dekstop on Windows.md` — fix + update the 1 link, or add a `redirects` rule.
- **First `--strict` build will surface 5–20 pre-existing broken links.** One-time cleanup, not a blocker.
- **URLs stay URL-encoded** (`%20` for spaces). Acceptable; users navigate via sidebar/search.
- **README.md vs index.md** — if `docs_dir: .` and both exist at root, MkDocs picks `index.md`. Keep README for GitHub rendering, make `index.md` the wiki home.
- **`Todo/` and `.claude/`** — exclude from docs; not for employees.

## Cost

| Item | Cost |
|---|---|
| Azure Static Web Apps Standard | ~$9/mo |
| Custom domain SSL | Free (via SWA) |
| Entra ID app registration | Free with any M365 tenant |
| GitHub Actions | Free public, 2000 min/mo free private (build is ~60–90s) |
| **Total** | **~$9/mo** |

## Rollout Sequence

| Phase | Effort | What happens |
|---|---|---|
| 0. Prep | ½ day | Decide brand colors, logo, domain, tenant ID, access approver. Create Azure subscription/RG. Create dev Entra app. Draft 8-card homepage copy. |
| 1. Local build | 1 day | Add `mkdocs.yml`, `requirements.txt`, `.pages` files, overrides, homepage. `mkdocs serve` until nav, search, wikilinks, homepage look right. Fix broken links from `--strict`. |
| 2. Staging deploy | ½ day | Second SWA `claudewiki-staging` bound to `staging` branch. Wire GitHub Actions. No auth yet. |
| 3. Auth on staging | ½ day | Add `staticwebapp.config.json` with staging Entra app. Test employee + non-employee + guest accounts. |
| 4. Pilot | 1 week | 3–5 representative non-technical users. Three tasks: find setup guide, find a finance prompt, search "DCF". Iterate homepage + nav. |
| 5. Prod | ½ day | Promote to prod SWA, prod Entra app, custom domain. Announce via email/Teams with a 90-sec Loom: "search bar is your friend." |
| 6. Ongoing | — | Weekly scheduled `mkdocs build --strict` as link-rot canary. Dependabot on `requirements.txt`. Quarterly nav review. |

**Total focused effort: ~3–5 working days spread over ~2 weeks**, most of it theme polish and pilot feedback rather than infra.

## Verification

### Build-time (CI, automatic)

- `mkdocs build --strict` exits 0 — no broken links, no unresolved wikilinks.
- Artifact under 50 MB.

### Post-deploy smoke tests

- Unauthenticated request → redirected to Entra login.
- Employee account → lands on homepage.
- Non-tenant account → rejected with AADSTS error.
- All 8 homepage cards return 200.
- Search for "DCF" finds the Financial Analysis doc.
- A `[[wikilink]]` in a Financial Analysis page resolves.
- Sidebar shows "Skills" not "5 - Skills".
- Dark-mode toggle works; mobile nav drawer works.
- "Last updated" date appears in footer.
- `.pptx` download works.
- Logout clears session (re-auth required on next visit).

### Ongoing monitoring

- Azure App Insights availability test against the login redirect.
- Weekly scheduled CI rebuild.
- Dependabot on `requirements.txt` for security updates.
