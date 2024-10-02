# Install Git Bash Completion

To make working with Git easier, you can add Git bash completion, which suggests Git commands and branches as you type.

1. **Download Git Completion Script:**

    ```bash
    curl -o ~/.git-completion.bash https://raw.githubusercontent.com/git/git/master/contrib/completion/git-completion.bash
    ```

2. **Edit `.bashrc` to Include Git Completion:**

    ```bash
    nano ~/.bashrc
    ```

    At the bottom of the file, add:

    ```bash
    if [ -f ~/.git-completion.bash ]; then
      . ~/.git-completion.bash
    fi
    ```

3. **Reload the Terminal:**

    ```bash
    source ~/.bashrc
    ```

Now, Git command autocompletion should work in your terminal, making it easier to work with branches and Git commands.

[Back to Main README](../README.md)
