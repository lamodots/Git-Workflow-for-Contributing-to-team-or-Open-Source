# Git Workflow for Contributing to Open Source

![Profile Picture](https://avatars.githubusercontent.com/lamodots) <!-- Replace with your actual photo URL if it's hosted somewhere else -->

### About Me

👋 Hey there! I’m Wisdom Lamodot, Full-stack Software Engineer.

I build things—scalable web apps, mobile solutions, and products that solve real problems. I am obsessed with tech that doesn’t just work—it transforms how people live and businesses grow. By day, I’m a full-stack engineer who loves turning ideas into code. By night, I’m a startup enthusiast figuring out how to make technology meaningful (and profitable!).  
[Connect with me on LinkedIn](https://www.linkedin.com/in/lamodot/)

---

This guide explains how to effectively contribute to an open-source/team repository with a structured Git workflow. The repository consists of three branches: `main`, `release`, and `development`. The workflow involves creating feature branches for tasks and raising pull requests (PRs) for changes.

---

## Table of Contents
1. [Cloning the Repository and Setting Up](#cloning-the-repository-and-setting-up)
2. [Starting a New Task](#starting-a-new-task)
3. [Working on a Task](#working-on-a-task)
4. [Raising a Pull Request](#raising-a-pull-request)
5. [Command Flow Summary](#command-flow-summary)
6. [Guide for Maintainers](#guide-for-maintainers)

---

## Cloning the Repository and Setting Up

To start contributing, the first step is to clone the repository and set up your local environment.

1. **Clone the Repository**  
   Replace `<repository-url>` with the URL of the repository you are contributing to:
   ```bash
   git clone <repository-url>
   cd <repository-folder>
   ```

2. **Switch to the `development` Branch**  
   Since the code is on the `development` branch, check it out:
   ```bash
   git checkout development
   ```

---

## Starting a New Task

When you start a new task, follow these steps:

1. **Pull the Latest Changes**  
   Before branching out for a new task, ensure your local `development` branch is up-to-date:
   ```bash
   git checkout development
   git pull origin development
   ```

2. **Create a New Branch**  
   Create a branch for the new task with a descriptive name. For example, if your task is to add an "About Page":
   ```bash
   git checkout -b about-page
   ```

---

## Working on a Task

Once you have created your branch, follow these steps to work on the task:

1. **Make Changes**  
   Perform the necessary changes in the codebase.

2. **Stage and Commit Changes**  
   After making changes, stage and commit them:
   ```bash
   git add .
   git commit -m "Add About Page feature"
   ```

3. **Push the Branch**  
   Push the branch to the remote repository:
   ```bash
   git push origin about-page
   ```

---

## Raising a Pull Request

After pushing your branch, follow these steps to raise a pull request (PR):

1. Go to the repository on GitHub (or the platform hosting the repo).  
2. You will see an option to "Compare & Pull Request" for your branch. Click on it.  
3. Ensure the base branch is `development` (or the branch you want to merge into).  
4. Add a **title** and **description** for your PR to explain the changes.  
5. Assign reviewers, labels, or any other requirements set by the project.  
6. Submit the PR for review.  

---

## Command Flow Summary

For quick reference, here’s the entire process in a concise command flow:

### Cloning and Setting Up
```bash
git clone <repository-url>
cd <repository-folder>
git checkout development
```

### Starting a New Task
```bash
git pull origin development
git checkout -b <new-branch-name> # Replace <new-branch-name> with your task name
```

### Working on a Task
```bash
# Make your changes
git add .
git commit -m "Describe your changes"
git push origin <new-branch-name> # Replace <new-branch-name> with your branch name
```

### Raising a Pull Request
1. Go to the repository on GitHub.
2. Click on "Compare & Pull Request."
3. Fill in the details and submit the PR.

---

## Guide for Maintainers

This section explains the step-by-step process for maintainers to review and merge accepted contributions. It also describes how the code progresses from `development` to `release` and eventually to `main`.

### 1. Reviewing a Pull Request
1. **Check the Pull Request (PR) Details**  
   - Read the title and description of the PR to understand the changes.
   - Ensure the PR is targeted to the correct branch (e.g., `development`).

2. **Review the Code**  
   - Navigate to the "Files changed" tab in the PR.
   - Review the code changes for correctness, readability, and conformity to the project's coding standards.
   - Suggest improvements or request changes if required.

3. **Run Tests Locally or in CI**  
   - Ensure all automated tests pass.
   - If applicable, pull the contributor's branch locally and test the feature to verify its functionality:
   ```bash
   git fetch origin <contributor-branch-name>
   git checkout <contributor-branch-name>
   ```

4. **Approve or Request Changes**  
   - If the changes are satisfactory, approve the PR.
   - If further modifications are needed, request changes and provide clear feedback.

---

### 2. Merging Accepted Pull Requests
1. **Merge into `development`**  
   - Once a PR is approved, merge it into the `development` branch using the "Squash and Merge" or "Rebase and Merge" option to maintain a clean history.

2. **Delete the Feature Branch**  
   - After merging, delete the contributor's feature branch to keep the repository organized.

---

### 3. Progressing Code to `release`
1. **Test in the `development` Branch**  
   - Before promoting code to the `release` branch, thoroughly test the `development` branch for bugs or issues.

2. **Merge into `release`**  
   - Once the `development` code is stable and ready for release, merge it into the `release` branch:
   ```bash
   git checkout release
   git merge development
   git push origin release
   ```

3. **Tag a Release**  
   - Create a versioned tag for the new release:
   ```bash
   git tag -a vX.Y.Z -m "Release version X.Y.Z"
   git push origin vX.Y.Z
   ```

---

### 4. Deploying to `main`
1. **Promote the Code to `main`**  
   - After the code in the `release` branch has been tested and validated, merge it into the `main` branch:
   ```bash
   git checkout main
   git merge release
   git push origin main
   ```

2. **Deploy the Latest Code**  
   - Deploy the latest code from the `main` branch to production.

---

### Summary of the Branch Workflow
1. Contributors create feature branches from `development` and raise PRs.
2. PRs are reviewed and merged into `development`.
3. `development` is tested and merged into `release` for staging.
4. After final testing, `release` is merged into `main` for production.

By following this process, you ensure high-quality contributions and a stable release cycle.

---