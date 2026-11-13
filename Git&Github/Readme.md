[⬅ Back to Main Page](../README.md) | [⬅ Prev: Google Docs](../Google-Docs/README.md)

# Git & GitHub — Complete Class Notes & Command Reference

**Git** is a distributed Version Control System (DVCS) that tracks changes in files over time, while **GitHub** is a cloud-based hosting platform for Git repositories that enables team collaboration, pull requests, and code reviews.

---

## 1. Core Concepts & Git Architecture
* **Repository (`repo`):** A project folder tracked by Git (contains a hidden `.git` directory).
* **The Three Local States / Areas:**
  1. **Working Directory:** The folder where you currently edit files.
  2. **Staging Area (Index):** A preview area holding files marked for the next commit.
  3. **Local Repository:** Permanent history of snapshots (`commits`) stored on your machine.
* **Remote Repository:** The cloud copy of your repository hosted on **GitHub** (commonly named `origin`).

---

## 2. Setup & Configuration Commands
Run these once after installing Git to attach your identity to commits:
```bash
git --version                                  # Check installed Git version
git config --global user.name "Your Name"      # Set global username
git config --global user.email "you@email.com" # Set global email
git config --list                              # View all Git settings
```

---

## 3. Starting & Cloning Repositories
```bash
git init                  # Initialize a new local Git repository in current folder
git clone <repo-url>      # Download an existing GitHub repository to your PC
```

---

## 4. Basic Snapshotting Workflow (Add, Status, Commit)
```bash
git status                # Check modified, untracked, and staged files
git add <filename>        # Stage a specific file
git add .                 # Stage all new and modified files in current directory
git commit -m "Message"   # Save staged changes to local repository with a message
git commit -am "Message"  # Stage tracked files and commit in one step
```

---

## 5. Inspecting History & Differences
```bash
git log                   # View full commit history (hash, author, date, message)
git log --oneline         # View compact one-line summary of commits
git log --graph --all     # View visual branch and merge history
git diff                  # Show unstaged changes in working directory
git diff --staged         # Show changes currently in the staging area
git show <commit-hash>    # Inspect details and changes of a specific commit
```

---

## 6. Branching & Merging
Branches allow you to work on new features or fixes without breaking the `main` branch:
```bash
git branch                     # List all local branches (* shows current branch)
git branch <branch-name>       # Create a new branch
git checkout <branch-name>     # Switch to an existing branch
git checkout -b <branch-name>  # Create AND switch to a new branch immediately
git switch <branch-name>       # Modern command to switch branches
git switch -c <branch-name>    # Modern command to create and switch branch
git merge <branch-name>        # Merge specified branch into your current branch
git branch -d <branch-name>    # Delete a merged branch safely
```

---

## 7. Remote Repositories & GitHub Syncing
```bash
git remote -v                        # List connected remote URLs
git remote add origin <repo-url>     # Link local repo to a GitHub repository
git branch -M main                   # Rename default branch to 'main'
git push -u origin main              # Push local commits to GitHub (first time)
git push origin <branch-name>        # Push updates to a specific branch
git pull origin main                 # Fetch AND merge latest changes from GitHub
git fetch origin                     # Download remote changes without auto-merging
```

---

## 8. Undoing Changes, Resetting & Stashing
```bash
git restore <filename>          # Discard unstaged edits in working directory
git restore --staged <filename> # Unstage a file (keeps your file edits)
git reset --soft HEAD~1         # Undo last commit, keep changes staged
git reset --hard HEAD~1         # Undo last commit AND delete all changes permanently
git revert <commit-hash>        # Create a new commit that safely reverses an old commit
git stash                       # Temporarily save uncommitted work aside
git stash pop                   # Restore stashed changes back to working directory
```

---

## 9. Important GitHub Features Learned
* **`.gitignore`:** A special file listing files/folders Git should ignore (e.g., `*.aux`, `*.log`, `*.exe`, `node_modules/`).
* **Fork:** Creating your own personal copy of someone else's GitHub repository.
* **Pull Request (PR):** Requesting the repository owner to review and merge your branch changes into `main`.
* **Merge Conflict:** Occurs when two branches edit the same lines of a file; resolved manually by editing conflict markers (`<<<<<<<`, `=======`, `>>>>>>>`) and committing.
* **GitHub Pages:** Free static web hosting directly from a GitHub repository (used to publish documentation pages).

---

[⬅ Back to Main Page](../README.md) | [⬅ Prev: Google Docs](../Google-Docs/README.md)
