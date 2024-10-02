# Squashing/Fixing commit history

To collapse (squash) some recent commits into one, even though you've already pushed them, you can follow these steps. This process involves interactive rebasing and force-pushing, which rewrites the commit history. Since you've already pushed the commits, make sure you're aware of potential issues for collaborators who might have already pulled your branch.

Here are the steps:

## Step 1: Ensure your working directory is clean

Before starting, make sure there are no uncommitted changes. You can check this with:

```bash
git status
```

## Step 2: Start an interactive rebase

*For example*, this allows you to rewrite the last **two commits**. Run the following command: 

```bash
git rebase -i HEAD~2
```

Otherwise, do a 
```bash
git log
```
in your branch and note the `<commit_hash>` from which you want to do the rebase and then type
```bash
git rebase -i <commit_hash>
```


## Step 3: Modify the rebase instruction

In the editor that opens, you'll see something like:

```bash
pick commit_hash Commit message 1
pick commit_hash Commit message 2
```

Change the second `pick` to `fixup` (or `squash`, but `fixup` is for cleaner commit messages):

```bash
pick commit_hash Commit message 1
fixup commit_hash Commit message 2
```

- `pick` means to keep the commit.
- `fixup` squashes the second commit into the first and discards its commit message.

## Step 4: Save and close the editor

After making the change, save and close the editor. Git will squash the two commits into one.

## Step 5: Force-push the changes

Since you've already pushed the original two commits, you will need to force-push the squashed commit to overwrite the previous history:

```bash
git push --force
```
This will overwrite the history in the remote repository with your new, squashed commit.

**Important Notes:**
- Collaborators: If others have already pulled the original two commits, they will need to be aware that you've rewritten the history. They'll have to reset their branches to the updated history, which might cause conflicts or confusion.
- Force-push: Use force-push carefully, especially when others are working on the same branch.



[Back to Main README](../README.md)
