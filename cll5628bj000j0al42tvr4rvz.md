---
title: "🚀📅 Day 10 DevOps Challenge  - Advance Git & GitHub for DevOps Engineers"
datePublished: Thu Aug 10 2023 12:59:47 GMT+0000 (Coordinated Universal Time)
cuid: cll5628bj000j0al42tvr4rvz
slug: day-10-devops-challenge-advance-git-github-for-devops-engineers
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1691672278267/f0f8ecdf-f09a-4ea1-9b67-8af2dcf4815e.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1691672376119/f8203193-437f-4457-a133-053c2656f42a.png
tags: software-development, web-development, devops, 90daysofdevops, shubhamlondhe

---

Welcome to this blog post on Advance Git & GitHub for DevOps Engineers! In this post, we will cover some key concepts and commands that are essential for working with Git and GitHub effectively. 🚀

## **Git Branching 🌿**

Branching in Git is a powerful feature that allows developers to isolate development work without affecting other parts of the repository. Every repository has a default branch (usually `master`), and you can create multiple other branches for specific tasks. This isolation helps in developing features, fixing bugs, and experimenting with new ideas without disrupting the main codebase.

### **Merging Branches** 🔄

Merging is the process of integrating changes from one branch into another. This is often done using pull requests, which allow for review and collaboration. Merging is essential for combining new features or bug fixes back into the main branch.

## **Git Revert and Reset ⏪**

Git provides two important commands, `git reset` and `git revert`, that help manage changes in previous commits.

**git reset** allows you to unstage changes or move the HEAD to a previous commit, effectively removing or altering commits.

**git revert** creates a new commit that undoes specific changes from a previous commit, leaving a history of changes intact.

## **Git Rebase and Merge 🔄**

### **Git Rebase 🌐**

Git rebase integrates changes from one branch to another by modifying the commit history. It's often used to streamline the commit history and make it more linear. Rebase helps in avoiding the complexities that can arise during traditional merge operations.

### **Git Merge 🔄**

Git merge combines branches by creating a new commit that has two parent commits. This preserves the commit history of both branches. There are two methods of merging branches: `git merge` and `git rebase`. Both achieve the same goal but differ in their commit history representation.

## 📝 **Task 1: Adding and Modifying Commits** 🌱

### **Step 1: Creating a New Branch and Adding a Text File**

```bash
cd /path/to/Devops/Git  # Navigate to the Git folder
git checkout -b dev     # Create and switch to the 'dev' branch
echo "This is the first feature of our application" > version01.txt
```

### **Step 2: Making Changes and Committing**

```bash
git status               # See the changes
git add version01.txt    # Add the changes
git commit -m "Added new feature"  # Commit with a message
```

### **Step 3: Pushing Changes to Remote Repository**

```bash
git push origin dev      # Push changes to remote 'dev' branch
```

### **Step 4: Adding More Content and Making Commits**

```bash
echo "This is the bug fix in development branch" >> Devops/Git/version01.txt
git add Devops/Git/version01.txt
git commit -m "Added feature2 in development branch"

echo "This is gadbad code" >> Devops/Git/version01.txt
git add Devops/Git/version01.txt
git commit -m "Added features in development branch"

echo "This feature will gadbad everything from now." >> Devops/Git/version01.txt
git add Devops/Git/version01.txt
git commit -m "Added feature4 in development branch"
```

### **Step 5: Restoring to a Previous Version**

```bash
git reset HEAD~1         # Remove the last commit but keep changes
# OR
git reset --hard HEAD~1  # Remove the last commit and discard changes
```

Remember to replace `/path/to/Devops/Git` with the actual path to your Git folder. Additionally, be cautious when using `git reset --hard`, as it permanently discards changes.

## 🌲 Git Branching and Merging🌿

📝 **Step 1: Creating and Merging Branches** 🌿

1. Open your terminal or Git Bash. 💻
    
2. Navigate to your project directory using `cd path/to/your/project`. 📂
    
3. Create a new repository or use an existing one with `git init`. 🆕
    
4. Create a new file named [`README.md`](http://README.md) or any other file using `touch` [`README.md`](http://README.md). 📄
    
5. Add and commit the initial file to the master branch:
    
    ```bash
    git add README.md
    git commit -m "Initial commit"
    ```
    
6. Create a new branch named `dev`:
    
    ```bash
    git checkout -b dev
    ```
    
7. Make changes to the file, like adding more content or modifying it.
    
8. Add and commit the changes to the `dev` branch:
    
    ```bash
    git add README.md
    git commit -m "Added content in dev branch"
    ```
    
9. Switch back to the `master` branch:
    
    ```bash
    git checkout master
    ```
    
10. Merge the changes from the `dev` branch into `master`:
    
    ```bash
    git merge dev
    ```