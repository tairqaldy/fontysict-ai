# Git Fundamentals

> Source: Canvas > Resources > Manage & Control > Git Fundamentals
> Last updated: 2026-02-10
> Status: complete

# 🔧 Git Fundamentals

Master version control for collaborative software development

## 🎯 What is Git and Why Do We Need It?

**🤔 The Problem:** Imagine working on a group project where everyone emails code files back and forth. `"final_version_REAL_final_v2.cs"` sound familiar?

Git is a **distributed version control system** that tracks changes in your code over time. It's like having a time machine for your projects, allowing you to:

* Save snapshots (commits)
* Collaborate safely
* Experiment in branches
* Roll back when needed

## 🚀 Getting Started: Your First Repository

### Step 1: Initialize a Repository

```bash
git init
git status
```

Git creates a hidden `.git` folder that will track all changes in your project. You now have a local repository.

## 📝 The Git Workflow: Add, Commit, Push

### 1. 📦 Stage (Add)

```bash
git add Program.cs
git add .
git add -A
```

### 2. 📸 Commit

```bash
git commit -m "Add user login functionality"
git commit -am "Fix bug in calculation method"
```

### 3. 🌐 Push

```bash
git push origin main
git push -u origin main
```

## 🤝 Collaboration: Working with Others

### Getting Updates from Teammates

```bash
git pull origin main
git log --oneline
git status
```

### Handling Conflicts

Conflicts happen when two people change the same lines. Git marks the conflict in the file; you and your teammate then decide which version to keep, edit, and commit the resolution.

## 🛠️ Essential Git Commands Cheat Sheet

**Info**

* `git status`
* `git log`
* `git diff`

**Workflow**

* `git add .`
* `git commit -m "message"`
* `git push`

**Recovery**

* `git checkout -- filename`
* `git reset HEAD~1`

## 🎯 Best Practices for Projects

* Commit small, logical chunks often.
* Write clear commit messages describing **what** changed and **why**.
* Use `.gitignore` to avoid committing build artifacts and secrets.
* Communicate with your team before big refactors.

## 📚 Learning Resources

* `https://git-scm.com/book/en/v2`
* `https://learngitbranching.js.org/`
* `https://docs.github.com/en/get-started`

