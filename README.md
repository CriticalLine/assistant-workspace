# assistant-workspace

A shared collaboration workspace for contributors building assistant features, experiments, and integrations. This repository holds code, documentation, CI configuration, and other artifacts used to develop and maintain the assistant.

Table of contents
- Purpose
- Quick start
- Branching & workflow
- Commit messages
- Pull request checklist
- Graduation & clean-up
- Testing & CI
- Security & secrets
- Support & communication

Purpose

This repo is a sandbox and integration workspace where team members can:
- Prototype features and integrations
- Iterate on documentation and developer tooling
- Maintain shared utilities and CI workflows used across assistant projects

This is NOT intended as:
- Long-term production home for released services
- A place to store personal forks or throw-away spikes that live >2–3 weeks
- The canonical repository for critical shared libraries (those should live in a dedicated repo)

If something graduates from prototype → production, move or extract it to a dedicated repository and update references here.

Quick start

1. Clone the repo
   git clone <repo-url>
   cd assistant-workspace

2. Sync main
   git fetch origin
   git checkout main
   git pull --ff-only origin main

3. Create a feature branch
   git checkout -b feat/<short-description>

Branching & workflow

- Always create a branch for changes. Use descriptive prefixes: `feat/`, `fix/`, `chore/`, `docs/`, `test/`.
- For short-lived experiments/spikes you may also use `exp/<you>/<topic>` or `play/<nickname>/...` — delete these branches within 1–2 weeks.
- Prefer small, focused PRs. Aim for <300 lines when possible.
- Rebase or merge frequently to stay up to date with `main`.
- After merge, delete your branch.

Commit messages

Follow a lightweight Conventional Commits style:
- Format: `type(scope): short description`
- Examples:
  - `feat(api): add healthcheck endpoint`
  - `fix(cli): correct flag parsing`
  - `docs(readme): improve usage examples`

Optional: emoji prefixes are allowed for extra skimmability (e.g. ✨, 🐛, 📝).

Pull Request checklist

Before requesting review, ensure your PR includes:
- A clear title and description of what changed and why
- Testing steps and expected results
- Screenshots or logs for UI/behavioral changes if relevant
- Linked issue(s) when applicable
- CI passing (status checks green)
- At least one reviewer assigned

Extra experiment-focused items (recommended for this workspace):
- Why this experiment matters / what question are we trying to answer?
- How long do you expect this branch / feature to live? (delete soon / candidate for graduation / indefinite playground)

Graduation & clean-up

When an experiment proves valuable or is moving toward production:
1. Create a new dedicated repository (or move the code to the target product repo).
2. Copy or migrate the valuable parts and document the migration.
3. Archive or delete the prototype branch in this repo.
4. Leave a short note in a commit or PR description about where it moved (e.g., `chore: graduated prototype → see assistant-health-api repo`).

Aim to keep this workspace clean — delete merged/obsolete branches regularly.

Testing & CI

- Add unit or integration tests for code changes where possible. CI must pass before merging.
- Keep CI fast by running only impacted suites if supported.
- If an experiment needs external secrets, document required secrets and test data (do not commit them).

Security & secrets

- Never commit credentials, secrets, or private keys. Use the organization's secret storage for CI and deployment secrets.
- If a secret is accidentally committed, rotate it immediately and notify the team.
- If your experiment requires an API key or external service, use repository secrets and ask #assistant-dev for help.

Support & communication

- Coordinate large refactors or architecture changes in team chat or open an issue first.
- For elevated access or CI secrets, request permission from repo owners.

Contributing

See CONTRIBUTING.md for detailed contribution guidelines, templates, and contact points.

Next steps (recommended)
- Add `.github/CODEOWNERS` to auto-request reviewers.
- Add `.github/pull_request_template.md` with the experiment checklist above.
- Add a minimal GitHub Actions CI workflow that runs lint/type checks.

If you want, I can add CODEOWNERS, a PR template, and a minimal CI workflow and open a branch/PR with these changes.