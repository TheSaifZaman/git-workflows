# **Advanced Git**

| **Topic**                       | **Command**                                      | **Description**                                                  |
|----------------------------------|-------------------------------------------------|------------------------------------------------------------------|
| **Advanced Branching**           | `git branch -d <branch-name>`                   | Delete a branch (safe, prevents deletion if not merged).         |
|                                  | `git branch -D <branch-name>`                   | Force delete a branch.                                           |
|                                  | `git checkout -b <branch-name> <commit>`        | Create a new branch from a specific commit.                      |
|                                  | `git cherry-pick <commit>`                      | Apply changes from a specific commit to the current branch.      |
|                                  | `git merge --no-ff <branch-name>`               | Merge with a new commit, no fast-forward.                        |
|                                  | `git merge --squash <branch-name>`              | Merge changes but combine them into a single commit.             |
|                                  | `git rebase -i <commit>`                        | Interactive rebase, allowing you to modify commit history.       |
| **Advanced Reset & Revert**      | `git reset --soft <commit>`                    | Reset the repository to a specific commit but keep changes staged. |
|                                  | `git reset --mixed <commit>`                   | Reset to a specific commit and unstage changes, but keep them in the working directory. |
|                                  | `git reset --hard <commit>`                    | Completely reset to a specific commit, discarding all changes.   |
|                                  | `git revert -n <commit>`                       | Revert a commit without automatically committing it.             |
|                                  | `git reflog`                                   | Show a log of all references, including detached HEADs.          |
| **Diffing & Comparing**          | `git diff --cached`                            | Show changes between the staging area and the latest commit.     |
|                                  | `git diff <branch1>..<branch2>`                | Show differences between two branches.                           |
|                                  | `git diff --stat`                              | Show changes with a summary of added/removed lines.              |
|                                  | `git diff --name-only`                         | Show which files have changed between commits or branches.       |
|                                  | `git diff --word-diff`                         | Show differences at the word level.                              |
| **Stashing & Applying**          | `git stash -u`                                 | Stash changes, including untracked files.                        |
|                                  | `git stash apply stash@{<index>}`              | Apply a specific stash.                                          |
|                                  | `git stash branch <branch-name>`               | Create a new branch and apply the most recent stash.             |
|                                  | `git stash drop`                               | Remove the most recent stash.                                    |
|                                  | `git stash list`                               | List all stashed changes.                                        |
| **Tagging**                      | `git tag -a <tag-name> -m "message"`           | Create an annotated tag with a message.                          |
|                                  | `git tag -d <tag-name>`                        | Delete a tag locally.                                            |
|                                  | `git push origin --tags`                       | Push all tags to the remote repository.                          |
|                                  | `git push origin :refs/tags/<tag-name>`        | Delete a tag from the remote repository.                         |
| **Working with Remotes**         | `git remote rm <remote-name>`                  | Remove a remote repository.                                      |
|                                  | `git remote rename <old-name> <new-name>`      | Rename a remote repository.                                      |
|                                  | `git fetch --prune`                            | Remove branches that no longer exist on the remote.              |
|                                  | `git pull --rebase`                            | Fetch changes and rebase the current branch.                     |
| **Rebasing**                     | `git rebase <upstream>`                        | Reapply commits on top of another branch.                        |
|                                  | `git rebase --continue`                        | Continue rebasing after resolving conflicts.                     |
|                                  | `git rebase --abort`                           | Abort the rebase process and return to the original state.       |
|                                  | `git rebase --skip`                            | Skip the current patch during a rebase.                          |
| **Squashing Commits**            | `git rebase -i HEAD~<n>`                       | Interactive rebase to squash the last `n` commits.               |
|                                  | `git commit --amend`                           | Modify the most recent commit (message or staged changes).       |
| **Cherry-Picking**               | `git cherry-pick <commit1> <commit2>`          | Apply multiple commits to the current branch.                    |
|                                  | `git cherry-pick --abort`                      | Abort the cherry-pick process.                                   |
| **Bisecting (Debugging)**        | `git bisect start`                             | Start a binary search to find a bug in the code.                 |
|                                  | `git bisect good <commit>`                    | Mark a commit as good (without the bug).                         |
|                                  | `git bisect bad <commit>`                     | Mark a commit as bad (with the bug).                             |
|                                  | `git bisect reset`                            | Exit the bisect process and return to the original branch.       |
| **Git Submodules**               | `git submodule add <repository-url>`           | Add a submodule to your repository.                              |
|                                  | `git submodule init`                           | Initialize the submodules.                                       |
|                                  | `git submodule update`                         | Update the submodules to the latest commit.                      |
|                                  | `git submodule deinit <path-to-submodule>`     | Deinitialize a submodule without removing its content.           |
| **Temporary Work**               | `git worktree add <path> <branch>`            | Add a working tree linked to a branch.                           |
|                                  | `git worktree prune`                           | Clean up unused worktree references.                             |
| **Ref & Log Manipulation**       | `git reflog expire --all --expire=now`         | Expire all reflog entries immediately.                           |
|                                  | `git gc --aggressive`                         | Clean up unnecessary files and optimize the local repository.    |
| **Managing Conflicts**           | `git mergetool`                                | Use a merge tool to resolve conflicts.                           |
|                                  | `git rerere`                                  | Automatically reuse conflict resolutions.                        |


### **Advanced Workflows & Collaboration**

| **Topic**                       | **Command**                                      | **Description**                                                  |
|----------------------------------|-------------------------------------------------|------------------------------------------------------------------|
| **Rewriting History**            | `git filter-branch --tree-filter <command>`      | Reapply a command to the entire commit history (e.g., to remove a file). |
|                                  | `git rebase -i --autosquash HEAD~<n>`           | Automatically squash and re-order commits using fixup and squash commands. |
|                                  | `git commit --fixup <commit>`                   | Create a fixup commit for later autosquashing during rebase.     |
|                                  | `git rebase -i --root`                          | Rebase all commits from the root of the repository.              |
| **Blame & Tracking Changes**     | `git blame -L <start>,<end> <file>`             | Blame only specific lines in a file.                             |
|                                  | `git shortlog -s -n`                            | View a summary of commits grouped by author.                     |
| **Force Pushing & Recovery**     | `git push --force-with-lease`                   | Safely force push only if no one else has pushed to the branch.  |
|                                  | `git reflog <branch>`                           | View the log of all actions (e.g., commits, rebases, resets) in a branch, useful for recovering after a bad rebase or reset. |
| **Subtree Merging**              | `git subtree add --prefix=<directory> <repository> <branch>` | Add another repository into a subdirectory of your repository (alternative to submodules). |
|                                  | `git subtree merge --prefix=<directory> <repository> <branch>` | Merge changes from a subtree repository.                        |
| **Partial Commits**              | `git add -p`                                    | Interactively add portions of a file to the staging area.        |
|                                  | `git reset -p`                                  | Interactively unstage portions of a file.                       |

### **Optimization for Large Repositories**

| **Topic**                       | **Command**                                      | **Description**                                                  |
|----------------------------------|-------------------------------------------------|------------------------------------------------------------------|
| **Shallow Clones**               | `git clone --depth <n> <repo>`                  | Clone only the most recent `n` commits (useful for large repositories). |
|                                  | `git fetch --depth <n>`                         | Convert an existing clone into a shallow clone.                  |
| **Sparse Checkout**              | `git sparse-checkout init`                      | Enable sparse checkout, useful for working with only parts of large repositories. |
|                                  | `git sparse-checkout set <file/dir>`            | Specify which files or directories to include in the sparse checkout. |
| **Optimize Repository**          | `git gc --prune=now --aggressive`               | Perform aggressive garbage collection to optimize repository size. |

### **Security & Access Management**

| **Topic**                       | **Command**                                      | **Description**                                                  |
|----------------------------------|-------------------------------------------------|------------------------------------------------------------------|
| **Signing Commits**              | `git config --global user.signingkey <gpg-key>`  | Configure GPG key to sign commits.                              |
|                                  | `git commit -S -m "message"`                    | Create a signed commit.                                          |
|                                  | `git verify-commit <commit>`                    | Verify the signature of a specific commit.                      |
| **Managing Credentials**         | `git config --global credential.helper cache`    | Cache credentials for a short period (avoids repeatedly entering credentials). |
|                                  | `git config --global credential.helper store`    | Save credentials to disk (less secure).                         |

### **Advanced Hooks**

| **Topic**                       | **Command**                                      | **Description**                                                  |
|----------------------------------|-------------------------------------------------|------------------------------------------------------------------|
| **Pre-commit Hooks**             | `.git/hooks/pre-commit`                         | Script that runs before each commit (e.g., to run tests, linting). |
| **Post-merge Hook**              | `.git/hooks/post-merge`                         | Script that runs after a merge, useful for syncing dependencies or running migrations. |

### **Testing & Continuous Integration**

| **Topic**                       | **Command**                                      | **Description**                                                  |
|----------------------------------|-------------------------------------------------|------------------------------------------------------------------|
| **Run Tests on Commits**         | `git bisect run <script>`                       | Automatically test each commit during bisecting.                 |
|                                  | `git hooks run`                                 | Run custom scripts on various Git actions (like pre-push, pre-commit). |

### **Handling Large Files**

| **Topic**                       | **Command**                                      | **Description**                                                  |
|----------------------------------|-------------------------------------------------|------------------------------------------------------------------|
| **Git LFS (Large File Support)** | `git lfs install`                               | Initialize Git LFS in a repository to track large files.         |
|                                  | `git lfs track <file>`                          | Track specific large files (e.g., binaries).                     |
|                                  | `git lfs push --all origin`                     | Push all LFS objects to the remote repository.                   |

### **Customization**

| **Topic**                       | **Command**                                      | **Description**                                                  |
|----------------------------------|-------------------------------------------------|------------------------------------------------------------------|
| **Aliases**                      | `git config --global alias.<alias-name> <command>` | Create a custom Git alias (e.g., `git config --global alias.co checkout`). |
| **Color Customization**          | `git config --global color.ui auto`             | Automatically enable colored output in Git commands.             |

These advanced topics will help with optimizing workflows, debugging, and managing larger repositories or complex version control scenarios. The addition of hooks, large file management, security measures, and interactive rebase commands can elevate your Git usage further.