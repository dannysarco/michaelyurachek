# 🪴 GitHub Branching Strategy

---

## 🔁 Main Branches

- **`main`** – Always contains the production-ready, deployable code.
- **`dev`** – Active development branch. All new work is merged here first.

---

## 🌿 Working Branches

Create short-lived branches for features and fixes off `dev`:

### ✅ Feature Branches

feature/short-description

**Examples:**
- `feature/user-login`
- `feature/add-settings-page`

### 🐛 Bugfix Branches

bugfix/short-description

**Examples:**
- `bugfix/fix-login-error`
- `bugfix/ui-glitch`

---

## 🔧 Workflow Steps

1. **Start from dev:**
   ```bash
   git checkout dev
   git pull
   ```
2.	**Create a working branch:**
    ```bash
    git checkout -b feature/your-feature-name
    ```
3.	**Work, commit, and push:**
    ```bash
    git add .
    git commit -m "feat: add login form"
    git push --set-upstream origin feature/your-feature-name
    ```
4.	**Merge to dev:**
    ```bash
    git checkout dev
    git pull
    git merge feature/your-feature-name
    git push
    ```
5.	**Release to main:**
    ```bash
    git checkout main
    git pull
    git merge dev
    git push
    ```

    ---

## ✏️ Commit Message Convention
Follow this format for clarity:
```code
<type>: <short summary>
```
**Examples:**
* feat: add user login screen
* fix: correct typo on landing page
* refactor: clean up settings component

**Types:**
* feat – New feature
* fix – Bug fix
* refactor – Code cleanup
* docs – Documentation only
* test – Adding tests
* chore – Maintenance tasks

---

### ✅ (Optional) GitHub Tips
* Use Pull Requests even if you’re solo – they help with context and tracking.
* Protect main in GitHub settings:
    * Require PRs before merging.
    * Block direct pushes.

---

### 🧭 Visual Overview
```code
main
 └── dev
      ├── feature/user-login
      ├── feature/add-settings-page
      └── bugfix/fix-login-error
```

---