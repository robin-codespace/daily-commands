# Most Frequently Used Git Commands

Here are the some Git commands which in my opinion are import:

## git status
Shows the state of your working directory and staging area.
Examples:
- `git status` - Show current status
- `git status -s` - Show status in short format

## git add
Stages changes for commit.
Examples:
- `git add file.txt` - Stage a specific file
- `git add .` - Stage all changes
- `git add -p` - Interactively stage changes

## git restore (only worked for staged changes)
- `git restore .` - Restore all changes
- `git restore --staged file.txt` - Restore a specific file (Git 2.23+)

## git reset
- `git reset HEAD~1` - to undo the last commit while keeping the changes
- `git reset --hard HEAD~1` - completely discared the last commit and its changes

## git commit
Creates a new commit with your staged changes.
Examples:
- `git commit -m "Add feature"` - Quick commit with message
- `git commit` - Opens editor for detailed message
- `git commit -am "Fix bug"` - Stage tracked files and commit

## git pull
Updates your current branch with remote changes.
Examples:
- `git pull origin main` - Pull from main branch
- `git pull --rebase` - Pull and rebase local changes

## git push
Uploads your commits to remote repository.
Examples:
- `git push origin main` - Push to main branch
- `git push -u origin feature` - Push new branch and set upstream

## git branch
Manages branches in your repository.
Examples:
- `git branch` - List local branches
- `git branch -a` - List all branches including remote
- `git branch -d branch-name` - Delete a branch

## git checkout
Switches branches or restores files.
Examples:
- `git checkout main` - Switch to main branch
- `git checkout -b feature` - Create and switch to new branch
- `git checkout file.txt` - Discard file changes

## git merge
Combines changes from different branches.
Examples:
- `git merge feature` - Merge feature branch into current branch
- `git merge --abort` - Abort a problematic merge

## git log
Shows commit history.
Examples:
- `git log` - Show commit history
- `git log --oneline` - Compact commit history
- `git log --graph` - Show branch and merge history

## git stash
Temporarily stores uncommitted changes.
Examples:
- `git stash` - Quick stash
- `git stash pop` - Apply and remove latest stash
- `git stash list` - Show all stashes
