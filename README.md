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

### If it “doesn’t run” for your coworker

1. **`git pull origin main`** so they have `.cursor/skills/` and `.cursor/rules/create-prototype.mdc`.
2. **Open the repo root** in Cursor (**File → Open Folder** → the folder that contains `.cursor/`, not a parent directory).
3. Use **Agent** chat (agent mode), not only inline Ask, if they are generating files.
4. **Update Cursor** to the latest version; Agent Skills need a current build.
5. In chat, try explicitly: **“Read `.cursor/skills/create_prototype/SKILL.md` and follow it. Feature name: `…`. PRD: …”**  
   A project rule also nudges the agent toward that file, but naming the path removes ambiguity.
6. **Personal copy (works in any repo):**  
   `mkdir -p ~/.cursor/skills/create_prototype && cp .cursor/skills/create_prototype/SKILL.md ~/.cursor/skills/create_prototype/`  
   Then restart Cursor. They can still say “follow create_prototype” in other workspaces.

### Optional: attach the Skill in UI

In Agent chat, open the **@** menu and look for **Skills** (or your Cursor version’s equivalent). If `create_prototype` appears, attach it. Names and menus vary by version; the rule + explicit file path above still work without that.

## License

Add a license if you intend open-source use.
