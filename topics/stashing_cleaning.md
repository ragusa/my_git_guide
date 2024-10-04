
# Git Stashing and Cleaning

## 1. Stash Uncommitted Changes
If you’re in the middle of some work but need to switch branches, you can temporarily save your changes using `git stash`:
```bash
git stash
```

**Explanation:** This saves your uncommitted changes and returns your working directory to the last commit.

## 2. View Stashed Changes
To see a list of all the stashes you’ve made:
```bash
git stash list
```

**Explanation:** This shows all saved stashes in the order they were created.

## 3. Apply Stashed Changes
To reapply your most recent stash:
```bash
git stash apply
```

To reapply and remove the stash at the same time:
```bash
git stash pop
```

**Explanation:** `git stash apply` reapplies the changes but keeps the stash in case you need it again, while `git stash pop` reapplies the changes and removes the stash.

## 4. Clean Untracked Files
To remove untracked files and directories (files not tracked by Git):
```bash
git clean -f
```

**Explanation:** This removes untracked files. Add `-d` to also remove untracked directories.

Use the `-n` flag to preview the files to be removed:
```bash
git clean -n
```

**Explanation:** This previews what would be deleted without actually removing the files.

## 5. Cleaning with Stash
If you want to stash untracked files as well, use:
```bash
git stash -u
```

**Explanation:** This command stashes both tracked and untracked files.

[Back to README](../README.md)
    