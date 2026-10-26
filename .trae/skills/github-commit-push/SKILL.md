---
name: github-commit-push
description: Commit all changes and push the whole project to the GitHub remote github.com/syr328/sang over SSH. Use when the user asks to 提交到GitHub, push to GitHub, or sync the project to GitHub. Do not use for Gitee pushes.
---

# Commit and Push to GitHub

Push this coursework project to the GitHub repository `github.com/syr328/sang` (SSH public key already configured).

## Workflow

1. Inspect before committing: run `git status`, `git diff --stat`, and `git log --oneline -5`.
2. Stage intended files by name (`git add <files>`). Never commit secrets or keys.
3. Commit with a concise imperative message in English, matching repo style (e.g. `Add 15-1 count-seven game page`).
4. Ensure the GitHub remote exists — `origin` points to Gitee, so GitHub uses a separate remote named `github`:
   - Check with `git remote -v`.
   - If missing: `git remote add github git@github.com:syr328/sang.git`
5. Push the current branch: `git push -u github main`
6. Verify with `git status` (branch should be up to date with `github/main`).

## Rules

- Only push to the `github` remote in this skill. Do not touch `origin` (Gitee).
- Never force-push (`--force`) or amend unless the user explicitly asks.
- If the push fails on SSH auth, run `ssh -T git@github.com` to diagnose and report the result to the user instead of retrying in a loop.
- Shell is PowerShell 5 — chain commands with `;`, not `&&`.
