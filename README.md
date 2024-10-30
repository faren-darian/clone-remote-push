# How to Clone a GitHub Repository with Terminal
This guide will walk you through the process of cloning a repository from one GitHub account using HTTPS, and then pushing it to another GitHub account using an SSH key.

## Prerequisites

- Two GitHub accounts (source and destination)
- SSH key set up for the destination GitHub account

## Step-by-Step Guide

### 1. Clone the Repository

First, clone the repository using HTTPS. This method requires the username and password of the source GitHub account.

```bash
git clone https://github.com/source-username/repository-name.git
```

Replace `https://github.com/source-username/repository-name.git` with the actual URL of the repository you want to clone.

### 2. Navigate to the Cloned Repository

Change your current directory to the newly cloned repository:

```bash
cd repository-name
```

Replace `repository-name` with the actual name of the cloned repository.
You can find the repository name from the cloned respository in step 1: ```git clone https://github.com/source-username/repository-name.git```

### 3. (Optional) Start Fresh

If you've previously cloned this repository and want to start fresh:

```bash
rm -rf repository-name
git clone https://github.com/source-username/repository-name.git
```

### 4. Verify the Clone

Ensure you're in the correct directory and the clone was successful:

```bash
git status
```

### 5. Create a New Branch (Optional)

If you want to work on a new feature or make changes:

```bash
git checkout -b new-feature-branch
```

Replace `new-feature-branch` with a descriptive name for your work.

To check if your branch is tracking the remote branch correctly:

```bash
git status
```
# CREATE AN SSH KEY - REFER TO THE "Generate a New SSH Key Pair" SECTION FOR INSTRUCTION

### 6. Add Your Personal GitHub as a Remote

```bash
git remote add personal git@github.com:your-username/your-repo-name.git
```

Replace `your-username` and `your-repo-name` with your actual GitHub username and repository name.

### 7. Verify Remote Repositories

Check your existing remotes:

```bash
git remote -v
```

### 8. Update Remote URL (If Necessary)

If the remote doesn't show the correct username and repository name, if it does show the correct username and repository name, then skip this step:

```bash
git remote set-url personal git@github.com:your-username/your-actual-repo-name.git
```

Replace `your-username` and `your-actual-repo-name` with the correct information.

### 9. Push to Your Personal GitHub

Push your new branch to your personal GitHub account:

```bash
git push -u personal new-feature-branch
```

Replace `new-feature-branch` with the name of your branch.

### 10. Verify the Push

To confirm your push was successful, check the remote branches:

```bash
git branch -r
```
