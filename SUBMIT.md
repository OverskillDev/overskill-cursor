# Marketplace submit (later)

Do not submit until OverSkill (Sich) has reviewed this package.

1. Land this directory in a public git repo.
2. Confirm `.cursor-plugin/plugin.json`, `mcp.json`, `skills/overskill-app-builder/SKILL.md`, `assets/logo.svg`, and `README.md`.
3. Test: install in Cursor, complete OverSkill OAuth, `list_apps`, create a throwaway internal tool, `update_app`, do not publish unless intended.
4. Submit the repo URL at https://cursor.com/marketplace/publish
5. Official MCP registry id mentioned by OverSkill: `com.overskill/mcp`

Checklist from Cursor:

- Unique kebab-case `name` (`overskill`)
- Description explains the purpose
- Skill has name + description frontmatter
- Logo is a relative path in the repo
- README documents install and OAuth
- No secrets, no `os_` keys, no client secrets
