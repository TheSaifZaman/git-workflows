# Hands-On Tasks Guide: Git Collaboration

## Task 1: Clone a Public Repository, Create Branches, and Submit a Pull Request

### Step 1: Clone a Public Repository

1. Find a public repository on GitHub. For this example, we'll use a hypothetical repository: https://github.com/example/open-source-project.git

2. Clone the repository:
   ```bash
   git clone https://github.com/example/open-source-project.git
   cd open-source-project
   ```

### Step 2: Create a New Branch

1. Create and switch to a new branch:
   ```bash
   git checkout -b feature/add-readme-section
   ```

### Step 3: Make Changes

1. Open the README.md file and add a new section:
   ```markdown
   ## Contributing

   We welcome contributions! Please follow these steps:
   1. Fork the repository
   2. Create a feature branch
   3. Make your changes
   4. Submit a pull request
   ```

2. Save the file and commit your changes:
   ```bash
   git add README.md
   git commit -m "Add contributing section to README"
   ```

### Step 4: Push Changes and Create a Pull Request

1. Push your branch to your fork:
   ```bash
   git push origin feature/add-readme-section
   ```

2. Go to the original repository on GitHub and click "New Pull Request"

3. Select your branch and provide a description of your changes

4. Submit the pull request

## Task 2: Collaborate on a Pull Request

### For the Pull Request Creator:

1. After creating the pull request, wait for feedback

2. If changes are requested, make them in your local branch:
   ```bash
   git checkout feature/add-readme-section
   # Make the requested changes
   git add .
   git commit -m "Address feedback: clarify contribution steps"
   git push origin feature/add-readme-section
   ```

3. The pull request will automatically update

### For the Collaborator/Reviewer:

1. Go to the "Pull Requests" tab in the repository

2. Select the pull request to review

3. Click on "Files changed" to see the modifications

4. Add comments or suggestions by clicking the "+" icon next to specific lines

5. Submit your review:
   - "Comment" for general feedback
   - "Approve" if the changes look good
   - "Request changes" if modifications are needed

6. If you have write access and the changes are approved, you can merge the pull request

Remember to communicate clearly and respectfully throughout the process. Pull requests are not just about code; they're about collaboration and improving the project together.
