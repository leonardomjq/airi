# Branch Management Quick Reference

## Your Fork Has Only 2 Permanent Branches

```
✅ main     - Your stable, working code
✅ upstream - Clean mirror of moeru-ai/airi
```

## Daily Branch Commands

### See what branch you're on
```bash
git branch
# * shows current branch
```

### See all your GitHub branches
```bash
git branch -r | grep origin/
```

### Create a new feature branch
```bash
git checkout main
git checkout -b feature/my-new-feature
```

### Delete a branch after merging
```bash
# Delete locally
git branch -d feature/my-feature

# Delete from GitHub
git push origin --delete feature/my-feature
```

## GitHub Web Views

### To see ONLY your branches:
**https://github.com/leonardomjq/airi/branches/yours**

### To see branch count:
Look for "**2 branches**" link on main page

## Branch Naming Convention

Use these prefixes to stay organized:

- `feature/name` - New features
- `fix/name` - Bug fixes
- `experimental/name` - Risky tests
- `docs/name` - Documentation
- `refactor/name` - Code cleanup

## Weekly Cleanup Routine

```bash
cd /c/Users/leona/Downloads/airi-fork-new

# 1. See all branches
git branch -a

# 2. Delete merged feature branches
git branch -d feature/old-completed-feature
git push origin --delete feature/old-completed-feature

# 3. Verify you only have main + upstream + active features
git branch
```

## What NOT to Do

❌ Don't commit directly to `main`
❌ Don't commit to `upstream` (it should mirror moeru-ai/airi exactly)
❌ Don't keep feature branches forever
❌ Don't push every experimental branch to GitHub

## What TO Do

✅ Always create feature branches
✅ Merge to main only when tested
✅ Delete branches after merging
✅ Keep main stable and working
✅ Sync upstream regularly

## Quick Status Check

```bash
# How many branches do I have?
git branch | wc -l

# What's on GitHub?
git ls-remote --heads origin | wc -l

# Should always be 2-5 total (main + upstream + 0-3 active features)
```

## If Your GitHub Shows More Than 5 Branches

You might have stale branches from the original fork. Check:
https://github.com/leonardomjq/airi/branches/stale

Delete any you don't recognize or need.
