# Hands-on Script: Git Basics Practice

This script will guide you through practicing Git commits, branching, and merging. Follow these steps to gain practical experience with Git workflows.

## Setup

1. Create a new directory for your practice repository:
   ```bash
   mkdir git-practice
   cd git-practice
   ```

2. Initialize a new Git repository:
   ```bash
   git init
   ```

3. Create a simple README file:
   ```bash
   echo "# Git Practice Repository" > README.md
   ```

## Practice Commits

1. Stage and commit the README file:
   ```bash
   git add README.md
   git commit -m "Initial commit: Add README"
   ```

2. Create a new file and make changes to README:
   ```bash
   echo "print('Hello, Git!')" > hello.py
   echo "This repository contains Python scripts." >> README.md
   ```

3. Stage and commit these changes:
   ```bash
   git add .
   git commit -m "Add hello.py and update README"
   ```

4. View your commit history:
   ```bash
   git log --oneline
   ```

## Practice Branching

1. Create and switch to a new branch:
   ```bash
   git checkout -b feature-goodbye
   ```

2. Create a new file in this branch:
   ```bash
   echo "print('Goodbye, Git!')" > goodbye.py
   ```

3. Stage and commit the new file:
   ```bash
   git add goodbye.py
   git commit -m "Add goodbye.py"
   ```

4. Switch back to the main branch:
   ```bash
   git checkout main
   ```

5. Create another branch and make changes:
   ```bash
   git checkout -b update-readme
   echo "## Scripts" >> README.md
   echo "- hello.py: Prints a greeting" >> README.md
   git add README.md
   git commit -m "Update README with script descriptions"
   ```

## Practice Merging

1. Merge the `feature-goodbye` branch into `main`:
   ```bash
   git checkout main
   git merge feature-goodbye
   ```

2. Try to merge the `update-readme` branch (this will cause a conflict):
   ```bash
   git merge update-readme
   ```

3. Resolve the conflict manually by editing the README.md file.

4. Stage the resolved file and complete the merge:
   ```bash
   git add README.md
   git commit -m "Merge update-readme, resolve conflicts"
   ```

5. View the final commit history:
   ```bash
   git log --oneline --graph --all
   ```

## Bonus: Practice Rebasing

1. Create a new branch from an earlier commit:
   ```bash
   git checkout -b feature-rebase HEAD~2
   ```

2. Make some changes and commit:
   ```bash
   echo "print('Learning Git!')" > learn.py
   git add learn.py
   git commit -m "Add learn.py"
   ```

3. Rebase this branch onto the latest main:
   ```bash
   git rebase main
   ```

4. Switch to main and merge the rebased branch:
   ```bash
   git checkout main
   git merge feature-rebase
   ```

Congratulations! You've now practiced the fundamental Git operations of committing, branching, merging, and even rebasing.
