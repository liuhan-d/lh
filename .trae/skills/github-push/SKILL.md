---
name: github-push
description: Commit all changes and push the project to the GitHub remote repository at https://github.com/liuhan-d/lh.git. Use when the user asks to submit, commit, push, or upload the project to GitHub.
---

## What I do

1. Ensure the GitHub remote is configured
2. Check status and recent commits
3. Stage all project files
4. Create a commit with a descriptive message
5. Push to the GitHub remote repository

## Workflow

### 1. Check/Configure Remote

```powershell
$existing = git remote get-url github 2>$null
if ($LASTEXITCODE -ne 0) {
    git remote add github https://github.com/liuhan-d/lh.git
}
```

### 2. Check Status

```powershell
git status --short
git log --oneline -3 2>$null
```

### 3. Stage All Files

```powershell
git add -A
```

### 4. Commit

Create a meaningful commit message based on what changed:
- If new exercise pages were added: `"Add exercise pages: [list page names]"`
- If modifications to existing pages: `"Update exercise pages: [list changes]"`
- If rules/docs changed: `"Update project rules in AGENTS.md"`
- If initial commit: `"Initial commit - 高级网页设计 coursework pages"`
- Otherwise: `"Update project files"`

```powershell
git commit -m "<message>"
```

### 5. Push

```powershell
git -c http.sslBackend=schannel push -u github main
```

If the push fails because the remote has different history, use `git push -u github main --force` only after confirming with the user.

## Notes

- Repository URL: `https://github.com/liuhan-d/lh.git`
- This machine's OpenSSL backend fails TLS verification for github.com ("unable to get local issuer certificate") — always push/ls-remote with `-c http.sslBackend=schannel` (uses the Windows certificate store); if `git` is not on PATH, use the full path `& "C:\Program Files\Git\cmd\git.exe"`
- Remote name: `github`
- Branch: `main`
- The project contains HTML/CSS exercise pages for 高级网页设计 coursework
- Some filenames contain Chinese characters and spaces — git handles these correctly on Windows
- Do NOT commit secrets or API keys
