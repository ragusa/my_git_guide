
# Git Rebase vs. Git Merge

## 1. Merging a Branch
Merging integrates the feature branch into the main branch:
```bash
git checkout main
git merge <feature-branch>
```

**Explanation:** This method creates a new "merge commit" and preserves the history of both branches.

## 2. Rebasing a Branch
Rebasing rewrites the commit history of your feature branch to make it appear as if you made changes starting from the tip of the main branch:

```bash
git checkout <feature-branch>
git rebase main
```

**Explanation:** This moves your feature branch's commits on top of the latest commit in the `main` branch.

## 3. Merge vs. Rebase: When to Use
- **Use `merge`** if you want to preserve the full context of your branch, including the point at which the feature was branched off.
- **Use `rebase`** if you want a linear history with no diverging branches.

## 4. Handling Conflicts in Rebase
During rebasing, conflicts can arise. Git will stop the process and allow you to resolve conflicts one by one. To continue rebasing after resolving a conflict:
```bash
git add <filename>
git rebase --continue
```

If you want to cancel the rebase process, run:
```bash
git rebase --abort
```

## 5. Interactive Rebase
You can also rewrite commit history using interactive rebase:
```bash
git rebase -i <commit-hash>
```
This allows you to squash, edit, or reorder commits.

[Back to README](../README.md)
    