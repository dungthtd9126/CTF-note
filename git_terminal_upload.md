# Phase 1: Create a Repository on GitHub
# Phase 2: Initialize and Commit Locally
```
cd /path/to/your/local/project
```
1. Initialize the directory as a Git repository (skip if already initialized)
```
git init
```
2. Stage all of your project files for the first commit
```
git add .
```
3. Commit the staged files with a descriptive message
```
git commit -m "Initial commit"
```
4. Rename your default branch to 'main' (matches GitHub's default standard)
```
git branch -M main
```
# Phase 3: Link and Push to GitHub
5. Link your local repository to the remote GitHub repository
```
git remote add origin <PASTE_YOUR_GITHUB_REPOSITORY_URL>
```
6. Push your local 'main' branch up to GitHub
```
git push -u origin main
```
# Update repo after changes
- Check stauts:
```
git status
```
- Update current changes in local
```
git add .
```
- commit on main git
```
git commmit -m "add changes"
```
# Track large files by lfs extension (file > 50mb)
Example:
```c
git lfs track "*.tar.gz"
git add .gitattributes
```
Then commit those change

- Install extension:
```
https://git-lfs.com/
```
Then extract the tar file and run:
```c
cd git-lfs-3.7.1 // current version when I install it
sudo ./install.sh // Because it use commit changes in /usr/local
```
# Exclude a folder when add changes
```c
git add . ":!folder_name"
```
