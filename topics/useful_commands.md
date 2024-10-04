
# Most Useful Git Commands

Here is a table of some of the most commonly used Git commands with brief explanations.

| Command                                | Explanation                                                     |
|----------------------------------------|-----------------------------------------------------------------|
| `git init`                             | Initializes a new Git repository in the current directory.       |
| `git clone <repo-url>`                 | Clones an existing repository from a URL to your local machine.  |
| `git status`                           | Shows the status of your working directory and staging area.     |
| `git add <file>`                       | Stages the specified file for the next commit.                   |
| `git commit -m "message"`              | Commits the staged changes with a descriptive message.           |
| `git log`                              | Displays the commit history of the current branch.               |
| `git branch`                           | Lists all branches in the repository.                            |
| `git checkout <branch>`                | Switches to the specified branch.                                |
| `git checkout -b <new-branch>`         | Creates a new branch and switches to it.                         |
| `git merge <branch>`                   | Merges the specified branch into the current branch.             |
| `git pull`                             | Fetches changes from the remote and merges them into your local branch. |
| `git push`                             | Pushes committed changes to the remote repository.               |
| `git remote -v`                        | Lists all remotes associated with the repository.                |
| `git fetch`                            | Downloads objects and refs from another repository.              |
| `git reset --soft HEAD~1`              | Undoes the last commit but keeps changes staged.                 |
| `git revert <commit-hash>`             | Creates a new commit that reverses the changes of a previous commit. |
| `git stash`                            | Temporarily saves uncommitted changes for later use.             |
| `git stash apply`                      | Reapplies stashed changes to the working directory.              |
| `git tag <tag-name>`                   | Creates a new tag for marking specific points in history.        |
| `git rebase <branch>`                  | Reapplies commits on top of another base branch.                 |
| `git cherry-pick <commit-hash>`        | Applies a specific commit from another branch to the current branch. |
| `git bisect start`                     | Starts the process of binary searching through commits to find a bug. |
| `git log --oneline`                    | Shows a simplified one-line log of commits.                      |

**Note:** This is not an exhaustive list but includes some of the most frequently used Git commands.
