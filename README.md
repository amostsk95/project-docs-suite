# project-docs-suite

Cursor Agent Skill that generates a full project documentation suite from the codebase:

- Product Requirements (`docs/PRD.md`)
- System Design & UI/UX (`docs/SYSTEM_DESIGN_UIUX.md`)
- System Architecture (`docs/SYSTEM_ARCHITECTURE.md`)
- AI Agent Instructions (`docs/AI_AGENT_INSTRUCTIONS.md` + `AGENTS.md`)
- Mermaid sources (`docs/diagrams/*.mmd`)
- Optional cross-document consistency review

Filled from the **current repository**; unknowns marked `[TBD]`. Does not invent commands or stack versions.

## Install into a project

### Option A — copy into the project (recommended)

```bash
mkdir -p .cursor/skills
cp -R /path/to/project-docs-suite/.cursor/skills/project-docs-suite .cursor/skills/
```

Or from this clone:

```bash
git clone https://github.com/amostsk95/project-docs-suite.git
cp -R project-docs-suite/.cursor/skills/project-docs-suite /path/to/your-app/.cursor/skills/
```

### Option B — user-level skill (this machine)

```bash
mkdir -p ~/.cursor/skills
cp -R .cursor/skills/project-docs-suite ~/.cursor/skills/
```

### Option C — git submodule

```bash
git submodule add https://github.com/amostsk95/project-docs-suite.git vendor/project-docs-suite
mkdir -p .cursor/skills
ln -s ../../vendor/project-docs-suite/.cursor/skills/project-docs-suite .cursor/skills/project-docs-suite
```

## Use

In Cursor chat:

- `/project-docs-suite`
- or: “Generate the PRD / architecture / UI docs suite”

## Layout

```text
.cursor/skills/project-docs-suite/
  SKILL.md
  references/
    deliverables.md    # section outlines + diagram list
    quality-rules.md   # SoT priority + conflict handling
```

Root `SKILL.md` and `references/` mirror the skill for browsing on GitHub.

## Provenance

Extracted from [amostsk95/MyPersonalDictionary](https://github.com/amostsk95/MyPersonalDictionary) after shipping Desk’s documentation package.

## License

MIT
