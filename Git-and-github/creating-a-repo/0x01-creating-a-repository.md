# 📂 Git & GitHub — Lesson 2: Your First Repository + First Commit

In Lesson 1, we installed Git, set up our name and email, and created a GitHub account.
Now it’s time to actually **put our hands on the wheel** — we’re going to create a real repository and get our first file online.

By the end of this lesson, you’ll:

* Know **what a repository really is** in practical terms
* Create a repo **on GitHub first** (easiest for beginners)
* Bring it to your computer with **git clone**
* Make changes locally and **push them back** to GitHub

---

## 🎯 Step 1: What is a Repository — in plain English

Think of a **repository** (repo) like a **special project folder** that has a memory.

* A normal folder holds files but forgets their history.
* A Git repository remembers **every save**, **every change**, **who made it**, and **when**.

When you create a repo on GitHub:

* You’re making an **online version** of that special folder.
* It’s empty at first (unless you ask GitHub to add files like a README for you).
* Anyone you allow can copy it, make changes, and send them back.

💡 You can have a **local repo** (on your computer) and a **remote repo** (on GitHub) — they sync back and forth.

---

## 🌐 Step 2: Why We’ll Start on GitHub (Option 2)

There are two ways to begin:

1. Start on your computer and upload it later (Option 1)
2. Start directly on GitHub and pull it down to your computer (Option 2)

For beginners, **Option 2 is easier** because:

* GitHub handles the initial setup
* You don’t have to remember `git init` yet
* You immediately have a remote copy ready to share

We’re going to take that path.

---

## 🖥 Step 3: Sign Up and Log In to GitHub

If you don’t have a GitHub account:

1. Go to [https://github.com](https://github.com)
2. Click **Sign up**
3. Choose:

   * A username (this will be public)
   * Your email address
   * A secure password
4. Complete the email verification
5. Log in to your new account

If you already have an account — log in.

---

## 📦 Step 4: Create a New Repository on GitHub

1. From your GitHub dashboard, look for the green **New** button (or click the “+” in the top-right → **New repository**)
2. **Repository name** → type `my-first-repo`
3. Description → optional, but helpful (e.g., “My first practice project on GitHub”)
4. **Visibility**: choose **Public** (anyone can see it) or **Private** (only you and people you invite)
5. **Initialize this repository with a README** → ✅ check this box

   * This gives us one file so the repo isn’t empty — makes cloning easier
6. Leave license and `.gitignore` as “None” for now
7. Click **Create repository**

🎉 You now have a living, breathing **remote repository** on GitHub.
You can click the README and even edit it directly in your browser — but the real fun comes when we bring it to your computer.

---

## 📥 Step 5: Cloning Your Repository (Downloading + Linking)

“Cloning” in Git means:

* You **download** a complete copy of the repository
* You also set up a **link** so your local copy knows where to send changes later

Think of it like:

> You get your own personal copy of the recipe book, but you can still send your new recipes back to the main library.

On your repo’s GitHub page:

1. Click the green **Code** button
2. Make sure **HTTPS** is selected
3. Copy the URL (looks like `https://github.com/yourusername/my-first-repo.git`)

In your terminal:

```bash
cd path/to/where/you/want/the/repo
git clone https://github.com/yourusername/my-first-repo.git
```

You should see:

```
Cloning into 'my-first-repo'...
remote: Enumerating objects...
Receiving objects...
Resolving deltas...
```

Now check:

```bash
cd my-first-repo
ls
```

You’ll see `README.md` — the same file that was on GitHub.

---

## ✏️ Step 6: Making Your First Local Change

Let’s edit the README locally.
Open `README.md` in your text editor and add:

```
## About this project
This is my first edit from my computer.
```

Save the file.

---

## 🗂 Step 7: Stage and Commit Your Change

When you change files locally, Git sees the difference but won’t save it until you **stage** and **commit**.

Check what’s changed:

```bash
git status
```

You’ll see `README.md` in red — means “modified, not staged.”

Stage it:

```bash
git add README.md
```

Check status again — now it’s green (staged).

Commit it:

```bash
git commit -m "Added an About section to README"
```

Now the change is in your local history — but not yet on GitHub.

---

## ☁️ Step 8: Push Your Changes to GitHub

“Push” means: send your local commits to the remote repo.

```bash
git push
```

If it’s your first push over HTTPS, GitHub will ask for:

* Your username
* Your **Personal Access Token** (instead of a password — because GitHub disabled password pushes in 2021)

💡 You can create a Personal Access Token:

1. Go to **GitHub → Settings → Developer settings → Personal access tokens → Tokens (classic)**
2. Click **Generate new token (classic)**
3. Set expiry (e.g., 90 days) and scopes (✅ repo)
4. Copy it — you won’t see it again
5. Use it when Git asks for a password

Once authenticated, your push will complete and GitHub will show your new README content.

---

## 🧠 Real Explanation of the Flow

Here’s what we just did:

1. **Created a repo online** — GitHub is the “main source”
2. **Cloned it** — made a linked copy on our machine
3. **Edited a file** — changed something locally
4. **Staged & committed** — told Git to save the change in our local history
5. **Pushed** — sent our local changes back to GitHub

That’s the standard “pull → edit → commit → push” loop you’ll use every day.

---

## 🧼 Summary Table

| Action        | Command               | Purpose                             |
| ------------- | --------------------- | ----------------------------------- |
| Clone a repo  | `git clone <url>`     | Get a linked local copy from GitHub |
| See changes   | `git status`          | Show modified files                 |
| Stage changes | `git add <file>`      | Mark for commit                     |
| Commit        | `git commit -m "msg"` | Save a snapshot locally             |
| Push          | `git push`            | Send commits to GitHub              |

---

## ⚠️ Common Pitfalls

| Problem                         | What Happens                      | Fix                                     |
| ------------------------------- | --------------------------------- | --------------------------------------- |
| Forgot `git add`                | Commit says “nothing to commit”   | Stage the files before commit           |
| Cloned wrong URL                | Push fails                        | Copy HTTPS URL from **Code** button     |
| Using password instead of token | Auth fails                        | Use Personal Access Token for HTTPS     |
| Editing in wrong folder         | Push says “everything up-to-date” | Make sure you’re inside the cloned repo |

---

## ✅ Key Takeaways

* Starting on GitHub is beginner-friendly — you skip `git init` and avoid setup mistakes.
* Cloning downloads the repo **and** remembers where it came from.
* The everyday Git rhythm is: **edit → add → commit → push**.
* HTTPS is simplest for beginners, but requires a Personal Access Token for pushing.

---
