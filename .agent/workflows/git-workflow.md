---
description: Git workflow for staging and main branches
---

# Git Workflow: Staging → Main

This project uses a two-branch workflow:
- **staging**: Development branch where all work happens
- **main**: Production branch with clean, squashed commits

## Daily Development Workflow

### 1. Start working on staging branch
```bash
git checkout staging
git pull origin staging
```

### 2. Make your changes and commit regularly
```bash
# Make changes to your files
git add .
git commit -m "Your descriptive commit message"
```

### 3. Push to staging branch
```bash
git push origin staging
```

## Merging Staging to Main (Squash All Commits)

When you're ready to merge your work from staging to main as a single commit:

### 1. Switch to main and update it
```bash
git checkout main
git pull origin main
```

### 2. Merge staging with squash (combines all commits into one)
```bash
git merge --squash staging
```

### 3. Create a single commit with all changes
```bash
git commit -m "Descriptive message for all changes from staging"
```

### 4. Push to main
```bash
git push origin main
```

### 5. Switch back to staging for continued development
```bash
git checkout staging
```

## Quick Reference

**Current branch status:**
```bash
git branch -vv
```

**See commit history:**
```bash
git log --oneline --graph --all
```

**Discard local changes:**
```bash
git reset --hard origin/staging
```

## Important Notes

- Always work on the **staging** branch
- Only merge to **main** when you have a complete feature or set of changes
- The `--squash` flag combines all staging commits into one clean commit on main
- This keeps main's history clean and easy to understand
