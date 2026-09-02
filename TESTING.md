# Proof plan

Do this before marketplace submit.

## Local install (Cursor)

1. Copy or symlink this repo to `~/.cursor/plugins/local/overskill`
2. Reload the window (Developer: Reload Window)
3. Open Customize. Confirm OverSkill appears with the green mark, the skill, and the MCP server.
4. Complete OverSkill OAuth. Do not paste an `os_` key.
5. `list_apps`
6. Create a throwaway internal tool. Poll `get_build` until ready. Open `preview_url`.
7. `update_app` on the same `build_id`.
8. Do not `publish_app` unless that is the intended test.

On Teams/Enterprise, local plugin imports may be off. Use a machine where they are allowed, or wait for marketplace listing.

## Catalog (after listing)

1. SearchPlugins / Cursor Customize search: `OverSkill` returns this plugin.
2. Grok Bot: install via the catalog (same plugin id). Deep link form: `grokbot://app/v1/plugin/add?id=<id>` once assigned.
3. Repeat OAuth + `list_apps` smoke on a Grok Bot.

## Fail the proof if

- Logo is the old orange-circle placeholder
- Skill description is not `Use when the user wants an app built.`
- MCP URL is not `https://mcp.overskill.com/mcp`
- An API key is required
- Create duplicates an existing app without `list_apps`
