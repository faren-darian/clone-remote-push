# How to Clone a GitHub Repository and Push to Another Account

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
