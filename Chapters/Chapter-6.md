# ❌ Part 6: Merge Conflicts and How to Resolve Them

---

## ⚔️ What Is a Merge Conflict?

A **merge conflict** happens when:

* Two branches **edit the same line** in the same file
* Git cannot automatically decide **which version to keep**

🧠 Example:

* Branch A changes line 5 of `index.html`
* Branch B also changes line 5
* You try to merge A into B → Git says “⚠️ Conflict!”

---

## 💣 How to Simulate a Merge Conflict (Step-by-Step)

### Step 1: Setup

```bash
mkdir merge-conflict-demo && cd merge-conflict-demo
git init
echo "Line 1" > file.txt
git add . && git commit -m "Initial commit"
```

---

### Step 2: Create a branch and change the file

```bash
git checkout -b branchA
echo "Change from A" >> file.txt
git add . && git commit -m "Update from branch A"
```

---

### Step 3: Switch to `master` and change the same file

```bash
git checkout master
echo "Change from master" >> file.txt
git add . && git commit -m "Update from master"
```

---

### Step 4: Merge and cause a conflict

```bash
git merge branchA
```

Git will show:

```
Auto-merging file.txt
CONFLICT (content): Merge conflict in file.txt
Automatic merge failed; fix conflicts and then commit the result.
```

---

## 🔍 What a Conflict Looks Like

Inside `file.txt`, you’ll now see:

```text
Line 1
<<<<<<< HEAD
Change from master
=======
Change from A
>>>>>>> branchA
```

These markers mean:

* **HEAD**: what’s currently on your branch (`master`)
* **branchA**: what you're trying to merge in

---

## 🛠 How to Fix It

You have 3 options:

* Keep HEAD (current branch)
* Keep branch content (incoming)
* Merge both manually

### Example (manual fix):

```text
Line 1
Change from master
Change from A
```

✅ Then save the file.

---

### Step 5: Stage and commit the resolved file

```bash
git add file.txt
git commit -m "Resolved merge conflict"
```

---

## 🛑 Abort the Merge (if needed)

If you want to cancel the merge completely:

```bash
git merge --abort
```

📌 Use this **only if you haven’t resolved the conflict yet**.

---

## 🧪 Use `git diff` to Investigate

See what’s conflicting:

```bash
git diff
```

Use this before or during a merge to see differences between branches or changes.

---

## 🧰 Tips for VS Code

When there's a merge conflict:

* Open the conflicted file in VS Code
* You’ll see “Accept Current / Incoming / Both” buttons
* Choose and edit visually
* Save, then commit via Git sidebar or terminal

---

## ✅ Summary

| Command                       | Purpose                     |
| ----------------------------- | --------------------------- |
| `git merge branch`            | Merge another branch        |
| `git diff`                    | View conflicting changes    |
| `git merge --abort`           | Cancel an in-progress merge |
| `git add <file>`              | Stage resolved file         |
| `git commit -m "Resolved..."` | Finalize resolution         |

---

## 🧪 Merge Conflict Challenge

1. Create a file and commit it
2. Create two branches: `feature-a` and `feature-b`
3. Modify the **same line** in both branches
4. Try merging one into the other
5. Resolve the conflict and commit
