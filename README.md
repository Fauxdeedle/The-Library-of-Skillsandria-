# 🧠 Claude Skills Library

A repository for sharing, iterating on, and distributing **Claude skill files** — structured markdown prompts that teach Claude how to reliably perform specific tasks.

---

## What Is a Skill File?

A skill file (typically named `SKILL.md`) is a markdown document that gives Claude explicit instructions for completing a well-defined task — like creating a PowerPoint presentation, building a React component, or generating a formatted Word document.

When a skill file is made available to Claude at runtime (e.g., via a mounted directory), Claude can read it using the `view` tool and follow its guidance to produce higher-quality, more consistent outputs than it would from general training alone.

Think of skills as **reusable, versioned prompt engineering** — shareable across projects, teams, and workflows.

---

## Repository Structure

```
/
├── skills/
│   ├── docx/
│   │   └── SKILL.md          # Word document generation
│   ├── pptx/
│   │   └── SKILL.md          # PowerPoint presentation creation
│   ├── xlsx/
│   │   └── SKILL.md          # Spreadsheet creation and editing
│   ├── pdf/
│   │   └── SKILL.md          # PDF generation and manipulation
│   └── your-skill-name/
│       └── SKILL.md          # Add your own!
└── README.md
```

Feel free to adapt this structure to fit your workflow — skills can be nested, grouped by domain, or kept flat.

---

## How to Use a Skill

1. **Make the skill available to Claude** — Mount the skills directory or provide the file path in your Claude environment.
2. **Claude reads the skill at runtime** — Claude uses the `view` tool to read the appropriate `SKILL.md` before starting a task.
3. **Claude follows the skill's instructions** — The skill overrides default behavior with task-specific best practices.

For best results, trigger the skill explicitly in your system prompt or task setup:

```
Before starting, read the skill file at /mnt/skills/pptx/SKILL.md and follow its instructions.
```

---

## Contributing a Skill

Have a skill that works well? Contributions are welcome.

1. Fork this repository
2. Create a new folder under `/skills/` named after your skill's purpose (e.g., `email-drafting`, `sql-query`, `data-viz`)
3. Add a `SKILL.md` file following the structure below
4. Open a pull request with a brief description of what the skill does and why it works

### Skill File Structure

A good `SKILL.md` typically includes:

- **Purpose** — What task this skill is for
- **Trigger conditions** — When Claude should use this skill
- **Step-by-step instructions** — Exactly what Claude should do
- **Tool usage** — Which tools to call and in what order
- **Output requirements** — File types, formatting standards, quality checks
- **Examples** — Sample inputs/outputs or gotchas to avoid

---

## Tips for Writing Good Skills

- **Be explicit, not suggestive.** Claude follows direct instructions better than hints.
- **Specify tool call order.** If Claude needs to install a library before running a script, say so.
- **Include edge cases.** What should Claude do if a file is missing? If the user's request is ambiguous?
- **Iterate in public.** Use issues and PRs to refine skills based on real usage — what works for one use case may break for another.
- **Version your skills.** Breaking changes to a skill's behavior should be documented.

---

## License

[MIT](LICENSE) — skills in this repo are free to use, modify, and redistribute.

---

*This README was written by [Claude](https://claude.ai), Anthropic's AI assistant.*
