
# Handling Merge Conflicts

## 1. Identify Merge Conflicts
When you merge two branches with conflicting changes, Git will pause and ask you to resolve the conflicts manually. To see the conflicting files:
```bash
git status
```

Files with conflicts will be marked as "both modified".

## 2. Open and Resolve Conflicts
Git marks the conflicting lines in the file like this:

```plaintext
<<<<<<< HEAD
Your changes
=======
Their changes
>>>>>>> branch-name
```

- Remove the conflict markers (`<<<<<<<`, `=======`, `>>>>>>>`).
- Choose which changes to keep or manually combine them.
- Save the file after resolving conflicts.

## 3. Mark the Conflict as Resolved
After resolving the conflicts, mark the file as resolved by staging it:
```bash
git add <filename>
```

If all conflicts are resolved, complete the merge with:
```bash
git commit
```

## 4. Merge Tool
Git also provides merge tools that help you resolve conflicts. To use Git’s built-in merge tool:
```bash
git mergetool
```

**Explanation:** This opens a visual tool to guide you through resolving conflicts.

## 5. Abort a Merge
If you decide not to complete the merge, you can abort it and return to the previous state:
```bash
git merge --abort
```

**Explanation:** This undoes the merge and reverts to the state before the merge was attempted.

[Back to README](../README.md)
    