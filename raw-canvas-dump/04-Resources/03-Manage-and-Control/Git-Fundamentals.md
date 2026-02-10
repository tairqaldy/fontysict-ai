# Git Fundamentals

# 🔧 Git Fundamentals

Master version control for collaborative software development

## 🎯 What is Git and Why Do We Need It?

**🤔 The Problem:** Imagine working on a group project where everyone emails code files back and forth. "final_version_REAL_final_v2.cs" sound familiar? That's chaos waiting to happen!

Git is a **distributed version control system** that tracks changes in your code over time. It's like having a time machine for your projects, allowing you to:

#### 📸 Save Snapshots

Keep a complete history of every change made to your project

#### 👥 Collaborate Safely

Multiple people can work on the same project without conflicts

#### 🔄 Experiment Freely

Try new features without fear of breaking working code

#### ⏪ Time Travel

Go back to any previous version when something goes wrong

**📘 S2 Context:** Git is essential for both your Individual Project and Group Project. It's not just a tool - it's a professional skill that every software developer must master.

## 🚀 Getting Started: Your First Repository

### Step 1: Initialize a Repository

# Navigate to your project folder cd my-awesome-project

# Initialize a new Git repository

git init

# Check the status of your repository

git status

**💡 What just happened?** Git created a hidden `.git` folder that will track all changes in your project. You now have a local repository!

## 📝 The Git Workflow: Add, Commit, Push

Git follows a simple three-step workflow. Think of it like preparing a package for shipping:

**💡 Commit Message Tips: **Write clear, concise messages that explain what you changed, not how. Future you will thank you!

1

#### 📦 Stage (Add)

Select which changes you want to include in your next snapshot.

git add Program.cs # Add a specific file
git add . # Add all changes in current directory
git add -A # Add all changes in the entire project

2

#### 📸 Commit

Create a snapshot with a descriptive message explaining what you changed.

git commit -m "Add user login functionality" # Commit with a meaningful message
git commit -am "Fix bug in calculation method" # Or stage and commit in one step

3

#### 🌐 Push

Upload your commits to a remote repository (like GitHub) so others can access them.

git push origin main # Push to the main branch
git push -u origin main # First time pushing? Set upstream

## 🤝 Collaboration: Working with Others

### Getting Updates from Teammates

# Download updates from remote repository

git pull origin main

# See what your teammates have been working on

git log --oneline

# Check current status

git status

### Handling Conflicts Like a Pro

Sometimes two people change the same line of code. Git will tell you about conflicts, and you'll need to resolve them manually.

 **🔥 Conflict Resolution Strategy:** 1. Don't panic! Conflicts are normal in team projects

1. Open the conflicted file and look for conflict markers
2. Discuss with your teammate which version to keep
3. Remove conflict markers and save the file
4. Add, commit, and push the resolved version

## 🛠️ Essential Git Commands Cheat Sheet

#### 🔍 Information Commands

`git status` - See current state

`git log` - View commit history

`git diff` - See changes since last commit

#### ⚡ Quick Workflow

`git add .` - Stage all changes

`git commit -m "message"` - Commit with message

`git push` - Upload to remote

#### 🆘 Emergency Commands

`git pull` - Get latest changes

`git checkout -- filename` - Undo changes to file

`git reset HEAD~1` - Undo last commit

## 🎯 Best Practices for Projects

Good: "Add user authentication with password hashing"
Bad: "fixed stuff" or "asdf"

#### 🔄 Commit Often, Push Regularly

Small, frequent commits are better than one huge commit with all your work

#### 📁 Use a .gitignore File

Don't commit build files, cache folders, or sensitive data like API keys

#### 🤝 Communicate with Your Team

Before making major changes, let your teammates know what you're working on

**📘 Professional Tip:** Start using Git from day one of your project. Don't wait until "the code is ready" - Git is most valuable when you use it throughout your development process.

## 📚 Learning Resources

**💡 Learning Strategy:** Start with the basics, practice with your own projects, then collaborate with teammates. Git becomes natural with regular use!

### 📖 Essential Resources

* **The Git Bible:** [Pro Git Book**Links to an external site.**](https://git-scm.com/book/en/v2) - Free, comprehensive guide to Git
* **Interactive Tutorial:** [Learn Git Branching**Links to an external site.**](https://learngitbranching.js.org/) - Visual, hands-on Git practice
* **GitHub Basics:** [GitHub Getting Started**Links to an external site.**](https://docs.github.com/en/get-started) - Learn to use GitHub effectively

### 🔗 Related Course Materials

* [Manage &amp; Control in Software Projects](https://fhict.instructure.com/courses/15759/pages/what-is-manage-and-control-in-a-software-project) - How Git fits into project management
* [Group Project](https://fhict.instructure.com/courses/15759/pages/group-project) - Applying Git in team collaboration
* [Individual Project](https://fhict.instructure.com/courses/15759/pages/individual-project) - Using Git for personal project management

### 🎮 Practice Platforms

**GitHub** - The most popular platform for hosting Git repositories

**GitLab** - Alternative and also available [hosted by Fontys ICT**Links to an external site.**](https://git.fhict.nl/)

**Visual Studio Code** - Excellent Git integration for beginners

*Part of the Software Design & Engineering course | Fontys ICT*
