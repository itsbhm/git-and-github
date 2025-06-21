# 🦾 Part 9: GitHub Automation

**(Codespaces, GitHub Actions, and CI/CD)**

---

## 🌩️ 1. GitHub Codespaces — Cloud Development

### 🔧 What is Codespaces?

**GitHub Codespaces** gives you a **cloud-powered VS Code environment** in the browser — pre-configured with your repo’s code, settings, and extensions.

> 💻 No local setup needed — just code from anywhere.

---

### 🚀 How to Use Codespaces

1. Open any GitHub repo (yours or a fork)
2. Click the **`<> Code`** button
3. Choose the **Codespaces** tab
4. Click **Create codespace on \[branch-name]**

🔐 Requires GitHub account (free-tier includes usage)

---

## 🔄 2. GitHub Actions — Automation for Developers

### ⚙️ What is GitHub Actions?

GitHub Actions lets you **automate tasks** like:

* Running tests on every push
* Deploying apps after a merge
* Sending Slack notifications
* Formatting code or linting

> 🔁 CI/CD (Continuous Integration / Delivery) directly in your GitHub repo

---

### 📦 Key Concepts

| Term         | Meaning                                             |
| ------------ | --------------------------------------------------- |
| **Workflow** | The automation logic (YAML file)                    |
| **Job**      | A group of steps run on a virtual machine           |
| **Step**     | Individual tasks (run command, checkout code, etc.) |
| **Runner**   | The machine where it runs (Ubuntu, Windows, Mac)    |

---

### 📄 Example Workflow

`.github/workflows/node.yml`

```yaml
name: Node CI

on: [push]

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
    - name: Get code
      uses: actions/checkout@v3

    - name: Install dependencies
      run: npm install

    - name: Run tests
      run: npm test
```

This workflow:

* Runs on every `push`
* Installs Node packages
* Runs tests using `npm test`

---

## 🌍 Marketplace

GitHub Actions has 10,000+ **ready-to-use actions** like:

* Deploy to Firebase, Netlify, or AWS
* Lint code
* Auto-tag releases
* Generate changelogs

Explore: [https://github.com/marketplace/actions](https://github.com/marketplace/actions)

---

## 🔐 Secrets & Environment Variables

You can safely store API keys and tokens in:

```
Settings → Secrets → Actions
```

Then access them in workflows like:

```yaml
env:
  API_KEY: ${{ secrets.API_KEY }}
```

---

## 🧪 Try It Yourself

1. Create a repo with a simple Node/HTML project
2. Add a `.github/workflows/test.yml` file
3. Add this inside:

```yaml
name: CI Test

on: [push]

jobs:
  echo:
    runs-on: ubuntu-latest
    steps:
      - run: echo "🚀 GitHub Actions Works!"
```

4. Push → see Actions tab trigger!

---

## ✅ Summary

| Feature            | Purpose                                |
| ------------------ | -------------------------------------- |
| **Codespaces**     | VS Code in the browser                 |
| **GitHub Actions** | Automate testing, building, deploying  |
| **Workflows**      | Define jobs/steps in YAML files        |
| **CI/CD**          | Run builds/tests/deploys automatically |
| **Secrets**        | Secure your API keys and tokens        |
