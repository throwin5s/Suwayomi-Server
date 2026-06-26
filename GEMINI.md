# Gemini Instructions for Suwayomi-Server

This file outlines the Git workflow rules that Gemini/Antigravity must follow when starting tasks, merging upstream updates, or pushing custom changes. Read this file at the start of every task.

---

## Workspace Remote Configuration
- **origin**: `https://github.com/throwin5s/Suwayomi-Server.git` (Your fork - read/write)
- **upstream**: `https://github.com/Suwayomi/Suwayomi-Server.git` (Original repository - read-only)

---

## Standard Git Workflows for Gemini

### 1. Starting a New Coding Task
Before making any edits or starting a new feature, Gemini should ensure it is working on top of the latest official code:
1. Fetch and merge latest upstream updates into your local `master` branch:
   ```bash
   git checkout master
   git fetch upstream
   git merge upstream/master
   ```
2. Push the updated `master` branch to your fork so your GitHub account is also synchronized:
   ```bash
   git push origin master
   ```
3. Create and switch to a new task branch:
   ```bash
   git checkout -b <task-or-feature-name>
   ```

### 2. Saving and Pushing Your Changes
When you want to save your progress or finish a task:
1. Stage and commit all changes with a clear description:
   ```bash
   git add .
   git commit -m "feat/fix: describe the changes made"
   ```
2. Push the task branch to your fork:
   ```bash
   git push origin <task-or-feature-name>
   ```

### 3. Syncing the Work-in-Progress with New Upstream Updates
If the original repository gets new updates while you are working on a custom branch, Gemini should merge them:
1. Fetch updates and update local `master`:
   ```bash
   git checkout master
   git fetch upstream
   git merge upstream/master
   ```
2. Switch back to your custom task branch and merge `master`:
   ```bash
   git checkout <task-or-feature-name>
   git merge master
   ```
3. Resolve any merge conflicts if they occur, commit them, and push the updated branch to your fork.
