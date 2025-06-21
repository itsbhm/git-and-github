# 🔧 Part 8: Advanced Git Commands

---

## 1️⃣ `git reset` — Roll Back & Unstage Changes

### 🔹 Unstage a file (but keep changes):

```bash
git reset <file>
```

### 🔹 Unstage everything:

```bash
git reset
```

### 🔹 Roll back to a previous commit (keep your code):

```bash
git reset <commit-id>
```

### 🔥 Hard reset (dangerous — **discards code**):

```bash
git reset --hard <commit-id>
```

⚠️ Use only if you're 100% sure — it **removes all changes after that commit**.

---

## 2️⃣ `git revert` — Undo a Commit Safely

Unlike `reset`, `revert` creates a **new commit** that undoes a previous one.

```bash
git revert <commit-id>
```

✅ Safe for public repos — history remains intact.

---

## 3️⃣ `git commit --amend` — Fix Last Commit

### Change the commit message:

```bash
git commit --amend -m "Better message"
```

### Add forgotten files to last commit:

```bash
git add forgotten-file.js
git commit --amend --no-edit
```

---

## 4️⃣ `git stash` — Save Work Without Committing

Temporarily save uncommitted changes so you can switch branches or pull safely.

### Save changes:

```bash
git stash
```

### Apply last stashed changes:

```bash
git stash pop
```

### List all stashes:

```bash
git stash list
```

### Save with a name:

```bash
git stash save "new design layout"
```

---

## 5️⃣ `git rebase` — Rebuild a Cleaner History

### Rebase your branch on top of the latest `main`:

```bash
git checkout feature-branch
git rebase main
```

✅ Creates a straight, linear history.

📌 Rebase is great for cleaning up your commits **before pushing**.

---

## 6️⃣ Squash Commits (Interactive Rebase)

Squash multiple commits into one:

```bash
git rebase -i HEAD~3
```

Then mark extra commits as `squash` or `s`.

Great for:

* Cleaning up “typo fix”, “final fix”, “actual final fix”

---

## 🧪 Practice Exercise

1. Create a repo, make 3 commits
2. Run:

```bash
git log         # copy a commit ID
git reset HEAD~1     # roll back 1 commit
git commit --amend   # edit last commit
git stash            # save changes temporarily
git stash pop        # reapply them
```

---

## ✅ Summary

| Command                | Use Case                              |
| ---------------------- | ------------------------------------- |
| `git reset`            | Undo commits or unstage files         |
| `git reset --hard`     | Delete commits + changes (**danger**) |
| `git revert`           | Create undo commit (safe)             |
| `git commit --amend`   | Fix the last commit                   |
| `git stash` / `pop`    | Pause + resume uncommitted work       |
| `git rebase`           | Rewrite commit history cleanly        |
| `git rebase -i HEAD~n` | Squash n commits into one             |
