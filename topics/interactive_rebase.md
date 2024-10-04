
# Git Interactive Rebase

## 1. Starting an Interactive Rebase
To start an interactive rebase, run:
```bash
git rebase -i <commit-hash>
```

**Explanation:** Replace `<commit-hash>` with the hash of the commit you want to rebase onto. This opens a text editor listing all the commits since that commit.

## 2. Squash Commits
To combine a commit with the one before it, change `pick` to `squash` in front of the commits you want to squash:

```plaintext
pick abc123 First commit
squash def456 Second commit
```

**Explanation:** This combines the second commit (`def456`) with the first (`abc123`). After saving the file, Git will prompt you to edit the commit message.

## 3. Edit Commit Messages
You can also change commit messages during interactive rebase by using `reword` instead of `pick`.

```plaintext
pick abc123 First commit
reword def456 Update commit message
```

**Explanation:** This allows you to change the commit message of the specified commit.

## 4. Dropping Commits
To remove a commit entirely, change `pick` to `drop`:

```plaintext
pick abc123 First commit
drop def456 Remove this commit
```

**Explanation:** This deletes the commit from the history.

## 5. Reordering Commits
You can also change the order of commits during an interactive rebase by moving the lines up or down in the editor.

## 6. Finalizing the Rebase
Once you’ve made your changes, save and close the editor. Git will apply your changes. If there are conflicts, resolve them as usual and continue the rebase:

```bash
git rebase --continue
```

[Back to README](../README.md)
    