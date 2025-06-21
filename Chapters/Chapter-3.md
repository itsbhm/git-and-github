# 🖥️ Part 3: Git with VS Code

---

## 💡 Why Use VS Code for Git?

VS Code has **built-in Git integration**, allowing you to:

* View changes (diffs) easily
* Commit without terminal
* Push/pull from GitHub
* Handle merge conflicts visually

You can use **both CLI and GUI** side by side.

---

## ✅ 1. Open a Git Project in VS Code

You’ll see a **Source Control icon** (🔃) on the sidebar if your folder is a Git repo.

If not initialized, you can:

* Click **Source Control** → `Initialize Repository`
* Or run `git init` from the terminal

---

## ✍️ 2. Making and Viewing Changes

* Edit any file
* Go to the **Source Control tab**
* You’ll see a list of changed (modified) and new (untracked) files

Click any file to:

* See changes in **side-by-side diff**
* **Discard** or **stage** with buttons

---

## ➕ 3. Stage & Commit from VS Code

* Hover over a file → click **+** icon to stage it
* Or click the **`+` (Stage All Changes)** button at the top
* Type a commit message in the box above
* Click **✓ Commit** to save the snapshot

---

## ☁️ 4. Connect to GitHub

If you’ve already:

* Initialized Git
* Pushed your repo to GitHub

VS Code can automatically detect the remote.

Otherwise:

1. Open Terminal (`` Ctrl + ` ``) and run:

   ```bash
   git remote add origin https://github.com/yourname/repo.git
   ```

2. Push:

   ```bash
   git push -u origin master
   ```

✅ Now your local code is connected to GitHub.

---

## 🔄 5. Pull / Push in VS Code

* Click the **three dots (•••)** in the Source Control panel
* Select **Push**, **Pull**, or **Sync**

Or use the bottom bar for push/pull shortcuts.

---

## 🧯 6. Merge Conflicts in VS Code

When a conflict occurs, VS Code will show:

* Incoming changes (from the branch you're merging)
* Current changes (from your branch)

You can click:

* **Accept Incoming**
* **Accept Current**
* **Accept Both**
* Or edit manually, then commit the resolved file

---

## 🧠 7. Keyboard Shortcuts

| Action              | Shortcut (Windows/Linux)     | Shortcut (Mac)    |
| ------------------- | ---------------------------- | ----------------- |
| Open terminal       | `Ctrl + \` \` or Ctrl + \`\` | \`Cmd + \`\`      |
| Commit changes      | `Ctrl + Enter`               | `Cmd + Enter`     |
| Open Source Control | `Ctrl + Shift + G`           | `Cmd + Shift + G` |
| Toggle sidebar      | `Ctrl + B`                   | `Cmd + B`         |

---

## ✅ Summary

* VS Code offers visual Git support
* You can stage, commit, and view diffs without CLI
* Great for resolving merge conflicts
* Integrates well with GitHub

---

## 🧪 Exercise

1. Open your `git-practice` folder in VS Code
2. Edit or create a file
3. Use Source Control tab to:

   * Stage changes
   * Add a commit message
   * Commit the changes
4. Link to a GitHub repo using the terminal
5. Push the changes
