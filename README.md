# Git and GitHub Complete Cheat Sheet

## Table of Contents

1. [Basic Configuration](#basic-configuration)
2. [Basic Commands](#basic-commands)
3. [Branching and Merging](#branching-and-merging)
4. [Remote Repository Operations](#remote-repository-operations)
5. [Advanced Operations](#advanced-operations)
6. [Git Workflow Best Practices](#git-workflow-best-practices)

## Basic Configuration

```bash
# Set global username
git config --global user.name "Your Name"

# Set global email
git config --global user.email "your.email@example.com"

# Set VS Code as default editor
git config --global core.editor "code --wait"

# Configure line endings
git config --global core.autocrlf "input"  # For Linux/macOS
git config --global core.autocrlf "true"   # For Windows

# View all configurations
git config --list

# Open global config in editor
git config --global -e
```

## Basic Commands

```bash
# Initialize new repository
git init

# Clone repository
git clone <repository-url>
git clone <repository-url> <directory-name>

# Check repository status
git status
git status -s  # Short format

# Stage files
git add <file-name>
git add .  # Stage all changes
git add -A  # Stage all changes including deletions

# Commit changes
git commit -m "Commit message"
git commit -am "Commit message"  # Stage and commit in one command

# View commit history
git log
git log --oneline  # Compact format
git log --graph --oneline --all  # Visual representation
git log --author="username"  # Filter by author
git log --since="2 weeks ago"  # Filter by date

# Undo changes
git restore <file>  # Discard changes in working directory
git restore --staged <file>  # Unstage changes
git reset HEAD~1  # Undo last commit, keep changes staged
git reset --hard HEAD~1  # Undo last commit, discard changes
```

## Branching and Merging

```bash
# List branches
git branch  # Local branches
git branch -r  # Remote branches
git branch -a  # All branches

# Create and switch to new branch
git switch -c <branch-name>
git checkout -b <branch-name>  # Alternative syntax

# Switch branches
git switch <branch-name>
git checkout <branch-name>  # Alternative syntax

# Delete branch
git branch -d <branch-name>  # Safe delete
git branch -D <branch-name>  # Force delete

# Merge branches
git merge <branch-name>
git merge --no-ff <branch-name>  # Create merge commit

# Rebase branch
git rebase <branch-name>
git rebase --continue  # After resolving conflicts
git rebase --abort  # Cancel rebase

# Stash operations
git stash  # Save changes temporarily
git stash list  # List stashes
git stash pop  # Apply and remove latest stash
git stash apply  # Apply latest stash
git stash drop  # Remove latest stash
```

## Remote Repository Operations

```bash
# Add remote repository
git remote add origin <repository-url>

# List remotes
git remote -v

# Fetch changes
git fetch origin
git fetch --all

# Pull changes
git pull origin <branch-name>
git pull --rebase origin <branch-name>

# Push changes
git push origin <branch-name>
git push -u origin <branch-name>  # Set upstream
git push --force  # Force push (use with caution)

# Update remote tracking
git remote update origin --prune
```

## Advanced Operations

```bash
# Cherry-pick commits
git cherry-pick <commit-hash>

# Interactive rebase
git rebase -i HEAD~3  # Rebase last 3 commits

# Amend last commit
git commit --amend  # Change message
git commit --amend --no-edit  # Keep message

# Create and apply patches
git format-patch <commit-hash>
git am <patch-file>

# Bisect for finding bugs
git bisect start
git bisect good <commit-hash>
git bisect bad <commit-hash>
git bisect reset

# Submodules
git submodule add <repository-url>
git submodule update --init --recursive
```

## Git Workflow Best Practices

### Feature Branch Workflow

1. Create feature branch from main
2. Develop and commit changes
3. Push feature branch to remote
4. Create pull request
5. Review and merge

### Git Flow

- main: Production code
- develop: Development code
- feature/\*: New features
- release/\*: Release preparation
- hotfix/\*: Production fixes

### Commit Message Guidelines

- Use present tense
- First line: Summary (50 chars or less)
- Body: Detailed explanation
- Reference issues/tickets

### Best Practices

1. Commit often, perfect later
2. Write meaningful commit messages
3. Keep commits focused and atomic
4. Review changes before committing
5. Use .gitignore effectively
6. Regular pulls from main branch
7. Clean up merged branches
8. Use meaningful branch names

### Common .gitignore Patterns

```
# Dependencies
node_modules/
vendor/

# Build outputs
dist/
build/

# IDE files
.idea/
.vscode/

# Environment files
.env
.env.local

# Logs
*.log
npm-debug.log*

# OS files
.DS_Store
Thumbs.db
```

Remember to:

- Always pull before pushing
- Keep commits atomic and focused
- Write clear commit messages
- Use branches for new features
- Review code before merging
- Keep your repository clean
