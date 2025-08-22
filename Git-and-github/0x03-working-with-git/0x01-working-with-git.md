
# Hands-On: From Empty GitHub Repo to First PR (VS Code + Terminal)

---

## Step 1 — Create an empty repo on GitHub

* On GitHub → **New repository** → name it `git-beginner-lab`.
* Leave it empty (no README, no license, no `.gitignore`).
* Copy the HTTPS URL:

  ```
  https://github.com/<you>/git-beginner-lab.git
  ```

---

## Step 2 — Clone into VS Code

Open VS Code → open terminal (\`Ctrl+\`\`). Run:

```bash
git clone https://github.com/<you>/git-beginner-lab.git
cd git-beginner-lab
```

👉 Check your repo state:

```bash
git status
```

Expected:

```
On branch main
nothing to commit, working tree clean
```

🔎 **Explanation**:

* *On branch main* → You’re on the `main` branch.
* *working tree clean* → Git isn’t seeing any new/changed files yet.

---

## Step 3 — Create your first files

In VS Code, create two new files:

* `README.md`

  ```
  # Git Beginner Lab

  Learning Git with VS Code and terminal.
  ```
* `hello.txt`

  ```
  hello world
  ```

Save both.

👉 Run:

```bash
git status
```

You’ll see:

```
Untracked files:
  README.md
  hello.txt
```

🔎 **Explanation**:

* **Untracked** = Git notices these files exist, but they’re not part of version control yet.
* Until you explicitly add them, Git will ignore them when saving snapshots.

---

## Step 4 — Stage, commit, and push

Stage = pick files for the snapshot.
Commit = take the snapshot.
Push = send it to GitHub.

```bash
git add README.md hello.txt
git status   # now they show as "Changes to be committed"
git commit -m "chore: add README and hello.txt"
git push
```

👉 Refresh GitHub → your files appear.

---

## Step 5 — Make and track a change

Edit `hello.txt` → add this line:

```
second line
```

Check status:

```bash
git status
```

You’ll see:

```
modified: hello.txt
```

🔎 **Explanation**:

* File is **already tracked** (because you committed it earlier).
* Now Git sees the difference between your last snapshot and the new content.

Commit it:

```bash
git add hello.txt
git commit -m "feat: add second line"
git push
```

## Step 6 — Add a `.gitignore` (protect your secrets ⚠️)

Sometimes, we have files on our computer that should **never ever** end up on GitHub:

* Secret API keys
* Passwords
* Private configs (like `.env`)

👉 If you push these by mistake, they become **public on the internet**. Anyone could steal and abuse them (e.g., hackers using your secret keys to spend money or attack servers).

### Fake Danger Demo

1. In VS Code, create a file called `.env`
   Put this inside (fake secrets, don’t worry):

   ```
   API_KEY=sk_live_123456789
   DB_PASSWORD=mySuperSecretPass
   ```

2. Run:

   ```bash
   git status
   ```

   You’ll see:

   ```
   Untracked files:
     .env
   ```

   🔎 Git sees `.env`, but if you commit it, this **sensitive info** goes straight to GitHub. Bad idea.

---

### The Fix: `.gitignore`

1. Create a new file named `.gitignore`.
   Add this:

   ```
   # Never push secrets
   .env
   ```

2. Save, then run:

   ```bash
   git status
   ```

   Now `.env` disappears from the list.

   🔎 Git is now **ignoring** `.env`. Even if it changes, Git won’t track it.

3. Commit the `.gitignore` (but **not** `.env`):

   ```bash
   git add .gitignore
   git commit -m "chore: add .gitignore to ignore secrets"
   git push
   ```

---

✅ **Key lesson**: `.gitignore` is your **safety net**. Without it, you risk exposing private stuff forever on GitHub. Always set it up early for secrets/configs.

---