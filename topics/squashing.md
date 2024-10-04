
# Git Squashing

## 1. What is Squashing?
Squashing combines multiple commits into a single commit, typically to clean up the commit history before merging to the main branch.

## 2. Start an Interactive Rebase
To squash commits, start an interactive rebase on the branch you want to clean up:
```bash
git rebase -i <commit-hash>
```

**Explanation:** Replace `<commit-hash>` with the hash of the commit before the first commit you want to squash.

## 3. Mark Commits for Squashing
In the text editor that opens, change `pick` to `squash` (or `s`) for the commits you want to squash into the previous one:

```plaintext
pick abc123 First commit
squash def456 Second commit
squash ghi789 Third commit
```

**Explanation:** The `squash` command combines the commit with the one before it.

## 4. Edit Commit Message
Git will prompt you to edit the commit message for the squashed commits. Combine or rewrite the commit messages as appropriate.

## 5. Complete the Rebase
Once you’ve made your changes, save and close the editor. Git will apply the changes and complete the rebase. If conflicts arise, resolve them as usual and continue the rebase with:
```bash
git rebase --continue
```

## 6. Push the Squashed Changes
If you've already pushed the commits, you'll need to force-push the squashed commits to update the branch:
```bash
git push --force-with-lease
```

**Explanation:** This ensures that no one else has made changes to the branch while you were squashing commits.

[Back to README](../README.md)
    