
# Undoing a Commit That Was Pushed

## 1. Reverting a Commit
If you have already pushed a commit to a remote repository, you should not use `git reset` because it rewrites history, which can cause issues for collaborators. Instead, use `git revert`.

### 1.1 Revert a Single Commit
To revert a commit, use:
```bash
git revert <commit-hash>
```

**Explanation:** This creates a new commit that undoes the changes introduced by the specified commit, without altering the commit history.

### 1.2 Revert Multiple Commits
To revert a range of commits, you can use:
```bash
git revert <commit-hash1>..<commit-hash2>
```

**Explanation:** This undoes all changes introduced by the commits between `<commit-hash1>` and `<commit-hash2>`. Each commit will be reverted individually.

### 1.3 Reverting a Merge Commit
To revert a merge commit, use:
```bash
git revert -m 1 <merge-commit-hash>
```

**Explanation:** The `-m 1` flag specifies that Git should revert the first parent of the merge, which is typically the branch you merged into.

## 2. Reset and Force Push (Last Resort)
If you must rewrite history and the commit was already pushed, you can use `git reset` followed by a force push. This should only be done with caution and when you're sure no one else is affected by the changes.

```bash
git reset --hard <commit-hash>
git push --force-with-lease
```

**Explanation:** This rewrites history on the remote branch. Use `--force-with-lease` to ensure you don’t overwrite any changes made by others.

[Back to README](../README.md)
    