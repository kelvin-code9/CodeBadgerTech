# ⚙️ Git & GitHub — Lesson 1: The Big Picture + Setup

✅ In this lesson, we’re going to **set the stage** so you not only install Git but also truly **understand** what it is, why it exists, and how it works with GitHub.

By the end, you’ll have:

* Git installed and configured
* A GitHub account ready to go
* SSH authentication set up (no more typing passwords for every push)
* A mental model of how Git & GitHub fit together

---

## 🎯 Part 1: What is Git? (And Why Should You Care?)

Imagine you’re writing a book — 200 pages long.
You make changes daily, sometimes deleting chapters, sometimes adding new ones.
Now, imagine **keeping every draft in a separate folder**, naming them like:

```
book-final.docx
book-final-FINAL.docx
book-FINAL-V2(UseThisOne).docx
```

💀 That’s chaos. And if your co-author emails you *their* copy with changes, you have no clean way to merge them without manually copy-pasting.

---

### 📌 Enter Git

Git is a **Version Control System (VCS)** — it solves this problem by:

* Tracking **every change** you make to files
* Allowing you to **move backward in time** to any previous state
* Letting you work on **multiple versions in parallel** without messing up the main one
* Merging your work with others automatically (and handling conflicts when needed)

💡 Git is *local first*. You can use Git without any internet connection. Every developer on a project has **the full history** of the project.

---

## 🌐 Part 2: What is GitHub? (And How is it Different from Git?)

If Git is **your time machine**,
GitHub is **the online library where you store that time machine**.

* Git manages changes **on your machine**
* GitHub is a **cloud service** that stores your Git repositories and lets you:

  * Share them with others
  * Contribute to open-source
  * Review code via Pull Requests
  * Track bugs/issues
  * Automate tasks (GitHub Actions)

💡 There are other Git hosting services — GitLab, Bitbucket — but GitHub is the most popular.

---

## 🔄 Part 3: Why Use Them Together?

| Without GitHub                      | With GitHub                    |
| ----------------------------------- | ------------------------------ |
| Git keeps your history safe locally | GitHub backs it up online      |
| You can work alone just fine        | You can collaborate globally   |
| Sharing requires sending .zip files | Sharing is one `git push` away |
| No project visibility               | Portfolio for recruiters       |

💡 GitHub **does not replace** Git — it enhances it.

---

## ⚙️ Part 4: Installing Git

### **Windows**

1. Go to [git-scm.com/downloads](https://git-scm.com/downloads)
2. Download the Windows installer
3. Run it → Keep defaults unless you know what you’re changing
4. Once installed, open **Git Bash** (comes with Git) or use your terminal

### **macOS**

```bash
brew install git
```

(Requires [Homebrew](https://brew.sh/) — if you don’t have it, install Git from the website)

### **Linux (Debian/Ubuntu)**

```bash
sudo apt update
sudo apt install git
```

---

## 🔍 Part 5: Verifying Your Installation

Run:

```bash
git --version
```

If installed, you’ll see:

```
git version 2.45.2
```

If not, your terminal will say something like `command not found`.

---

## 🧾 Part 6: Configuring Git (Your Identity)

Every commit in Git records **who made the change**.
We set our **name** and **email** so that:

* You can see authorship in history
* GitHub can match commits to your account

```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
```

💡 Use the **same email** you’ll use for GitHub, so commits appear on your GitHub profile.

Check your settings:

```bash
git config --list
```

---

---

## 🧼 Summary Table

| Concept     | Description                             |
| ----------- | --------------------------------------- |
| Git         | Local version control system            |
| GitHub      | Cloud hosting for Git repos             |
| Install Git | Download or install via package manager |
| Identity    | `git config --global user.name/email`   |
| Verify      | `git --version`                         |

---

## ⚠️ Common Pitfalls

| Problem               | What Happens                         | Fix                      |
| --------------------- | ------------------------------------ | ------------------------ |
| Wrong email in config | Commits won’t show on GitHub profile | Use same email as GitHub |
| Multiple Git versions | Wrong one runs                       | Check with `which git`   |


---

## ✅ Key Takeaways

* Git = the tool that manages versions; GitHub = the cloud platform for sharing.
* Install Git once, configure your identity so commits are correctly attributed.
* You’re now ready to **create your first repository** in Lesson 2.

---
