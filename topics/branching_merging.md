
# Git Branching and Merging

## 1. Create a New Branch
To create a new branch:
```bash
git checkout -b <branch-name>
```

**Explanation:** This command creates and switches to a new branch. Use meaningful names for branch names, such as `feature/add-login`, `bugfix/fix-typo`, etc.

## 2. Merging Branches
Once you've made changes on a branch and are ready to merge it back into the main branch, use:
```bash
git checkout main
git merge <branch-name>
```

**Explanation:** Make sure to switch back to the main branch before merging. Merging incorporates the changes from `<branch-name>` into the main branch.

## 3. Fast-Forward Merge
If the main branch hasn’t diverged since you created the feature branch, Git will perform a “fast-forward” merge, moving the pointer of the main branch forward. This occurs automatically unless you specify the `--no-ff` flag:

```bash
git merge --no-ff <branch-name>
```

**Explanation:** This forces Git to create a merge commit even if a fast-forward merge is possible, preserving a clearer history.

## 4. Three-Way Merge
When the main branch has changed since the feature branch was created, Git will perform a three-way merge:
```bash
git merge <branch-name>
```

Git automatically merges changes, but if there are conflicts, you’ll need to resolve them manually.

## 5. Resolving Merge Conflicts
When a merge conflict occurs, Git will mark the conflicting areas in the file. To see which files are in conflict:
```bash
git status
```

Edit the conflicting files to resolve conflicts, then mark them as resolved:
```bash
git add <filename>
git commit
```

## 6. Merging Best Practices
- **Commit frequently**: Keep your branch small and commit often to avoid difficult merges.
- **Pull frequently**: Regularly pull updates from the main branch to minimize conflicts when merging later.

[Back to README](../README.md)
    