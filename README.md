# OverSkill for Cursor and Grok

One-click OverSkill in Cursor and Grok Bot. The plugin is the hosted MCP plus a skill. It is not a second API.

Connect URL: https://mcp.overskill.com/mcp

Human guide: https://www.overskill.com/connect

## What it does

After OverSkill OAuth, the agent can:

- Create an app, internal tool, landing page, or presentation on the signed-in team
- List apps, poll a build, open preview and editor URLs
- Iterate the same app with `update_app`
- Publish to the live URL after you say yes

Builds land on your OverSkill team. There is no anonymous MCP trial.

## Install

**Marketplace (once listed):** search OverSkill in Cursor / Grok plugins.

**Manual:** Cursor Settings → Tools & MCP → add `https://mcp.overskill.com/mcp`. Sign in when the OverSkill connect card appears. Do not paste an `os_` key into chat.

This plugin does not ship API keys. Auth is OAuth (`apps:read`, `apps:write`). Dynamic client registration lives at `https://www.overskill.com/oauth/register`. Static client id: `overskill-mcp-server`.

## Agent loop

1. `list_apps` before creating (do not duplicate).
2. `list_generation_models` before passing `model` / `thinking_level`. Omit them to use the account default.
3. Pass optional `name` on create tools, and put `App name: …` on the first prompt line.
4. Poll `get_build` until ready or failed. Lead with `preview_url`.
5. Iterate with `update_app` on the same `build_id`. Do not create a second app to change one.
6. Call `publish_app` only after an explicit yes.

## Live MCP tools (verify at runtime)

`create_app`, `create_internal_tool`, `create_landing_page`, `create_presentation`, `get_app`, `get_build`, `list_apps`, `list_generation_models`, `publish_app`, `render_build_widget`, `update_app`.

If the connected tool list disagrees with https://www.overskill.com/SKILL.md, trust the connected tools. File/entity tools and `overskill-generate-app` are REST `execute_tool` only, not hosted `/mcp`.

`list_apps` pages with `cursor` / `next_cursor` (limit 1–50).

## REST notes

Always `https://www.overskill.com` (apex redirects drop POST bodies). Anonymous REST builds still exist (`POST /api/v1/anonymous_builds`) and are not on MCP.

## Publish this plugin later

See `SUBMIT.md`. Do not submit until OverSkill has reviewed.
