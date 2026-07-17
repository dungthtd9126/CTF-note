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
