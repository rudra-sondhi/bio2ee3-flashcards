# 🚀 Putting this on GitHub via Terminal (and updating it later)

Do steps 1–5 **once**. After that, publishing a new chapter is the 3 commands in step 6.

Your folder (note the spaces — always keep the quotes):
```
"/Users/rudrasondhi/Desktop/University Material/BIO 2EE3/flashcards-site"
```

---

## Step 1 — Check git works & set your identity

Open **Terminal** (⌘-Space → "Terminal") and run:

```bash
git --version
```

- If you get a version number → good.
- If macOS pops up *"The git command requires the command line developer tools"* → click
  **Install**, wait a few minutes, then run it again.

Then set who you are (only needed once, ever):

```bash
git config --global user.name "Rudra Sondhi"
git config --global user.email "rudra.sondhi2@gmail.com"
```

> Use the same email as your GitHub account so your commits link to your profile.

---

## Step 2 — Create the empty repo on GitHub (browser, 30 sec)

1. Go to **https://github.com/new**
2. **Repository name:** `bio2ee3-flashcards`
3. Select **Public**
4. ❗ Leave **"Add a README file"** and the .gitignore/licence options **UNCHECKED**
   (an empty repo makes the first push clean)
5. **Create repository**

Leave that page open — it shows your repo URL.

---

## Step 3 — Turn the folder into a repo and push it

Copy-paste these one block at a time. **Replace `YOUR-USERNAME`** with your GitHub username.

```bash
cd "/Users/rudrasondhi/Desktop/University Material/BIO 2EE3/flashcards-site"
git init
git add .
git commit -m "Add BIO 2EE3 flashcards site (Chapters 1 and 2)"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/bio2ee3-flashcards.git
git push -u origin main
```

Sanity check before pushing: `git status` should list `index.html`, `ch1.html`,
`ch2.html`, `README.md`, `.gitignore` — and **no** `.DS_Store`.

---

## Step 4 — When it asks you to log in

GitHub **does not accept your account password** in the terminal. Two ways:

### Option A — GitHub CLI (easiest, browser login)
```bash
brew install gh          # skip if you already have gh
gh auth login            # choose: GitHub.com → HTTPS → Yes → Login with a web browser
```
Follow the browser prompt, then re-run `git push -u origin main`. Done — no tokens ever.

*(No Homebrew? Install it from https://brew.sh, or use Option B.)*

### Option B — Personal Access Token (no installs)
1. Go to **https://github.com/settings/tokens** → **Tokens (classic)** →
   **Generate new token (classic)**
2. Note: `mac terminal` · Expiration: 90 days (or No expiration) ·
   **Check the `repo` scope**
3. **Generate token** → copy it (starts with `ghp_`) — you only see it once
4. Back in Terminal, when prompted:
   - **Username:** your GitHub username
   - **Password:** paste the **token**

> The password field stays blank while you paste — that's normal, just hit Enter.
> macOS Keychain remembers it, so you only do this once.

---

## Step 5 — Turn on GitHub Pages

1. Your repo → **Settings** → **Pages** (left sidebar)
2. *Source*: **Deploy from a branch**
3. *Branch*: **main**, folder **/ (root)** → **Save**
4. Wait ~1 minute, refresh. Your live link appears:

```
https://YOUR-USERNAME.github.io/bio2ee3-flashcards/
```

That's the link you send the group chat. 🎉

---

## Step 6 — ⭐ Publishing an update (this is the payoff)

When you add `ch3.html` (or I send you an updated deck), drop the file in this folder, then:

```bash
cd "/Users/rudrasondhi/Desktop/University Material/BIO 2EE3/flashcards-site"
git add .
git commit -m "Add Chapter 3 deck"
git push
```

Live in about a minute at the same link. That's it — three commands, forever.

> Adding a new chapter? Also add a link card for it in `index.html` so it shows on the
> landing page (I can generate that for you).

---

## Troubleshooting

| Message | Fix |
|---|---|
| `remote origin already exists` | `git remote set-url origin https://github.com/YOUR-USERNAME/bio2ee3-flashcards.git` |
| `src refspec main does not match any` | You haven't committed yet — run `git add .` then `git commit -m "first"` |
| `Authentication failed` | You used your password. Use a **token** (Step 4B) or `gh auth login` (4A) |
| `Updates were rejected... fetch first` | Repo wasn't empty. Run `git pull --rebase origin main` then `git push` |
| `.DS_Store` keeps showing up | It's already in `.gitignore`; if it snuck in: `git rm --cached .DS_Store` then commit |
| Pages link 404s | Give it 2 min; confirm Settings → Pages is on **main / (root)** and the file is named exactly `index.html` |

---

## Handy commands

```bash
git status                  # what's changed / staged
git log --oneline           # your commit history
git remote -v               # confirm where you're pushing
```
