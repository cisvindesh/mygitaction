## 🌿 Git Upstream (Tracking) Branch — Simple & Clear

A **Git upstream (tracking) branch** is the **default remote branch** that your **local branch is linked to** for `git push` and `git pull`.

---

## 🔹 What is an upstream branch?

It tells Git:

> “When I run `git push` or `git pull`, **which remote branch should I use by default?**”

Example:

```
Local branch:  main
Upstream:      origin/main
```

---

## 🔹 Why upstream branch is important

Without upstream:

* ❌ `git push` fails
* ❌ `git pull` fails

With upstream:

* ✅ `git push`
* ✅ `git pull`
* ✅ `git status` shows ahead/behind info

---

## 🔹 How upstream branch is created

### 1️⃣ During first push (MOST COMMON)

```bash
git push -u origin main
```

`-u` = `--set-upstream`

Now Git remembers:

```
main ➜ origin/main
```

---

### 2️⃣ While creating branch

```bash
git checkout -b feature-x
git push -u origin feature-x
```

---

### 3️⃣ Set upstream for an existing branch

```bash
git branch --set-upstream-to=origin/main
```

or shorthand:

```bash
git branch -u origin/main
```

---

## 🔹 How to check upstream branch

### ✔ Show upstream for all branches

```bash
git branch -vv
```

Output:

```
* main      abc123 [origin/main] Initial commit
  feature   def456 [origin/feature] New feature
```

---

### ✔ Show upstream of current branch

```bash
git rev-parse --abbrev-ref --symbolic-full-name @{u}
```

---

## 🔹 What happens internally (important)

Git stores upstream info in `.git/config`:

```ini
[branch "main"]
    remote = origin
    merge = refs/heads/main
```

---

## 🔹 Visual Diagram

```
LOCAL REPO                REMOTE REPO
----------               ------------
main  o---o---o  ----->  origin/main
```

`main` tracks `origin/main`

---

## 🔹 Difference: Upstream vs Remote Branch

| Term            | Meaning                                    |
| --------------- | ------------------------------------------ |
| Remote branch   | A branch on remote repo (`origin/main`)    |
| Upstream branch | The remote branch your local branch tracks |

---

## 🔹 Common Errors & Fixes

### ❌ Error

```
fatal: The current branch feature-x has no upstream branch
```

### ✅ Fix

```bash
git push -u origin feature-x
```

---

## 🔹 Interview one-liner

> **An upstream branch is the remote branch linked to a local branch for default push and pull operations.**

---

If you want, I can also explain:

* 🔁 `git pull` with upstream
* ⚔️ Rebase vs merge using upstream
* 🚀 Best practices for feature branches

Just say the word 🙂
