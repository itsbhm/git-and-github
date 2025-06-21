# ⚡️ Part 1: Getting Started with Git

---

## ✅ 1. What is Git?

**Git** is a distributed **version control system** that tracks changes in your code, allows multiple people to work on a project, and helps you roll back if anything breaks.

🔧 It helps you:

* Save snapshots of your code history (commits)
* Collaborate with others without overwriting changes
* Revert to a stable version when needed

---

## 💻 2. Install Git

You’ll need Git installed on your machine to use it in any project.

---

### 🔷 Windows

1. Go to [https://git-scm.com/download/win](https://git-scm.com/download/win)
2. Download and run the installer.
3. Use default options unless you know what you're doing.
4. It will install Git + Git Bash (recommended terminal).

---

### 🍏 Mac (using Homebrew)

1. Install Homebrew if not already installed: [https://brew.sh](https://brew.sh)
2. Run this in the terminal:

```bash
brew install git
```

---

### 🐧 Linux

Use your package manager. Example for Ubuntu/Debian:

```bash
sudo apt update
sudo apt install git
```

More help here: [https://git-scm.com/book/en/v2/Getting-Started-Installing-Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)

---

## 🔍 3. Check Git Version

Once installed, confirm it using:

```bash
git --version
```

You should see something like:

```bash
git version 2.41.0
```

---

## 👤 4. Set Username and Email (One Time)

Git uses this info to label your commits.

```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
```

✅ Replace with your actual name and email (use the one linked to your GitHub if possible).

---

## 📋 5. View Current Git Config

To verify the info you just set:

```bash
git config --list
```

You should see:

```
user.name=Your Name
user.email=you@example.com
```

---

## 🔥 Summary

| Step              | Command Example                                       |
| ----------------- | ----------------------------------------------------- |
| Check Git Version | `git --version`                                       |
| Set Username      | `git config --global user.name "Shubham"`             |
| Set Email         | `git config --global user.email "shubham@itsbhm.com"` |
| View Config       | `git config --list`                                   |

---

## 🧪 Exercise

1. Install Git on your OS
2. Open Git Bash or Terminal
3. Run:

   ```bash
   git --version
   git config --global user.name "Your Name"
   git config --global user.email "you@example.com"
   git config --list
   ```
