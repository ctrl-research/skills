# skills

A library of reusable agent skills. See [AGENTS.md](AGENTS.md) for repository
structure and authoring conventions; start new skills from
[templates/skill-template](templates/skill-template/SKILL.md).

## Skill Catalog

| Skill | Description |
|---|---|
| [org-defaults](skills/org-defaults/SKILL.md) | ctrl-research org values and governance policy referenced by the other skills |
| [pr-commit-conventions](skills/pr-commit-conventions/SKILL.md) | Conventions for branches, commit messages, and pull requests |

## Using a Skill

Copy a skill's directory into the target agent environment (e.g.
`.claude/skills/` or `.agents/skills/` in the consuming repo). Skills are
org-neutral by convention; install [org-defaults](skills/org-defaults/SKILL.md)
alongside them to apply ctrl-research values and governance policy.

## Repository

- **Structure and authoring conventions** — [AGENTS.md](AGENTS.md)
- **New skills** — start from [templates/skill-template](templates/skill-template/SKILL.md)
- **CODEOWNERS** — `@ctrl-research/reviewers` auto-requested on PRs
- **Branch protection** — `main` requires PRs and review
- **Renovate** — dependency updates (`renovate.json`, `.github/renovate-config.js`)
