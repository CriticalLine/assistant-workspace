# Contributing to assistant-workspace

Thanks for contributing — we welcome bug fixes, improvements, documentation updates, and experiments. This file explains how to contribute, our workflow, and expectations for quality.

1) Getting started

- Fork the repository (if required by platform) and clone your fork.
- Create a topic branch for your change: `git checkout -b feat/<short-description>`.

2) Issue workflow

- Open an issue to propose larger changes or discuss design before implementation.
- Reference related issues/PRs in commits and PR descriptions with `#<issue-number>`.

3) Branching & naming

- Use descriptive branch names with one of these prefixes: `feat/`, `fix/`, `chore/`, `docs/`, `test/`.
- Keep branches short-lived and focused on a single task.

4) Commit message style

- Use Conventional Commit style: `type(scope): short description`.
- Include a longer explanatory body in the commit message when the change is non-obvious.

5) Pull request process

- Open a PR targeting `main` (or the designated integration branch).
- PR description should include:
  - What changed and why
  - Testing steps and expected results
  - Any migration or rollout notes
  - Checklist of items completed

- Review process:
  - Assign at least one reviewer.
  - Address review comments via follow-up commits; keep the conversation on the PR.
  - Rebase or merge `main` if needed to resolve conflicts prior to merging.

6) Review & approvals

- PRs should have at least one approval from a code owner or team reviewer before merging.
- Critical or large changes may require multiple reviewers.

7) Testing & CI

- Add/maintain tests for code changes. CI must pass before merging.
- If adding long-running tests, mark them appropriately and document how to run locally.

8) Code style & linting

- Follow existing code style in the repo. Add linters or formatting configs if needed.
- Run the linters and formatters locally before opening a PR.

9) Security

- Never commit secrets. Use the org's secrets/credentials store. If a secret is leaked, rotate immediately and open an incident issue.

10) Commit signing (optional)

- If your organization requires signed commits, sign commits with your GPG key: `git commit -S -m "..."`.

11) Adding new dependencies

- Discuss adding significant dependencies in an issue first. Prefer lightweight, actively maintained libraries.
- Document why a dependency is needed and any notable security/privacy implications.

12) Templates & automation (suggested)

- Recommended files to add for better collaboration:
  - `.github/PULL_REQUEST_TEMPLATE.md` — PR template
  - `.github/ISSUE_TEMPLATE/bug_report.md` — issue templates
  - `CODEOWNERS` — map directories to reviewers
  - `docs/` — documentation and design notes

13) Support & escalation

- For CI failures or infra issues, contact the repo owners or the DevOps channel.
- For security incidents, follow the organization's security incident response playbook.

Thank you for contributing! If you'd like, I can create PR and issue templates, CODEOWNERS, and a basic GitHub Actions CI workflow next.