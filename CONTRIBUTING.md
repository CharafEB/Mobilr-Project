# 🚀 Contributing Guide

This document defines the professional workflow for contributing to **Mobilr-Project**. To maintain code quality and stability, direct pushes to the `main` branch are strictly prohibited.

---

## ⛔ Non-Negotiable Rules

1.  **Protected `main` Branch:** ✅ Changes land via Pull Request (PR) only. ❌ No direct pushes or merges to `main`.
2.  **Issue-First Workflow:** Do not start coding before an Issue is created, described, and assigned to you.
3.  **Short-Lived Feature Branches:** Every task must be performed on a dedicated branch branched out from the latest `main`.
4.  **Mandatory Linking:** Every PR must reference and close a specific Issue (e.g., `Closes #12`).
5.  **Clean History:** Use descriptive commit messages and delete branches immediately after merging.

---

## 1) Workflow Organization

*   **Tracking:** All tasks are managed via the **GitHub Project** board.
*   **Status Updates:** Move your Issue from `Ready` to `In Progress` when you start coding, and to `In Review` once a PR is opened.

---

## 2) Branch Naming Convention

Use the following format: `<type>/<issue-number>-<short-description>`

**Allowed Types:**
*   `feature/` : New functionality.
*   `fix/` : Bug fixes.
*   `refactor/` : Code improvements without changing behavior.
*   `docs/` : Documentation updates.
*   `chore/` : Maintenance tasks.

**Examples:**
*   `feature/10-user-authentication`
*   `fix/25-api-timeout-error`

---

## 3) Commit Rules (Mandatory)

We follow a structured commit message format to keep history readable. Emojis are mandatory.

**Format:**
```
<emoji> <type>(scope): short description
```

**Emoji Mapping:**
*   ✨ `feat`: New feature
*   🐛 `fix`: Bug fix
*   💥 `breaking`: Breaking change
*   🧹 `refactor`: Code cleanup / improvement
*   🏗️ `build`: Build config / dependencies
*   📝 `docs`: Documentation
*   🧪 `test`: Testing
*   🗑️ `chore`: Maintenance / cleanup

**Example:**
```bash
git commit -m "✨ feat(profile): add avatar picker UI"
```

---

## 4) Technical Execution Steps (Development Flow)

### 4.1 Update Local Environment
Before starting a new branch, ensure you have the latest code:
```bash
git switch main
git pull origin main
```

### 4.2 Create a Feature Branch
```bash
git switch -c feature/issue-number-description
```

### 4.3 Push and Open a PR
When your changes are ready and tested:
```bash
git push -u origin feature/your-branch-name
```
Then, go to GitHub and open a Pull Request to the `main` branch.

---

## 5) Pull Request Process

### 5.1 PR Template (Mandatory)
When opening a PR, you MUST fill out the description using this template. It ensures reviewers have all the context they need.

```markdown
# 🚀 Pull Request: <Title>

**Closes #<issue-number>**

---

## 📝 Summary
> Provide a brief overview of the changes and why they were made.

## 🛠 Type of Change
- [ ] ✨ **New feature**
- [ ] 🐛 **Bug fix**
- [ ] 💥 **Breaking change**
- [ ] 🧹 **Refactor**
- [ ] 📝 **Docs / Chore**

---

## 🔍 Changes Made
- List specific changes here...

## 🚦 How to Test
1. **Pull branch:** `git switch <branch-name>`
2. **Setup:** `npm install` (if dependencies changed)
3. **Execution:** Describe steps to reproduce/test (e.g., "Login and check profile page")
4. **Verification:** What is the expected result?

---

## 📸 Visuals (Optional)
| Before | After |
| :--- | :--- |
| <img src="" width="250"> | <img src="" width="250"> |

---

## ✅ Checklist
- [ ] My code follows the project style.
- [ ] I have performed a self-review.
- [ ] I have linked the issue to the GitHub Project board.
- [ ] All tests pass locally.
```

---

## 6) Common Git Recipes (just for help)

### Undo last commit (not pushed)
```bash
git reset --soft HEAD~1
```

### Fix last commit message
```bash
git commit --amend
```

### Stash work temporarily
```bash
git stash
git stash pop
```

### Update branch with latest main
```bash
git fetch origin
git rebase origin/main
```

---

## 7) Examples

### ✨ New Feature Example
*   **Branch:** `feature/123-profile-avatar-upload`
*   **PR Title:** `✨ #123: Profile avatar upload`
*   **Commits:**
    *   `✨ feat(profile): add avatar picker UI`
    *   `✨ feat(profile): upload avatar to storage`

### 🐛 Bug Fix Example
*   **Branch:** `fix/245-login-crash-null-token`
*   **PR Title:** `🐛 #245: Fix login crash (null token)`
*   **Commits:**
    *   `🐛 fix(auth): prevent crash when token is null`
    *   `🧪 test(auth): add null token regression test`