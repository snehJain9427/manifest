# Complete Setup and Repository Guide

## 1. Initial Git Configuration
```
git config --global user.name "Your Name"
git config --global user.email "your_email@example.com"
```
## 2. SSH Authentication Setup
### Generate a new SSH key
```
ssh-keygen -t ed25519 -C "your_email@example.com"
```
### Start the SSH agent and add your key
```
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519
```
### Copy your public key (Choose the command for your OS)
**macOS:** pbcopy < ~/.ssh/id_ed25519.pub \
**Linux:** cat ~/.ssh/id_ed25519.pub \
**Windows (Git Bash):** clip < ~/.ssh/id_ed25519.pub 


### Test SSH connection to GitHub
```
ssh -T git@github.com
```
## 3. Project Workspace Initialization
```
mkdir my-workspace
cd my-workspace
```
### Initialize the workspace using the SSH manifest URL
```
#repo init command
repo init -u git@github.com:snehJain9427/manifest.git -m manifest.xml
#repo sync command
repo sync
```
## 4. Optional: Switch Existing Repository Remote to SSH
#### Run this inside an existing git repository folder if needed:
```
git remote set-url origin git@github.com:snehJain9427/manifest.git
```
