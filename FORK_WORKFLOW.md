# Fork Workflow Guide

This document explains how to maintain this fork of AIRI and keep it synchronized with the upstream repository.

## Repository Setup

This fork uses a **simplified flow** strategy optimized for safe development:

### Branch Types

**Permanent Branches:**
- **`upstream`**: Clean mirror of moeru-ai/airi (NEVER commit directly here)
- **`main`**: Your stable, working version (should ALWAYS work!)

**Temporary Feature Branches:**
- **`feature/name`**: Individual features you're building
- **`experimental/name`**: Wild experiments that might not work out
- **`fix/name`**: Bug fixes

### The Golden Rule

> **NEVER work directly on `main`!** Always create a feature branch. This way, if something breaks, your working code is safe.

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

## Complete Development Workflow

### Starting a New Feature (Step-by-Step)

Let's say you want to add advanced memory learning from your planning doc.

**Step 1: Make sure main is up to date**
```bash
git checkout main
git pull origin main
```

**Step 2: Create a feature branch**
```bash
git checkout -b feature/advanced-memory
```
This creates a new branch based on `main`. Now you can experiment safely!

**Step 3: Work on your feature**
```bash
# Make changes to files...
# Test your changes...

# Save your work frequently
git add .
git commit -m "Add vector database integration for memory"

# Continue working...
git add .
git commit -m "Implement memory retrieval system"
```

**Step 4: Push your feature branch to GitHub (backup)**
```bash
git push origin feature/advanced-memory
```
Now your work is backed up on GitHub, even if it's not done yet!

**Step 5: Test thoroughly**
```bash
# Run the app, test everything...
# Make sure nothing is broken
```

**Step 6: Merge into main (only when it works!)**
```bash
git checkout main
git merge feature/advanced-memory
git push origin main
```

**Step 7: Clean up the feature branch**
```bash
git branch -d feature/advanced-memory           # Delete locally
git push origin --delete feature/advanced-memory # Delete from GitHub
```

### Working on Multiple Features

You can have multiple feature branches at once:

```bash
git branch
  main
  feature/advanced-memory
  feature/live2d-emotions
  experimental/voice-cloning
  * feature/response-optimization
```

Switch between them anytime:
```bash
git checkout feature/live2d-emotions  # Work on emotions
# ... make changes ...
git checkout feature/voice-cloning    # Switch to voice work
```

### When Things Break (Recovery Strategies)

**Scenario 1: Your feature branch is broken, but main is fine**
```bash
# Just delete the broken branch and start over
git checkout main
git branch -D feature/broken-thing  # Force delete
git checkout -b feature/broken-thing  # Start fresh
```

**Scenario 2: You accidentally committed to main**
```bash
# Move your commits to a new branch
git branch feature/my-work   # Save your work
git reset --hard origin/main # Reset main to GitHub version
git checkout feature/my-work # Continue working here
```

**Scenario 3: You want to abandon all local changes**
```bash
git checkout main
git reset --hard origin/main  # Match exactly what's on GitHub
git clean -fd                 # Remove untracked files
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

## Understanding Pull Requests (Contributing to Open Source)

Even though you're building your own enhanced version, you might want to contribute improvements back to the original AIRI project. Here's how that works:

### What's a Pull Request (PR)?

A Pull Request is how you propose changes to someone else's repository. Think of it as saying: "Hey, I made this cool improvement, would you like to include it in your project?"

### When to Contribute Back to Upstream

Consider contributing when you:
- Fix a bug that exists in the original project
- Add a feature that would benefit all AIRI users
- Improve documentation or fix typos
- Optimize performance in a general way

### How to Create a Pull Request

**Step 1: Create a clean feature branch from upstream**
```bash
git checkout upstream
git checkout -b feature/my-contribution
```
Start from `upstream` (not `main`) so your PR doesn't include all your personal customizations!

**Step 2: Make your changes**
```bash
# Make ONLY the changes you want to contribute
# Test thoroughly
git add .
git commit -m "Add improved memory caching system"
git push origin feature/my-contribution
```

**Step 3: Create PR on GitHub**
1. Go to https://github.com/leonardomjq/airi
2. Click "Pull Requests" → "New Pull Request"
3. Change base repository to `moeru-ai/airi` (not your fork!)
4. Select your feature branch as the compare branch
5. Write a clear description of what you changed and why
6. Click "Create Pull Request"

**Step 4: Respond to feedback**
The maintainers might ask questions or request changes. Be responsive and polite!

### Should You Contribute Everything?

**DO contribute:**
- Bug fixes
- Performance improvements
- General features
- Documentation fixes

**DON'T contribute:**
- Your personal customizations
- Features specific to your use case
- Experimental/unfinished work
- Changes that break existing functionality

### Keeping Your Fork and Contributions Separate

This is why we keep the `upstream` branch! You can:
- Build your personal features on `main`
- Create contributions from `upstream`
- Keep them completely separate

## Recommended Workflow

1. **Weekly sync**: Pull from upstream weekly to stay current
2. **Before major work**: Sync with upstream before starting significant features
3. **After merging upstream**: Test your application to ensure upstream changes didn't break your enhancements
4. **Document changes**: Update AI_ASSISTANT_PROJECT.md with implementation notes as you build features
5. **Use feature branches**: ALWAYS work on branches, never directly on main

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
- Commit often with clear messages
- Push feature branches to GitHub for backup
- Don't be afraid to experiment - that's why we have feature branches!

## Quick Reference Cheat Sheet

### Daily Development
```bash
# Start a new feature
git checkout main
git checkout -b feature/my-feature

# Work and save progress
git add .
git commit -m "Description of changes"
git push origin feature/my-feature

# Merge when ready
git checkout main
git merge feature/my-feature
git push origin main
git branch -d feature/my-feature
```

### Weekly Maintenance
```bash
# Sync from upstream
git checkout upstream
git pull upstream main
git checkout main
git merge upstream
git push origin main upstream
```

### Emergency Commands
```bash
# Discard all local changes
git checkout main
git reset --hard origin/main

# See what branch you're on
git branch

# See differences from main
git diff main

# Undo last commit (keep changes)
git reset --soft HEAD~1

# Undo last commit (discard changes)
git reset --hard HEAD~1
```

### Useful Info Commands
```bash
git status              # What's changed?
git log --oneline -10   # Recent commits
git branch -vv          # All branches
git diff                # What did I change?
git remote -v           # Where am I connected?
```

## Questions?

- Original AIRI documentation: https://airi.moeru.ai/docs/
- Original AIRI repository: https://github.com/moeru-ai/airi
- Your fork: https://github.com/leonardomjq/airi
