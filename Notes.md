# Git Global Configuration Notes

## Configuration Commands
```bash
# Set global username
git config --global user.name "Raza Ali"

# Set global email
git config --global user.email "razaalli.webdev@gmail.com"

# Set VS Code as default editor
git config --global core.editor "code --wait"

# Configure line endings (Linux/macOS)
git config --global core.autocrlf "input"

# Open global config in editor
git config --global -e

# Stage all changed files in current directory
git add .

# Commit staged changes with a message
git commit -m "Descriptive commit message"

# View commit history in compact format
git log --oneline

# Git reset 
git reset --hard HEAD~1

# Show detailed repository status
git status

# Show concise status with change indicators
git status -s

# View compact commit history
git log --oneline

# View compact history with branch visualization
git log --oneline --graph

