# Git Role Distribution: AI SOC Copilot

**Version:** 1.0  **Date:** 30 October 2026
**Repository:** https://github.com/dija040/ai-soc-copilot

## 1. Team

| # | Name | GitHub username |
|---|---|---|
| 1 | Khadija Maraoui | @dija040 |
| 2 | Name | @to-be-added |
| 3 | Name | @to-be-added |
| 4 | Name | @to-be-added |
| 5 | Name | @to-be-added |

## 2. Role distribution

| Member | Git role | Owned folders | Spec features | Branch prefix | Reviews PRs of |
|---|---|---|---|---|---|
| Member 1 | Maintainer: repo setup, merges to `main`, README, Docker, releases, final demo | `docs/`, root files | AC10, deliverables 1, 9, 10 | `chore/`, `docs/` | Member 5 |
| Member 2 | Developer: data layer | `ingestion/`, `storage/` | F01, F02, F08 | `feature/ingestion-*`, `feature/storage-*` | Member 3 |
| Member 3 | Developer: detection | `detection/` | F03, F04 | `feature/detection-*` | Member 4 |
| Member 4 | Developer: AI explanation | `explanation/` | F05, F06 | `feature/ai-*` | Member 5 |
| Member 5 | Developer: dashboard and evaluation | `dashboard/`, `evaluation/`, `tests/` | F07, F09 | `feature/dashboard-*`, `feature/eval-*` | Member 2 |

Each folder has one owner. Changes to another member's folder need that
owner's review.

## 3. Repository structure

```
ai-soc-copilot/
├── ingestion/      # Member 2
├── storage/        # Member 2
├── detection/      # Member 3
├── explanation/    # Member 4
├── dashboard/      # Member 5
├── evaluation/     # Member 5
├── tests/          # Member 5 (each member adds tests for own module)
├── docs/           # Member 1
├── .gitignore
├── .env.example
└── README.md
```

## 4. Branching strategy

- `main` is always stable and working. Nobody pushes directly to it.
- Every task gets its own branch from the latest `main`.
- Branch names: `feature/<module>-<task>`, `fix/<task>`, `docs/<task>`, `test/<task>`.
  Example: `feature/detection-bruteforce-rule`.
- Delete the branch after it is merged.

## 5. Commit convention

Format: `type: short description`

- `feat:` new feature (`feat: add failed-login rule`)
- `fix:` bug fix (`fix: handle empty log lines`)
- `test:` tests (`test: add normalization tests`)
- `docs:` documentation (`docs: update README`)
- `chore:` setup and maintenance

## 6. Pull Request and review process

1. Create a branch, commit, and push it.
2. Open a Pull Request with a short description and `Closes #issue-number`.
3. The assigned reviewer reviews within 48 hours (approve or request changes).
4. At least 1 approval and passing tests are required.
5. The Maintainer merges and the branch is deleted.

## 7. Issues and milestones

- One GitHub Issue per task, assigned to the module owner.
- 8 milestones, one per week of the project plan (Week 1 Setup to Week 8 Finalization).

## 8. Conflict handling

- Update your branch from `main` before opening a PR.
- Do not edit another member's folder without telling the owner.
- If there is a disagreement, the team decides together, and the Maintainer
  has the final word.

## 9. Security rules for Git

- Never commit API keys, passwords, or `.env` files (use `.env.example`).
- Commit only synthetic or sanitized logs, never real sensitive data.
- Keep test data separate from any machine learning training data.

## 10. Weekly responsibilities

| Week | Focus | Main owner(s) |
|---|---|---|
| 1 | Planning, repo and environment setup | Member 1 |
| 2 | Ingestion and normalization | Member 2 |
| 3 | Rule-based detection | Member 3 |
| 4 | Detection and prioritization, baseline evaluation | Member 3, Member 5 |
| 5 | AI-assisted explanations | Member 4 |
| 6 | Dashboard and investigation history | Member 5, Member 2 |
| 7 | Security, testing, limitations | All members |
| 8 | Finalization, demo, documentation | Member 1, all members |

## 11. Version history

| Version | Date | Change |
|---|---|---|
| 1.0 | 30 Oct 2026 | Initial proposal |