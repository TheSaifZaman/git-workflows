# **Comprehensive Git cheat sheet organized by topic inside the table**

---

| **Topic**                   | **Command**                            | **Description**                                                  |
|-----------------------------|----------------------------------------|------------------------------------------------------------------|
| **Repository Management**    | `git init`                             | Initialize a new Git repository in the current directory.        |
|                             | `git clone <repository-url>`           | Clone a repository into a new directory.                         |
|                             | `git remote -v`                        | Show remote repository URLs.                                     |
|                             | `git remote add <name> <url>`          | Add a new remote repository.                                     |
| **Status & Information**     | `git status`                           | Show the status of changes in the working directory and staging area. |
|                             | `git log`                              | Show the commit history.                                         |
|                             | `git log --oneline`                    | Show a simplified one-line commit history.                       |
|                             | `git show <tag/commit>`                | Show details of a tag or commit.                                 |
|                             | `git blame <file>`                     | Show who modified each line of a file.                           |
| **Adding & Committing**      | `git add <file>`                       | Add a file to the staging area.                                  |
|                             | `git add .`                            | Add all modified files to the staging area.                      |
|                             | `git commit -m "message"`              | Commit changes with a message.                                   |
|                             | `git commit -a -m "message"`           | Stage and commit all changes in one step (excluding untracked files). |
| **Branching & Merging**      | `git branch`                           | List all branches in the repository.                             |
|                             | `git branch <branch-name>`             | Create a new branch.                                             |
|                             | `git checkout <branch-name>`           | Switch to the specified branch.                                  |
|                             | `git checkout -b <branch-name>`        | Create and switch to a new branch in one step.                   |
|                             | `git merge <branch-name>`              | Merge the specified branch into the current branch.              |
| **Stashing & Cleaning**      | `git stash`                            | Save the current work in progress for later use.                 |
|                             | `git stash pop`                        | Reapply the most recent stashed changes and remove them from the stash list. |
|                             | `git clean -f`                         | Remove untracked files from the working directory.               |
| **Pulling & Pushing**        | `git fetch`                            | Download objects and refs from another repository.               |
|                             | `git pull`                             | Fetch and merge changes from the remote repository to the current branch. |
|                             | `git push`                             | Push the current branch to the remote repository.                |
|                             | `git push origin <branch-name>`        | Push a specific branch to the remote repository.                 |
| **Tagging & Releases**       | `git tag <tag-name>`                  | Create a new tag for the current commit.                         |
|                             | `git show <tag>`                       | Show details of a tag or commit.                                 |
| **Resetting & Reverting**    | `git reset <file>`                     | Unstage a file without modifying it.                             |
|                             | `git reset --hard <commit>`            | Reset the repository to a specific commit, discarding all changes. |
|                             | `git revert <commit>`                  | Create a new commit that undoes changes made by a specific commit. |
| **Rebasing & Cherry-picking**| `git rebase <branch>`                 | Reapply commits on top of another base branch.                   |
|                             | `git cherry-pick <commit>`             | Apply the changes from a specific commit to the current branch.  |
| **Configuration**            | `git config --global user.name "name"` | Set the global Git username.                                     |
|                             | `git config --global user.email "email"`| Set the global Git email.                                        |
| **Advanced Tools**           | `git bisect start`                     | Start a binary search to find the commit that introduced a bug.  |

---

This table groups the commands by topic, making it easier to find the relevant Git commands for a specific task. Let me know if you'd like to dive deeper into any specific topic!