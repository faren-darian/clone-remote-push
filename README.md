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

***You only need to set the remote once per repository.***

```bash
git remote add personal git@github.com:your-username/your-repo-name.git
```

Replace `your-username` and `your-repo-name` with your actual GitHub username and repository name.

- If you want to remote a repository on github and save changes that you made in vscode:
- 
```bash
git remote set-url origin git@github.com:your-username/your-repo-name.git
```

|             Command             |                     What it does                     |                            Used when                            |
|:-------------------------------:|:----------------------------------------------------:|:---------------------------------------------------------------:|
| `git remote add [name] [url] `    | Adds a new remote (with a custom name like `personal`) | You want to keep multiple remotes                               |
|`git remote set-url origin [url] `| Changes the existing `origin` remote URL               | You want to switch the existing remote (e.g. from HTTPS to SSH) |


### 7. Verify Remote Repositories

Check your existing remotes:

```bash
git remote -v
```

### 8. Update Remote URL (If Necessary)

If the remote doesn't show the correct username and repository name, (if it does show the correct username and repository name, then skip this step):

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


- If you want to remote a repository on github through SSH and save changes that you made in vscode, follow the below steps:

| Step |              What to Do             |                               Command to Run                              |              What It Means             |
|:----:|:-----------------------------------:|:-------------------------------------------------------------------------:|:--------------------------------------:|
|0 |check status|`git status`||
|0| Test SSH connection| `ssh -T git@github.com`||
| 1️⃣    | Clone the repo using **SSH**                 | `git clone git@github.com:your-username/your-repo-name.git`                 | Copy your GitHub repo to your computer (Bringing the project to your local machine) |
|Do the 🔄 step to remote |   |||
| 2️⃣    | Go into the folder                  | `cd your-repo-name `                                                        | Move into the project directory        |
| 3️⃣    | Open in VS Code                     | `code .`                                                                    | Open the current folder in VS Code     |
| 4️⃣    | Make changes in files               | (Use VS Code)                                                             | Edit .ipynb, .py, .md, etc.            |
| 5️⃣    | Check changes                       | `git status`                                                                | See which files were changed           |
| 6️⃣    | Stage changes                       | `git add . `                                                                | Add all changed files (**stage** your changes)                 |
| 7️⃣    | Commit changes                      | `git commit -m "your message"  `                                            | Save a version with a message locally         |
| 8️⃣    | Push to GitHub                      | `git push origin main     `                                                 | Send your changes to GitHub            |
| 🔄    | If you cloned with HTTPS by mistake |` git remote set-url origin git@github.com:your-username/your-repo-name.git` | Fix it to use SSH (no password needed) |
| 🔎    | Check current remote                |` git remote -v      `                                                       | See if it's SSH or HTTPS               |

🧠 Think of it like this:
SSH key = 🔐 Your house key to GitHub

Clone = 📦 Bringing the project to your computer

Remote = 📡 Git remembers where the repo lives online

Push/pull = 🔁 Send/receive updates

## So What Do You Do Next Time?
Just:

1. Open your repo folder in VS Code:

```bash
cd your-repo-name
code .
```
2. Make your changes

3. Run:

```bash
git add .
git commit -m "your update message"
git push origin main
```
