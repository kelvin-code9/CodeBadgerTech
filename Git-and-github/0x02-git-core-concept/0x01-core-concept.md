# 📖 3. Core Git Concepts — The Mental Model

Before we push more code to GitHub, let’s slow down and **understand Git’s “world”**.
If you only memorize commands without knowing what’s happening, Git will feel like magic — and magic is scary when it breaks.

Think of Git as having **three main ideas**:

* **Where your code lives** (repos, branches)
* **How changes are stored** (commits, staging)
* **How different versions connect** (merges, history)

---

## 1️⃣ Repository (Repo) — Local & Remote

* **Local repository** → lives on *your computer*. Created with `git init`.
* **Remote repository** → lives on a server (e.g., GitHub).
* They can be **linked** so changes move between them.

💡 Analogy:

* Local repo = your **personal diary** at home.
* Remote repo = a **photocopy** of your diary stored in a library.

Commands you’ve seen:

```bash
git init               # makes a local repo
git remote add origin <url>   # links local to remote
```

---

## 2️⃣ Commit — A Snapshot of Your Code

A **commit** is a **save point in time**.
When you commit, Git stores:

* **Changes** you made
* **Message** describing the change
* **Author & date**
* A unique **hash ID** (like `6a1f9c2`)

💡 Git **doesn’t store full copies** of every file each time — it stores *changes* (deltas).

Example:

```bash
git commit -m "Add homepage HTML"
```

---

## 3️⃣ Branch — A Parallel Version of Your Project

* **Branch** = a pointer to a commit.
* You start with `main` (or `master` in older repos).
* You can create other branches to test features without breaking the main branch.

💡 Analogy:

* `main` = your main workbench.
* `feature-x` = another workbench where you can experiment.

Common commands:

```bash
git branch feature-login   # create branch
git checkout feature-login # switch to branch
```

---

## 4️⃣ Merge — Combining Work from Different Branches

Merging = taking changes from one branch and **integrating** them into another.
Sometimes Git can do it automatically, sometimes you get **merge conflicts**.

💡 Analogy:

* You and a friend edit the same doc in different rooms.
* When you combine changes, you have to decide which version wins.

Example:

```bash
git checkout main
git merge feature-login
```

---

## 5️⃣ Staging Area — What `git add` Really Does

The **staging area** is like a **shopping cart** before checkout:

* You can **pick which files** go into the next commit.
* This is why you can commit some changes but not others.

Example:

```bash
git add index.html  # stage this file only
git add .           # stage all changes
```

---

## 6️⃣ The Three Zones of Git

Git’s workflow happens in **three zones**:

| Zone                  | What’s Here                       | Command to Move Forward |
| --------------------- | --------------------------------- | ----------------------- |
| **Working directory** | Your actual files on disk         | `git add`               |
| **Staging area**      | Changes you’ve selected to commit | `git commit`            |
| **Commit history**    | Permanent snapshots of your code  | `git push` (to share)   |

Flow:

```
Edit files → git add → git commit → git push
```

---

## 🧠 Visual Mental Model

```
[ Working Directory ]  --git add-->  [ Staging Area ]  --git commit-->  [ Local Repo ]
        ↑                                                               |
        └------------------------------git pull------------------------┘
        
[ Local Repo ] --git push--> [ Remote Repo (GitHub) ]
```

---

## 🔑 Key Takeaways

* A **repo** can be local, remote, or both.
* A **commit** is a permanent save point.
* A **branch** is a pointer to a line of commits.
* The **staging area** decides *which* changes go into the next commit.
* Always think in **zones**: working dir → staging → commit history → GitHub.

---
