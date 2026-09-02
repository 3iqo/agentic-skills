# agentic-skills

Curated bundle of [Claude Office Skills](https://github.com/anthropics/skills) cleaned up to comply with [agentic-skill-validator](https://github.com/revanthpobala/skill-atlas) rules.

## Layout

```
.
├── .github/workflows/validate-skills.yml   # CI: blocks PRs with invalid skills
└── skills/                                # the actual skills (one folder per skill)
    ├── academic-search/
    ├── amazon-seller/
    ├── ...
    └── _template/                         # placeholder template (validator ignores)
```

## Validation

Run locally:

```bash
npx --yes agentic-skill-validator ./skills
```

Rules enforced:

- `name:` must equal the folder name and be strict kebab-case.
- `description:` cannot contain `<` or `>`.
- Folder must contain a single `SKILL.md` (no `README.md`).
- Folder name must be strict kebab-case.

The single `_template/` failure is expected — it is a meta-template, not a real skill.

## CI

Every push and PR runs the validator via GitHub Actions. PRs with new violations are blocked.

## Reference

- Tool: <https://github.com/revanthpobala/skill-atlas>
- Web IDE: <https://atlas-skills.netlify.app>