
# Undoing a Commit That Was Not Pushed

## 1. Using `git reset` to Undo a Commit
If you have committed changes locally but haven’t pushed them to the remote repository, you can easily undo the commit using `git reset`.

### 1.1 Undo the Last Commit but Keep Changes
To undo the last commit but keep the changes in your working directory, use:
```bash
git reset --soft HEAD~1
```

**Explanation:** This moves the HEAD back by one commit but leaves your changes staged, allowing you to make a new commit.

### 1.2 Undo the Last Commit and Unstage Changes
To undo the last commit and unstage the changes (but keep them in your working directory), use:
```bash
git reset HEAD~1
```

**Explanation:** This resets both the commit and the staging area, but your working directory remains unchanged.

### 1.3 Undo the Last Commit and Remove Changes
If you want to completely undo the commit and remove the changes as well:
```bash
git reset --hard HEAD~1
```

**Explanation:** This discards the commit and all associated changes, returning your repository to the state before the commit.

## 2. Undoing Multiple Commits
If you need to undo multiple commits, simply change the number after `HEAD~`. For example, to undo the last 3 commits:
```bash
git reset --hard HEAD~3
```

**Warning:** Be cautious when using `--hard` as it will delete changes.

[Back to README](../README.md)
    