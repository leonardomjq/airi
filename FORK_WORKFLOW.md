# Fork Workflow Guide

This document explains how to maintain this fork of AIRI and keep it synchronized with the upstream repository.

## Repository Setup

This fork uses a two-branch strategy:

- **`main`**: Your custom changes and enhancements to AIRI
- **`upstream`**: Mirrors the original `moeru-ai/airi` main branch

## Git Remotes

Two remotes are configured:

```bash
origin     https://github.com/leonardomjq/airi.git      # Your fork
upstream   https://github.com/moeru-ai/airi.git         # Original repository
```

## Syncing from Upstream

### 1. Update the upstream branch

First, fetch the latest changes and update your local `upstream` branch:

```bash
git checkout upstream
git pull upstream main
```

### 2. Review changes

See what's new in the upstream repository:

```bash
git log upstream..HEAD  # Changes you've made
git log HEAD..upstream  # Changes from upstream
git diff main upstream  # All differences between your work and upstream
```

### 3. Merge upstream changes into main

Merge the latest upstream changes into your main branch:

```bash
git checkout main
git merge upstream
```

This will merge the upstream changes into your main branch. Resolve any conflicts if they occur.

### 4. Push updates

Push both branches to your fork on GitHub:

```bash
git push origin main
git push origin upstream
```

## Working on Features

### Creating a new feature

For larger features, consider creating a feature branch:

```bash
git checkout main
git checkout -b feature/your-feature-name
# Make your changes...
git add .
git commit -m "Your commit message"
git push origin feature/your-feature-name
```

### Merging features

Once your feature is complete and tested:

```bash
git checkout main
git merge feature/your-feature-name
git push origin main
```

## Common Tasks

### Check your current branch and remote tracking

```bash
git branch -vv
```

### See all remotes

```bash
git remote -v
```

### View commit history with both branches

```bash
git log --oneline --graph --all --decorate
```

### Compare your main with upstream

```bash
git diff upstream..main          # See your changes
git log --oneline upstream..main # See your commits
```

## Recommended Workflow

1. **Weekly sync**: Pull from upstream weekly to stay current
2. **Before major work**: Sync with upstream before starting significant features
3. **After merging upstream**: Test your application to ensure upstream changes didn't break your enhancements
4. **Document changes**: Update AI_ASSISTANT_PROJECT.md with implementation notes as you build features

## Emergency: Reset to Upstream

If you need to reset your main branch to match upstream exactly (⚠️ **this will delete your changes**):

```bash
git checkout main
git reset --hard upstream
git push origin main --force
```

Only do this if you're certain you want to discard all your custom changes!

## Tips

- Keep your changes modular and well-documented
- Test after merging from upstream
- Consider rebasing your feature branches before merging to main for a cleaner history
- Tag important milestones in your development with `git tag v1.0-enhanced` etc.

## Questions?

- Original AIRI documentation: https://airi.moeru.ai/docs/
- Original AIRI repository: https://github.com/moeru-ai/airi
- Your fork: https://github.com/leonardomjq/airi
