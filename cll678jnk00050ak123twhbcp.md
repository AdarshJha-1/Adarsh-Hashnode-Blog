---
title: "🚀📅 Day 11 DevOps Challenge - Exploring Git: Stash, Cherry-Pick, and Sync Magic! 🚀🌟"
datePublished: Fri Aug 11 2023 06:20:28 GMT+0000 (Coordinated Universal Time)
cuid: cll678jnk00050ak123twhbcp
slug: git-magic-stash-pick-sync-shine
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1691734664060/e270b0f1-3246-4066-b8a7-99fe2733c2ca.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1691734814899/8c667bb3-c542-432c-8769-417a894c0604.png
tags: software-development, github, web-development, devops, 90daysofdevops

---

1. ## **Git Stash** 📦🔒
    
    Imagine you're working on a puzzle, but suddenly you need to clean up your table. You don't want to lose your progress, so you put all the puzzle pieces in a box to keep them safe. Git stash is like that box – it lets you store your unfinished work (changes) safely away so you can switch to a different task or branch. Later, you can take the box (stash) back out and continue where you left off.
    
2. ## **Cherry-pick** 🍒✨
    
    Pretend you have a big basket of fruit (commits), but you only want to pick one specific type of fruit (commit) and add it to your plate. Cherry-picking in Git is similar – you can choose a single commit from another branch and add it to your current branch. It's like taking the "cherry" commit you like and putting it into your work.
    
3. ## **Resolving Conflicts** 🤝🔀❌
    
    Imagine you and a friend are both editing the same document. Sometimes, you might change the same sentence differently, causing a conflict. Resolving conflicts in Git is like working together to fix those conflicting changes. You both talk it out and decide which version to keep, making sure the document makes sense in the end. Similarly, in Git, when different branches have conflicting changes, you need to decide which changes to keep and which ones to discard so that your code works smoothly.
    

## Task 1: Stash and Switch Merge Challenge

1. Create a new branch, make changes, and stash them.
    
2. Switch to a different branch, make changes, and commit.
    
3. Retrieve and apply stashed changes to the second branch.
    
    ```bash
    # Task-01: Create a new branch and make some changes to it.
    git checkout -b new-branch
    # Make some changes to your files here
    
    # Use git stash to save the changes without committing them.
    git stash save "My changes on new-branch"
    
    # Switch to a different branch, make some changes, and commit them.
    git checkout different-branch
    # Make some changes to your files here
    git add .
    git commit -m "Made changes on different-branch"
    
    # Use git stash pop to bring the changes back and apply them on top of the new commits.
    git checkout new-branch
    git stash pop
    # Now your changes from new-branch are applied on top of the changes in different-branch
    ```
    
    In this example:
    
    * You create a new branch called `new-branch`.
        
    * You make changes to the files on `new-branch` and use `git stash` to save these changes without committing them.
        
    * You switch to a different branch called `different-branch`, make changes, and commit them.
        
    * Finally, you switch back to `new-branch` and use `git stash pop` to bring back and apply the changes you stashed earlier, effectively combining them with the new commits on `different-branch`.
        

## Task 2: Feature Enhancement and Commit Alignment

1. **In** `version01.txt` **of the** `development` **branch, after the line "This is the bug fix in development branch" (from Day10 and reverted), add:**
    
    ```bash
    After bug fixing, this is the new feature with minor alteration
    ```
    
    ***Commit with the message: "Added feature2.1 in development branch"***
    
2. **Add the content:**
    
    ```bash
    This is the advancement of the previous feature
    ```
    
    ***Commit with the message: "Added feature2.2 in development branch"***
    
3. **Add the content:**
    
    ```bash
    Feature 2 is completed and ready for release
    ```
    
    ***Commit with the message: "Feature2 completed"***
    
4. **Ensure these commit messages are reflected in the** `Production` **branch, derived from** `Master` **branch, using rebase.**
    

## Task-03: Production Perfection 🚀🍒

**In the** `Production` **branch:**

1. Cherry-pick the commit "Added feature2.2 in development branch" to bring in the latest feature enhancement.
    
2. After the line "This is the advancement of the previous feature," add:
    
    ```bash
    Line4>> Added few more changes to make it more optimized.
    ```
    
    Commit with the message: "Optimized the feature" to ensure your project is running even smoother. 🛠️
    

Remember, cherry-picking lets you pick and choose specific commits like you're selecting cherries from a tree, and optimizing features ensures your software is finely tuned for peak performance! 🍒🔧🏃‍♂️

**We went on a Git journey, learning cool tricks! We saved changes like puzzles in a box using 🔒. Cherry-picking 🍒 let us pick special parts for new branches. We worked together to fix clashes 🤝, like editing a paper with friends. Finally, we made things better 🛠️, syncing all changes. Git's magic helps us work smoothly, like mixing colors. Our coding adventure continues! 🌟🚀**