
# Git Large File Storage (LFS)

## 1. What is Git LFS?
Git LFS is a Git extension for managing large binary files in your repository. Instead of storing the entire file, Git LFS stores a pointer and keeps the actual file in a separate location.

## 2. Install Git LFS
To use Git LFS, you need to install it first:
```bash
git lfs install
```

**Explanation:** This sets up Git LFS in your Git configuration.

## 3. Track Large Files
To track a file with Git LFS, use the `git lfs track` command:
```bash
git lfs track "*.psd"
```

**Explanation:** This tells Git to track all files with the `.psd` extension (or any other large files).

## 4. Committing Large Files
Once a file is being tracked by Git LFS, commit it as usual:
```bash
git add <large-file>
git commit -m "Add large file with LFS"
```

**Explanation:** Git LFS will store a pointer to the file in your repository and the actual file in LFS storage.

## 5. Push Changes
To push your LFS-tracked files, push your changes as usual:
```bash
git push origin <branch-name>
```

**Explanation:** The large files will be uploaded to LFS storage, while the rest of your changes are pushed to the Git repository.

## 6. Fetching LFS Files
When you clone or pull a repository with LFS-tracked files, Git will download the pointers first. To download the actual files:
```bash
git lfs pull
```

**Explanation:** This fetches the large files from LFS storage.

[Back to README](../README.md)
    