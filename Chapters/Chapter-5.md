# 🌲 Part 5: Collaboration with Branches and Merging

---

## 🌱 1. What is a Branch?

A **branch** lets you work on a feature, bug fix, or experiment **without affecting the main project**.

When done, you **merge** it back into `master` or `main`.

💡 Example: You’re working on a new contact form → create a branch `contact-form` → build it → merge into main when complete.

---

## 🔎 2. `git branch` — List, Create, and Delete

### List all branches:

```bash
git branch
```

### Create a new branch:

```bash
git branch feature-login
```

### Delete a branch:

```bash
git branch -d feature-login
```

---

## 👀 3. `git checkout` — Switch Between Branches

### Move to a branch:

```bash
git checkout feature-login
```

### Shortcut: create and switch to a branch:

```bash
git checkout -b feature-login
```

✅ Always create new features on a separate branch.

---

## 🔀 4. `git merge` — Combine Branches

After finishing work on your branch:

1. Go to the branch you want to merge **into** (usually `main` or `master`)
2. Run:

```bash
git merge feature-login
```

Git tries to combine the changes automatically.

---

## 🔁 5. `git diff` — See Differences Before Merging

```bash
git diff main feature-login
```

Shows the changes between the two branches.

---

## ⚔️ 6. What is a Merge Conflict?

A merge conflict happens when:

* You and someone else **edited the same line**
* Or **changed the same file in different ways**

Git doesn’t know which version to keep.

---

## ⚙️ How to Resolve Merge Conflicts

1. Git shows markers like:

```diff
<<<<<<< HEAD
Your version
=======
Incoming version
>>>>>>> feature-branch
```

2. Edit the file manually or use VS Code to resolve it.

3. Then commit the resolution:

```bash
git add conflicted-file.html
git commit -m "Resolved merge conflict"
```

4. If things get messy:

```bash
git merge --abort
```

---

## 🧪 Practice Exercise

```bash
# Start a project
mkdir branch-practice && cd branch-practice
git init
echo "Hello world" > index.html
git add . && git commit -m "Initial commit"

# Create a branch and change content
git checkout -b new-feature
echo "New Feature" >> index.html
git add . && git commit -m "Added new feature"

# Merge into main
git checkout master
git merge new-feature
```

---

## ✅ Summary

| Command                    | Purpose                          |
| -------------------------- | -------------------------------- |
| `git branch`               | List branches                    |
| `git branch branch-name`   | Create a branch                  |
| `git checkout branch-name` | Switch to branch                 |
| `git checkout -b name`     | Create + switch                  |
| `git merge branch-name`    | Merge into current branch        |
| `git diff`                 | See differences between branches |
| `git merge --abort`        | Cancel a merge                   |
