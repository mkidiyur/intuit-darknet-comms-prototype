# intuit-darknet-comms-prototype

Intuit-related HTML prototypes and tooling.

## Cursor Agent Skill: `create_prototype`

This repo includes a [Cursor Agent Skill](https://docs.cursor.com) that generates self-contained HTML prototypes in the Intuit Security Center design system.

**Location in this repo**

- **Cursor:** `.cursor/skills/create_prototype/SKILL.md`
- **Claude Code:** `.claude/skills/create_prototype/SKILL.md` (same instructions)

**After you clone**

1. Open this folder as a workspace in Cursor.
2. In chat, attach the skill or ask for a prototype (e.g. “use create_prototype”); provide a **feature name** and **PRD** inline.
3. The agent writes `<feature-name>-prototype.html` in the project root.

**Use in another project**

Copy the folder `.cursor/skills/create_prototype/` into that project’s `.cursor/skills/` directory, or copy `SKILL.md` to `~/.cursor/skills/create_prototype/SKILL.md` for a personal skill available in all your projects.

## License

Add a license if you intend open-source use.
