# 🏠 Part 2: Creating Your First Git Repository

---

## 🛠️ 1. `git init` — Initialize a Git Repository

`git init` creates a new **local git repository** in your project folder.

### 🔹 Example:

```bash
mkdir my-first-git-project
cd my-first-git-project
git init
```

You’ll see:

```
Initialized empty Git repository in ...
```

📁 Git creates a hidden `.git/` folder — this stores your entire commit history.

---

## 👁️ 2. `git status` — View Repository Status

Use this to check the state of your working directory.

```bash
git status
```

It tells you:

* Which files are **untracked**
* Which are **staged**
* Which are **modified**

---

## ➕ 3. `git add` — Stage Changes

Before committing, you must **stage** the files.

### Stage a specific file:

```bash
git add index.html
```

### Stage all files:

```bash
git add .
```

---

## 📸 4. `git commit` — Save a Snapshot

Commits are like “save points” in your project.

```bash
git commit -m "Initial commit 🚀"
```

🔒 This records the current staged changes into your Git history.

---

## 🔁 Bonus: Add + Commit in One Step

```bash
git commit -am "Updated homepage"
```

✅ This adds and commits all **modified** (already tracked) files.
⚠️ It won’t include **new** files — they still need `git add` first.

---

## 🧪 5. View Commit History

```bash
git log
```

You’ll see:

```
commit 38723abc...
Author: Shubham V <email>
Date:   ...

    Initial commit 🚀
```

---

## 💡 Quick Summary

| Step            | Command                    |
| --------------- | -------------------------- |
| Initialize Repo | `git init`                 |
| Check Status    | `git status`               |
| Stage File      | `git add filename`         |
| Stage All Files | `git add .`                |
| Commit          | `git commit -m "message"`  |
| Add + Commit    | `git commit -am "message"` |
| View Log        | `git log`                  |

---

## 🧪 Exercise

1. Create a folder and navigate into it:

   ```bash
   mkdir git-practice && cd git-practice
   ```

2. Initialize Git:

   ```bash
   git init
   ```

3. Create a file:

   ```bash
   echo "Hello Git" > hello.txt
   ```

4. Stage and commit:

   ```bash
   git add .
   git commit -m "Initial commit"
   ```

5. View your commit:

   ```bash
   git log
   ```
