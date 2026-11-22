# Contributing Guide

## 1. Branches

- `main`: stable, demo-ready. Receives merges from `develop` only.
- `develop`: integration branch. All features merge here.
- `feature/<task-id>-<short-name>`: new work. Example: `feature/CU-12-register-endpoint`
- `bugfix/<task-id>-<short-name>`: bug fixes.
- `hotfix/<short-name>`: urgent fix, branched from `main`.
- Never push directly to `main` or `develop`.

## 2. Daily Flow

1. Pick a task in ClickUp and move it to In Progress.
2. Sync and create your branch:
   ```
   git checkout develop
   git pull
   git checkout -b feature/CU-12-register-endpoint
   ```
3. Work in small commits.
4. Push and open a Pull Request into `develop`.
5. Move the task to Review.
6. After approval: Squash and merge, delete the branch, move the task to Done.

## 3. Commit Messages

Format: `<type>(<scope>): <description>`

- Types: feat, fix, docs, refactor, test, chore, ci
- Examples:
  - feat(identity): add register endpoint
  - fix(chat): block messages before request is accepted
  - docs(use-cases): add chat use cases
- Present tense, under 72 characters, one purpose per commit.

## 4. Pull Requests

- Title follows the commit format.
- Link the ClickUp task in the description.
- Keep PRs small (under about 400 changed lines).
- At least 1 approval from another team member.
- CI must pass.
- Resolve all review comments.
- Merge strategy:
  - feature into develop: Squash and merge
  - develop into main: Merge commit

## 5. Code Review

- Review within 24 hours.
- Comment on the code, not the person.
- Check: it works, readable, tested, no secrets, follows the architecture.

## 6. Releases

- End of each sprint: PR from `develop` into `main`, then tag (v0.1.0, v0.2.0).

## 7. Hotfix

- Branch from `main`, PR into `main`, then merge `main` back into `develop`.

## 8. Rules

- No secrets in the repo (passwords, keys, connection strings). Use environment variables.
- Do not commit build output (bin, obj, node_modules).
- Run `git pull origin develop` before opening a PR.

## 9. Definition of Done

- Code builds and works
- Tests added and passing
- Reviewed and approved
- Docs updated if behavior changed
