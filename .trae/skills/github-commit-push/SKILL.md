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
   - If missing or pointing elsewhere: `git remote set-url github ssh://git@ssh.github.com:443/syr328/sang.git`
   - Note: port 22 to github.com is blocked on this network, so the remote MUST use the ssh.github.com:443 endpoint.
5. Push with the local identity key (named `id_ed25519_gitee`, not a default key name, so ssh alone cannot find it):
   ```powershell
   $env:GIT_SSH_COMMAND = "ssh -i C:/Users/34186/.ssh/id_ed25519_gitee -o StrictHostKeyChecking=accept-new -o ConnectTimeout=20"; git push -u github main
   ```
   Do not rely on `~/.ssh/config` — it contains no GitHub entry.
6. Verify with `git status` (branch should be up to date with `github/main`).

## Rules

- Only push to the `github` remote in this skill. Do not touch `origin` (Gitee).
- Never force-push (`--force`) or amend unless the user explicitly asks.
- If the push fails on SSH auth, run `ssh -T git@github.com` to diagnose and report the result to the user instead of retrying in a loop.
- Shell is PowerShell 5 — chain commands with `;`, not `&&`.
