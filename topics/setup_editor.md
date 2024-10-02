# Setting Up a Git Editor

## Step 1: Choose Your Editor

Here are some common editors and how to set them up for Git:

### 1. **VS Code**:
```bash
git config --global core.editor "code --wait"
```

### 2. Vim (default for many Linux/Mac systems):

```bash
git config --global core.editor "vim"
```

### 3. Nano:

```bash
git config --global core.editor "nano"
```

### 4. Sublime Text:

```bash
git config --global core.editor "subl -n -w"
```

### 5. Notepad++ (on Windows):

```bash
git config --global core.editor "'C:/Program Files/Notepad++/notepad++.exe' -multiInst -notabbar -nosession -noPlugin"
```

### 5 .Notepad (Windows):
```bash
git config --global core.editor "notepad"
```


## Step 2: Verify the Editor
After setting the editor, you can verify it by running:

```bash
git config --global core.editor
```
This will show the currently configured editor for Git.

## Step 3: Test the Editor
You can test if the editor is working correctly by running the following command, which will trigger Git to open the editor:

```bash
git commit --amend
```

If the editor opens as expected, you're all set for the rebase process.

[Back to Main README](../README.md)
