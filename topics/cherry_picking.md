
# Git Cherry-Picking

## 1. What is Cherry-Picking?
Cherry-picking allows you to apply specific commits from one branch to another without merging the entire branch.

## 2. Cherry-Pick a Commit
To apply a specific commit from another branch, use:
```bash
git cherry-pick <commit-hash>
```

**Explanation:** Replace `<commit-hash>` with the hash of the commit you want to apply. Git will apply the changes made in that commit to the current branch.

## 3. Resolving Conflicts in Cherry-Picking
If the commit you are cherry-picking causes conflicts, Git will stop and ask you to resolve them:
```bash
git status
```

Edit the conflicting files to resolve the issues, then continue the cherry-pick with:
```bash
git add <filename>
git cherry-pick --continue
```

If you want to abort the cherry-pick, use:
```bash
git cherry-pick --abort
```

**Explanation:** This aborts the cherry-pick and restores your branch to its previous state.

## 4. Cherry-Picking Multiple Commits
To cherry-pick multiple commits at once, provide a range of commit hashes:
```bash
git cherry-pick <commit-hash1> <commit-hash2>
```

Or use a range:
```bash
git cherry-pick <commit-hash1>^..<commit-hash2>
```

**Explanation:** This applies all commits between `<commit-hash1>` and `<commit-hash2>` (inclusive).

## 5. Cherry-Pick from Another Branch
You can also cherry-pick commits from another branch by specifying the branch name and commit hash:
```bash
git cherry-pick <branch-name> <commit-hash>
```

[Back to README](../README.md)
    