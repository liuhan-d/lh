---
name: gitee-push
description: Commit all changes and push the project to the Gitee remote repository at https://gitee.com/liu-hanabc/lh_html.git. Use when the user asks to submit, commit, push, or upload the project to Gitee.
metadata:
  opencode/slash: "false"
  opencode/autoinvoke: "false"
---

## What I do

1. Ensure the Gitee remote is configured
2. Stage all project files
3. Create a commit with a descriptive message
4. Push to the Gitee remote repository

## Workflow

### 1. Check/Configure Remote

```powershell
$existing = git remote get-url gitee 2>$null
if ($LASTEXITCODE -ne 0) {
    git remote add gitee https://gitee.com/liu-hanabc/lh_html.git
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
- If initial commit: `"Initial commit - 高级网页设计 coursework pages"`
- Otherwise: `"Update project files"`

```powershell
git commit -m "<message>"
```

### 5. Push

```powershell
git push -u gitee main
```

If the push fails because the remote has different history, use `git push -u gitee main --force` only after confirming with the user.

## Notes

- Repository URL: `https://gitee.com/liu-hanabc/lh_html.git`
- Remote name: `gitee`
- Branch: `main`
- The project contains HTML/CSS exercise pages for 高级网页设计 coursework
- Some filenames contain Chinese characters and spaces — git handles these correctly on Windows
- Do NOT commit secrets or API keys
