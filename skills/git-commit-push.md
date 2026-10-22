# Git Commit and Push

## Description
Use when the user asks to commit changes and push to a remote repository (e.g., Gitee, GitHub).

## Workflow

1. Check current git status: `git status`
2. Stage all intended files: `git add <files>` (never commit secrets or keys)
3. Write a concise commit message matching repo style
4. Commit: `git commit -m "<message>"`
5. Add remote if not present: `git remote add origin <url>`
6. Push: `git push -u origin main`

## Rules
- Inspect `git status`, `git diff`, and `git log --oneline -10` before committing
- Stage only intended files; never commit secrets or keys
- Do not force-push or amend unless explicitly requested
- If push fails due to auth, inform the user to check credentials
