## Section 1: Git Workflow (Push & Pull Mechanics)

Understanding how to initialize, track, push, and pull changes ensures seamless coordination between local code, remote repositories, and cloud environments (such as Visual Studio Code and Google Colab).

### 1.1 Local repository initialization & identity setup
Run these commands inside your project root folder:

```bash
# Initialize a new local Git repository
git init

# Configure author identity for the repository
git config user.name "NAME"
git config user.email "EMAIL"
```

### 1.2 Remote association & branch setup
Link your local workspace to your remote GitHub repository:

```bash
# Add remote origin
git remote add origin [https://github.com/USERNAME/REPOSITORY_NAME.git](https://github.com/USERNAME/REPOSITORY_NAME.git)

# Set main as the default primary branch
git branch -M main
```

### 1.3 Staging, committing, and pushing changes
When uploading new code or edits to GitHub:

```bash
# Check status of tracked/untracked files
git status

# Stage specific files or all changes
git add .               # Stages all modified and new files
# git add src/main.py   # Alternative: Stages a specific file

# Commit changes with a clear conventional message
git commit -m "feat: setup initial environment scripts and docs"

# Push commits to remote repository
git push -u origin main
```

### 1.4 Pulling remote changes (Synchronization)
When working across multiple environments (e.g., pulling code modified in GitHub or Google Colab back into VS Code):

```bash
# Fetch and merge latest changes from remote 'main'
git pull origin main
```

> [!WARNING]
> Executing rm -rf .git permanently removes all revision history. Only use this command if you explicitly intend to reset the Git workspace.
