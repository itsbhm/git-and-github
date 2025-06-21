# ☁️ Part 4: Working with Remote Repositories (GitHub)

---

## ☁️ 1. What is a Remote Repository?

A **remote repository** is a copy of your Git repo that lives on the internet — like on **GitHub**, **GitLab**, or **Bitbucket**.

🛰 This allows you to:

* Share code with others
* Back up your project
* Collaborate with teams

---

## 🔗 2. `git remote` — Add/Check Remote URLs

### Check connected remotes:

```bash
git remote -v
```

You’ll see something like:

```
origin  https://github.com/yourname/project.git (fetch)
origin  https://github.com/yourname/project.git (push)
```

### Add a remote manually:

```bash
git remote add origin https://github.com/yourname/project.git
```

---

## ☝️ 3. `git push` — Upload Code to GitHub

### First push (set upstream):

```bash
git push -u origin master
```

✅ The `-u` flag sets **origin** as the default remote, so in future you can just do:

```bash
git push
```

---

## 👇 4. `git pull` — Download & Merge Updates

Use `git pull` to **fetch and merge** changes from the remote repo.

```bash
git pull
```

📌 Always pull **before** you start working to avoid merge conflicts.

---

## 🔁 5. `git fetch` vs `git pull`

| Command     | Description                          |
| ----------- | ------------------------------------ |
| `git fetch` | Downloads latest commits only        |
| `git pull`  | Fetches and merges into local branch |

🔍 `git fetch` is safer if you want to **review before merging**.

---

## 📋 6. `git clone` — Download a Remote Repo

Clone a GitHub repo to your local machine:

```bash
git clone https://github.com/itsbhm/html.git
```

Optionally, rename the folder:

```bash
git clone https://github.com/itsbhm/html.git my-html-course
```

---

## 🧪 Practice Task

1. Create a new GitHub repo (no README)
2. In your terminal:

```bash
git init
git add .
git commit -m "Initial commit"
git remote add origin https://github.com/yourname/repo.git
git push -u origin master
```

3. On a second machine (or folder), clone your repo:

```bash
git clone https://github.com/yourname/repo.git
```

---

## ✅ Summary

| Command                       | Purpose                                |
| ----------------------------- | -------------------------------------- |
| `git remote -v`               | View current remote URLs               |
| `git remote add origin <url>` | Link local repo to GitHub              |
| `git push -u origin master`   | Push code to GitHub for the first time |
| `git pull`                    | Fetch & merge updates from GitHub      |
| `git fetch`                   | Download updates only                  |
| `git clone <url>`             | Download full remote repo to local     |
