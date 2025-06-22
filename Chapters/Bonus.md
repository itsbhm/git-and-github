# 🎁 Bonus Chapter: Ship Clean Code with ESLint, Prettier, Husky, lint-staged & Commit Prefixes

---

## 🚀 Why This Chapter Matters

As your codebase grows, it's not enough to just write working code. Teams and developers must ensure that code is:

* **Consistently formatted**
* **Free of obvious bugs or smells**
* **Well-organized and easy to review**
* **Commit history is clean and meaningful**

This bonus chapter helps you automate that entire process using the following tools:

| Tool        | Purpose                                     |
| ----------- | ------------------------------------------- |
| ESLint      | Lint JavaScript/TypeScript for code issues  |
| Prettier    | Format code uniformly                       |
| Husky       | Hook into Git (e.g., block bad commits)     |
| lint-staged | Only run linting/formatting on staged files |
| Commitlint  | Enforce proper commit message prefixes      |

---

## 🛠️ Step-by-Step Setup

### ✅ Step 1: Initialize Your Project

```bash
npm init -y
```

---

### ✅ Step 2: Install Dev Dependencies

```bash
npm install --save-dev eslint prettier eslint-config-prettier eslint-plugin-prettier husky lint-staged @commitlint/cli @commitlint/config-conventional
```

---

### ✅ Step 3: Configure Prettier

Create a `.prettierrc` file:

```json
{
  "singleQuote": true,
  "trailingComma": "es5",
  "semi": true,
  "printWidth": 80
}
```

Create `.prettierignore`:

```
node_modules
build
dist
```

---

### ✅ Step 4: Configure ESLint with Prettier

Run the ESLint initializer:

```bash
npx eslint --init
```

After that, edit `.eslintrc.json` to extend Prettier rules:

```json
{
  "env": {
    "browser": true,
    "es2021": true
  },
  "extends": [
    "eslint:recommended",
    "plugin:prettier/recommended"
  ],
  "plugins": ["prettier"],
  "rules": {
    "prettier/prettier": "error"
  }
}
```

---

### ✅ Step 5: Setup Husky

Enable Husky Git hooks:

```bash
npx husky install
npm pkg set scripts.prepare="husky install"
npm run prepare
```

Add pre-commit hook:

```bash
npx husky add .husky/pre-commit "npx lint-staged"
```

Add commit-msg hook for commitlint:

```bash
npx husky add .husky/commit-msg "npx --no-install commitlint --edit $1"
```

---

### ✅ Step 6: Setup lint-staged

Add this to `package.json`:

```json
"lint-staged": {
  "*.{js,jsx,ts,tsx}": [
    "eslint --fix",
    "prettier --write",
    "git add"
  ]
}
```

---

### ✅ Step 7: Configure Commitlint

You can enforce full or **limited commit prefixes** using Commitlint.

To allow **only selected prefixes**, modify `commitlint.config.js` like this:

```js
module.exports = {
  extends: ['@commitlint/config-conventional'],
  rules: {
    'type-enum': [
      2,
      'always',
      [
        'feat',
        'fix',
        'docs',
        'style',
        'refactor',
        'chore'
      ]
    ]
  }
};
```

This setup allows commits **only with these prefixes**:

* `feat`
* `fix`
* `docs`
* `style`
* `refactor`
* `chore`

⛔ Any other type (e.g., `test`, `ci`, `wip`, `merge`, etc.) will be blocked with an error.

### 🧪 Example

```bash
git commit -m "feat: add carousel section"     ✅ allowed
git commit -m "test: write snapshot test"     ❌ blocked
```

Create a `commitlint.config.js` file:

```js
module.exports = {
  extends: ['@commitlint/config-conventional']
};
```

---

## 🏃️ Commit Prefix Standards

We use the [Conventional Commit](https://www.conventionalcommits.org/) standard to prefix commit messages.

### 🔹 Format:

```bash
git commit -m "<type>(optional-scope): <description>"
```

### 📄 Prefixes Only (Complete List)

* `feat`: A new feature
* `fix`: A bug fix
* `docs`: Documentation changes
* `style`: Code style changes (formatting only, no logic)
* `refactor`: Code changes that neither fix a bug nor add a feature
* `perf`: Code change that improves performance
* `test`: Adding or fixing tests
* `build`: Changes that affect the build system or external dependencies
* `ci`: Changes to CI configuration files and scripts
* `chore`: Maintenance changes (e.g., refactoring tooling)
* `revert`: Reverts a previous commit
* `wip`: Work in progress (for temporary commits)
* `init`: Initial commit
* `merge`: Merging branches
* `release`: Version release commits
* `hotfix`: Quick fixes on production

### 🌟 Examples:

```bash
git commit -m "feat: add login functionality"
git commit -m "fix(nav): correct alignment"
git commit -m "docs(readme): update contributing guide"
```

### 🎲 Common Prefixes with Emoji

| Type     | Prefix   | Emoji | Description                      |
| -------- | -------- | ----- | -------------------------------- |
| Feature  | feat     | ✨     | New features                     |
| Fix      | fix      | 🐛    | Bug fixes                        |
| Docs     | docs     | 📝    | Documentation only               |
| Style    | style    | 💄    | Formatting, white-space, etc.    |
| Refactor | refactor | ♻️    | Code changes without feature/fix |
| Test     | test     | ✅     | Tests only                       |
| Chore    | chore    | 🔧    | Maintenance or config updates    |
| CI       | ci       | 👷    | Continuous Integration related   |
| WIP      | wip      | 🚧    | Work in progress                 |
| Init     | init     | ⚡️    | Initial project commit           |
| Revert   | revert   | ↩️    | Reverting commits                |
| Release  | release  | 📅    | Tagging or releasing version     |
| Merge    | merge    | 🔀    | Merging changes                  |
| Hotfix   | hotfix   | ⚠️    | Emergency patch/fix              |

---

## 🚪 VS Code Integration

Create a `.vscode/settings.json`:

```json
{
  "editor.formatOnSave": true,
  "editor.codeActionsOnSave": {
    "source.fixAll.eslint": true
  },
  "eslint.validate": ["javascript", "javascriptreact"]
}
```

---

## 🚪 Final Directory Structure

```
project/
├── .husky/
│   ├── pre-commit
│   └── commit-msg
├── .eslintrc.json
├── .prettierrc
├── commitlint.config.js
├── package.json
└── index.js
```

---

## 📅 Final Checklist

| Task                               | Done |
| ---------------------------------- | ---- |
| Prettier formatting configured     | ✅    |
| ESLint integrated with Prettier    | ✅    |
| Husky Git hooks active             | ✅    |
| lint-staged running pre-commit     | ✅    |
| Commit messages follow convention  | ✅    |
| Commitlint blocks invalid messages | ✅    |

---

You now have a fully automated, professional Git workflow that enforces clean, readable, and maintainable code with every commit. This setup is used by top companies and teams for high-quality codebases.
