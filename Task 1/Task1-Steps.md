# Git Workflow - Task 1

This document outlines the complete Git workflow performed for Task 1, including repository setup, SSH configuration, commits, and advanced Git operations.

---

## 1. Create Repository

Created a new repository on GitHub named `ITI-GIT-Course`.

---

## 2. Configure SSH Authentication

Generated an SSH key pair for secure authentication with GitHub:

```bash
ssh-keygen -t ed25519 -C "agml2047@gmail.com"
```

**Steps:**
- Generated SSH key using ED25519 algorithm
- Copied the public key to GitHub settings under SSH and GPG keys
- Configured GitHub to accept SSH connections

---

## 3. Clone Repository

Cloned the repository using SSH protocol:

```bash
git clone git@github.com:Jemy45/ITI-GIT-Course.git
```

---

## 4. Initial Commit

Created the first commit with README file:

```bash
git add .
git commit -m "Initial commit"
```

**Changes:**
- Added README file with name and tracking information

---

## 5. First Feature Commit

Added Python notebook file:

```bash
git add .
git commit -m "add python dumb file"
```

**Changes:**
- Added `dumbpy.ipynb` containing Python exercises

---

## 6. Second and Third Commits

Made two commits to remove questions from the notebook:

```bash
git commit -am "Delete seventh question"
git commit -am "Delete sixth question"
```

**Note:** Used `-am` flag to add and commit modified files in one command.

---

## 7. Soft Reset - Delete Last 2 Commits

Removed the last 2 commits while preserving changes in staging area:

```bash
git reset --soft HEAD~2
```

**Effect:**
- Deleted "Delete seventh question" and "Delete sixth question" commits
- Changes remained staged

---

## 8. Unstage Changes

Removed file from staging area:

```bash
git restore --staged .\dumbpy.ipynb
```

---

## 9. Discard Working Directory Changes

Reverted file changes in working directory:

```bash
git restore .\dumbpy.ipynb
```

---

## 10. Empty Commit After Deletion

Since working tree was clean, created an empty commit:

```bash
git commit --allow-empty -m "commit after deletion"
```

**Reason:** No file changes existed, but needed to mark the deletion point.

---

## 11. Force Push to Remote

Pushed local changes to remote, overwriting remote history:

```bash
git push origin main --force
```

**Warning:** Force push rewrites remote history. Should only be used when necessary.

---

## 12. Add Lab Completion Marker

Added markdown cell to notebook with "LAB DONE" text:

```bash
git add .
```

---

## 13. Amend Last Commit

Modified the last commit to include the new changes with updated message:

```bash
git commit --amend -m "finish"
```

**Effect:**
- Combined "commit after deletion" with "LAB DONE" changes
- Replaced commit message with "finish"

---

## 14. Revert Last Commit

Created a new commit that undoes the last commit:

```bash
git revert HEAD
```

**Effect:**
- Preserved history by creating a revert commit
- Undid changes from "finish" commit without deleting it

---

## 15. Push Revert to Remote

Pushed the revert commit to remote repository:

```bash
git push origin main
```

**Note:** No force push needed because revert preserves history.

---

## Summary of Commands Used

| Command | Purpose |
|---------|---------|
| `ssh-keygen` | Generate SSH authentication key |
| `git clone` | Clone repository from remote |
| `git add` | Stage changes for commit |
| `git commit` | Create commit with changes |
| `git commit -am` | Add and commit modified files |
| `git reset --soft` | Delete commits, keep changes staged |
| `git restore --staged` | Unstage changes |
| `git restore` | Discard working directory changes |
| `git commit --allow-empty` | Create commit without changes |
| `git push --force` | Overwrite remote history |
| `git commit --amend` | Modify last commit |
| `git revert` | Undo commit with new commit |
| `git push` | Push commits to remote |

---

## Key Learnings

1. **SSH Authentication**: Secure method for connecting to GitHub
2. **Soft Reset**: Allows deletion of commits while preserving changes
3. **Empty Commits**: Useful for marking points in history without file changes
4. **Amend**: Modifies the last commit instead of creating a new one
5. **Force Push**: Overwrites remote history (use with caution)
6. **Revert**: Safe way to undo commits without rewriting history

---

**Date Completed:** March 5, 2026
