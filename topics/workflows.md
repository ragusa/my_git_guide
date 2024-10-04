
# Collaborative Git Workflows

## 1. Git Flow

### 1.1 Create a New Feature Branch
All new features should be developed on their own branch, branched off from `develop`:
```bash
git checkout develop
git checkout -b feature/<feature-name>
```

### 1.2 Merge Feature Branch Back to Develop
Once the feature is complete, merge it back into the `develop` branch:
```bash
git checkout develop
git merge feature/<feature-name>
```

### 1.3 Release Branches
When you’re ready to create a release, create a release branch from `develop`:
```bash
git checkout -b release/<version>
```

After final testing, merge the release branch into both `develop` and `main`:
```bash
git checkout develop
git merge release/<version>
git checkout main
git merge release/<version>
```

## 2. GitHub Flow

### 2.1 Always Work on a Branch
In GitHub Flow, always create a feature branch for any change:
```bash
git checkout -b feature/<feature-name>
```

### 2.2 Open a Pull Request
When your feature is ready, push the branch to GitHub and open a pull request. After it’s reviewed and approved, merge it into `main`.

## 3. Trunk-Based Development

### 3.1 Continuous Integration
Trunk-Based Development emphasizes keeping the main branch (`main` or `master`) ready to release at any time. Developers should commit small, frequent changes to the trunk:
```bash
git checkout main
git pull origin main
git checkout -b small-change-branch
```

Merge changes as soon as they are ready, and avoid long-lived feature branches.

[Back to README](../README.md)
    