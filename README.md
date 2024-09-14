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
