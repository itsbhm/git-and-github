# 🍴 Part 7: Forking and Pull Requests (PRs)

---

## 🌍 What Is a Fork?

A **fork** is a personal copy of someone else's repository on GitHub.

It lets you:

* Work on a project **without affecting the original**
* Make changes, test features, and submit them for review

🧠 Think of it like:
“Copy → Customize → Contribute”

---

## 🛠️ How to Fork a Repository

1. Go to any public GitHub repo (e.g., [https://github.com/itsbhm/html](https://github.com/itsbhm/html))
2. Click the **Fork** button (top-right corner)
3. Choose your GitHub account
4. You now have your **own copy** of the repo

---

## 📥 Cloning Your Fork

Once forked, clone it to your computer:

```bash
git clone https://github.com/your-username/project-name.git
```

---

## 👨‍💻 Make Your Changes

1. Create a branch:

```bash
git checkout -b new-feature
```

2. Make changes, commit them:

```bash
git add .
git commit -m "Added new feature"
```

3. Push to your fork:

```bash
git push origin new-feature
```

---

## 📬 Submitting a Pull Request (PR)

1. Go to your forked repo on GitHub
2. GitHub will show:
   👉 “Compare & pull request” button
3. Click it and write:

   * What you changed
   * Why it's helpful
   * Screenshots or details if needed
4. Submit PR!

🎉 Now the original project maintainer can review your changes and **merge** them if they’re accepted.

---

## ✅ When to Use a PR

* Contributing to open-source
* Working with teams on shared projects
* Sharing ideas without affecting the main branch directly

---

## 🧠 PR Terminology

| Term              | Meaning                                         |
| ----------------- | ----------------------------------------------- |
| PR (Pull Request) | Request to merge your changes into another repo |
| Fork              | Your copy of someone else’s repo                |
| Origin            | Your forked repo                                |
| Upstream          | The original repo you forked from               |

---

## 🔁 Optional: Add the Original Repo as "Upstream"

To fetch changes from the original repo:

```bash
git remote add upstream https://github.com/original-user/repo.git
git fetch upstream
git merge upstream/main
```

✅ Keeps your fork **up to date** with the original.

---

## 🧪 Practice

1. Fork [https://github.com/itsbhm/html](https://github.com/itsbhm/html)
2. Clone your fork locally
3. Create a branch and edit `index.html`
4. Push the branch
5. Open a PR on GitHub

---

## ✅ Summary

| Step                           | Command / Action                              |
| ------------------------------ | --------------------------------------------- |
| Fork a repo                    | Click **Fork** on GitHub                      |
| Clone it                       | `git clone https://github.com/you/repo.git`   |
| Create a branch                | `git checkout -b feature-name`                |
| Commit and push                | `git commit`, `git push origin feature-name`  |
| Submit Pull Request            | Use GitHub web interface                      |
| Add upstream remote (optional) | `git remote add upstream <original-repo-url>` |
