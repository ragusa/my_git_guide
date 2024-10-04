
# Git Hooks

## 1. What Are Git Hooks?
Git hooks are scripts that run automatically at certain points in the Git lifecycle, such as before committing or after merging.

## 2. Setting Up a Hook
Hooks are stored in the `.git/hooks/` directory of your repository. To create a hook, simply add a script file to this folder and make it executable.

For example, to create a pre-commit hook:
```bash
cd .git/hooks/
nano pre-commit
```

Add your custom script inside the file, then make it executable:
```bash
chmod +x pre-commit
```

## 3. Example: Pre-Commit Hook for Code Linting
This hook runs a linting tool like `eslint` before every commit:
```bash
#!/bin/sh
eslint .
if [ $? -ne 0 ]; then
  echo "Linting failed. Commit aborted."
  exit 1
fi
```

## 4. Built-in Hooks
Git comes with several pre-defined hooks, including:

- **pre-commit**: Runs before a commit is made.
- **post-merge**: Runs after a merge has completed.
- **pre-push**: Runs before pushing changes to a remote.

## 5. Managing Hooks Globally
You can create hooks for all repositories by placing them in a global directory. Set the global hooks directory with this command:
```bash
git config --global core.hooksPath /path/to/hooks
```

**Explanation:** This configures a default hooks directory for all Git projects.

[Back to README](../README.md)
    