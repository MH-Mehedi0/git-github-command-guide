# Git & GitHub Command Guide

A beginner-friendly Git and GitHub command reference in Bangla, including the complete workflow for Pull, Change, Commit, and Push.

## 📌 Table of Contents

- [1. Basic Git Commands](#1-basic-git-commands)
- [2. First-Time GitHub Setup](#2-first-time-github-setup)
- [3. Daily Project Workflow](#3-daily-project-workflow)
- [4. Common Git Problems](#4-common-git-problems)
- [5. Useful Git Commands](#5-useful-git-commands)

---

## 1. Basic Git Commands

| Command | কাজ |
|---|---|
| `git init` | নতুন Git Repository তৈরি করে |
| `git status` | ফাইলের বর্তমান অবস্থা দেখায় |
| `git add .` | সব পরিবর্তিত ফাইল Stage করে |
| `git add filename` | নির্দিষ্ট ফাইল Stage করে |
| `git commit -m "message"` | পরিবর্তনের Snapshot তৈরি করে |
| `git log --oneline` | Commit History দেখায় |
| `git branch` | Branch-এর তালিকা দেখায় |
| `git branch -M main` | বর্তমান Branch-এর নাম `main` করে |
| `git remote -v` | Remote Repository-এর URL দেখায় |
| `git pull origin main` | Remote থেকে `main` Branch-এর পরিবর্তন আনে |
| `git push origin main` | Local Commit GitHub-এ পাঠায় |
| `git clone URL` | GitHub Repository-এর Local Copy তৈরি করে |

---

## 2. First-Time GitHub Setup

নতুন Local Project-কে GitHub Repository-র সঙ্গে Connect করার জন্য এই ধাপগুলো অনুসরণ করো।

### Step 1: Initialize Git

```bash
git init
```

### Step 2: Add Project Files

```bash
git add .
```

### Step 3: Create the First Commit

```bash
git commit -m "Initial commit"
```

### Step 4: Rename the Branch

```bash
git branch -M main
```

### Step 5: Connect GitHub Repository

```bash
git remote add origin https://github.com/USERNAME/REPOSITORY.git
```

Replace `USERNAME` with your GitHub username and `REPOSITORY` with your repository name.

### Step 6: Push to GitHub

```bash
git push -u origin main
```

**Note:** If `origin` is already configured, do not run `git remote add origin` again.

---

## 3. Daily Project Workflow

প্রতিদিন কোড পরিবর্তন করার পর সাধারণত নিচের Workflow অনুসরণ করবে।

### Step 1: Check the Current Branch

```bash
git branch
```

### Step 2: Pull the Latest Code

```bash
git pull origin main
```

### Step 3: Make Changes

নিজের Code Editor, VS Code অথবা Antigravity ব্যবহার করে প্রজেক্টের কোড পরিবর্তন করো।

### Step 4: Check Changed Files

```bash
git status
```

### Step 5: Stage Changes

```bash
git add .
```

### Step 6: Commit Changes

```bash
git commit -m "Update project"
```

### Step 7: Push to GitHub

```bash
git push origin main
```

### 🚀 Complete Workflow — Copy & Run

```bash
git pull origin main
git status
git add .
git commit -m "Update project"
git push origin main
```

**Important:** এই Workflow চালানোর আগে নিশ্চিত হও যে তোমার Local Changes নিরাপদ আছে। Pull-এর সময় Conflict হলে আগে সেটি সমাধান করো। নতুন পরিবর্তন না থাকলে Commit করার প্রয়োজন নেই।

---

## 4. Common Git Problems

### Problem 1: `nothing to commit`

**কারণ:** নতুন কোনো পরিবর্তন নেই অথবা সব পরিবর্তন ইতিমধ্যে Commit করা হয়েছে।

```bash
git status
```

পরিবর্তন না থাকলে নতুন Commit করার দরকার নেই।

### Problem 2: `remote origin already exists`

**কারণ:** Repository-তে আগে থেকেই `origin` সেট করা আছে।

```bash
git remote -v
```

Remote URL পরিবর্তন করতে চাইলে:

```bash
git remote set-url origin https://github.com/USERNAME/REPOSITORY.git
```

### Problem 3: Push Rejected

**কারণ:** GitHub-এ এমন Commit আছে যা তোমার Local Branch-এ নেই।

প্রথমে নিজের পরিবর্তন নিরাপদ করো। তারপর:

```bash
git pull --rebase origin main
```

Conflict হলে ফাইলগুলো ঠিক করে:

```bash
git add .
git rebase --continue
```

Rebase সফল হলে:

```bash
git push origin main
```

### Problem 4: Check Repository Connection

```bash
git remote -v
```

### Problem 5: View Commit History

```bash
git log --oneline
```

---

## 5. Useful Git Commands

| Command | কাজ |
|---|---|
| `git diff` | Commit না করা পরিবর্তন দেখায় |
| `git diff --staged` | Stage করা পরিবর্তন দেখায় |
| `git fetch origin` | Remote-এর আপডেট আনে, কিন্তু Local Branch-এ Merge করে না |
| `git switch main` | `main` Branch-এ যায় |
| `git switch -c feature-name` | নতুন Branch তৈরি করে সেখানে যায় |
| `git restore filename` | Stage না করা পরিবর্তন বাতিল করে |
| `git stash` | সাময়িকভাবে Local Changes সরিয়ে রাখে |
| `git stash pop` | Stash করা পরিবর্তন ফিরিয়ে আনে |

**Warning:** `git restore` দিয়ে বাতিল করা পরিবর্তন হারিয়ে যেতে পারে। ব্যবহার করার আগে নিশ্চিত হও যে পরিবর্তনগুলো দরকার নেই।

---

## 📖 Remember the Workflow

```text
PULL → CHANGE CODE → STATUS → ADD → COMMIT → PUSH
```

- **Pull:** GitHub থেকে সর্বশেষ পরিবর্তন আনা।
- **Change:** প্রজেক্টের কোড পরিবর্তন করা।
- **Status:** পরিবর্তন যাচাই করা।
- **Add:** Commit-এর জন্য ফাইল প্রস্তুত করা।
- **Commit:** পরিবর্তনের Snapshot তৈরি করা।
- **Push:** Commit GitHub-এ পাঠানো।

---

**Repository Name:** `git-github-command-guide`

**Purpose:** A simple Bangla reference for learning and using Git and GitHub commands.
