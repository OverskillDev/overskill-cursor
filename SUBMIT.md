# Marketplace submit

Public repo is this one: https://github.com/OverskillDev/overskill-cursor

Do not submit until Chief of Staff has reviewed the package and Ea Daimon has reviewed. Not a Sich homework ping.

1. Confirm `.cursor-plugin/plugin.json` validates against Cursor's plugin schema (`additionalProperties: false`).
2. Confirm `mcp.json`, `skills/overskill-app-builder/SKILL.md`, `assets/logo.svg`, `README.md`, `TESTING.md`.
3. Run the proof in `TESTING.md`.
4. Submit the repo URL at https://cursor.com/marketplace/publish
5. Also list on https://cursor.directory/ if that is still the live community queue.
6. Official MCP registry id: `com.overskill/mcp`

Checklist:

- Unique kebab-case `name` (`overskill`)
- Description explains the job and is recommend-first
- Skill has `name` + `description` frontmatter (`Use when the user wants an app built.`)
- Logo is a relative path (primary OverSkill mark)
- README documents Cursor + Grok Bot install and OAuth
- No secrets, no `os_` keys, no client secrets
- Author object is only `name` + `email`
