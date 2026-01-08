# Git & GitHub CLI Commands Guide

## Setup & Configuration

### Initial Git Setup
```bash
git config --global user.email "your-email@example.com"
git config --global user.name "Your Name"
git config --global core.editor "vim"  # Set default editor
```

## Repository Basics

### Initialize & Clone
```bash
git init                                    # Create new local repository
git clone <url>                             # Clone remote repository
git clone <url> <directory>                 # Clone into specific directory
```

### File Operations
```bash
git add <file>                              # Stage specific file
git add .                                   # Stage all changes
git add -A                                  # Stage all changes (including deletions)
git status                                  # Show working tree status
git status -s                               # Short format status
```

### Commits
```bash
git commit -m "message"                     # Commit with message
git commit -am "message"                    # Stage and commit tracked files
git commit --amend                          # Modify last commit
git log                                     # Show commit history
git log --oneline                           # Condensed commit history
git log --graph --all --decorate            # Visual branch history
```

## Branching

### Create & Switch
```bash
git branch <branch-name>                    # Create new branch
git branch -a                               # List all branches (local & remote)
git checkout <branch-name>                  # Switch to branch
git checkout -b <branch-name>               # Create and switch in one command
git switch <branch-name>                    # Modern alternative to checkout
git branch -M <new-name>                    # Rename current branch
git branch -d <branch-name>                 # Delete branch (safe)
git branch -D <branch-name>                 # Force delete branch
```

## Changes & Reversions

### View Changes
```bash
git diff                                    # Show unstaged changes
git diff --staged                           # Show staged changes
git diff <branch1> <branch2>                # Compare branches
git show <commit-id>                        # Show specific commit
```

### Undo Changes
```bash
git revert <commit-id>                      # Create new commit undoing changes
git revert HEAD                             # Revert most recent commit
git revert HEAD --no-edit                   # Revert with default message
git reset <file>                            # Unstage file
git reset --soft HEAD~1                     # Undo last commit, keep changes staged
git reset --mixed HEAD~1                    # Undo last commit, unstage changes
git reset --hard HEAD~1                     # Undo last commit, discard changes
```

## Remote Repositories

### Connect & Fetch
```bash
git remote add origin <url>                 # Add remote repository
git remote -v                               # List remote repositories
git fetch origin                            # Fetch all remote changes
git fetch origin <branch>                   # Fetch specific branch
```

### Pull Changes
```bash
git pull origin <branch>                    # Fetch and merge remote branch
git pull --rebase origin <branch>           # Fetch and rebase (maintains linear history)
git log <branch>..origin/<branch>           # Compare local vs remote commits
```

### Push Changes
```bash
git push -u origin <branch>                 # Push and set upstream
git push origin <branch>                    # Push to remote branch
git push origin --delete <branch>           # Delete remote branch
git push --all                              # Push all branches
git push origin --tags                      # Push all tags
```

## Merging & Rebasing

### Merge
```bash
git merge <branch-name>                     # Merge branch into current branch
git merge --no-ff <branch-name>             # Create merge commit
git merge --squash <branch-name>            # Combine commits before merging
```

### Rebase
```bash
git rebase <branch-name>                    # Rebase current branch
git rebase -i HEAD~3                        # Interactive rebase last 3 commits
git rebase --continue                       # Continue after resolving conflicts
git rebase --abort                          # Cancel rebase operation
```

## Advanced Operations

### Stashing
```bash
git stash                                   # Temporarily save changes
git stash list                              # List all stashes
git stash pop                               # Apply and remove most recent stash
git stash apply                             # Apply stash without removing
```

### Tags
```bash
git tag <tag-name>                          # Create lightweight tag
git tag -a <tag-name> -m "message"          # Create annotated tag
git tag -l                                  # List all tags
git push origin <tag-name>                  # Push specific tag
```

### Cleaning
```bash
git clean -fd                               # Remove untracked files and directories
git clean -fdx                              # Also remove ignored files
git gc                                      # Garbage collection/optimization
```

