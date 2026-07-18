# 🦠 BIO 2EE3 Flashcards — put this online & share it

This folder is a **complete website**. Upload these 3 files and you get a link you can
drop in the class group chat.

```
index.html   ← landing page (links to both chapters)
ch1.html     ← Chapter 1 deck (65 cards)
ch2.html     ← Chapter 2 deck (110 cards)
```

Don't rename them — `index.html` links to `ch1.html` and `ch2.html` by name.

---

## Option A — GitHub Pages (recommended: free, permanent, easy to update)

1. Make a free account at **https://github.com** (skip if you have one).
2. Click **+** (top-right) → **New repository**.
   - Name: `bio2ee3-flashcards` (this becomes part of your link)
   - Set **Public**
   - Click **Create repository**
3. On the new repo page click **Add file → Upload files**.
   Drag in **all three** `.html` files → scroll down → **Commit changes**.
4. Go to **Settings → Pages** (left sidebar).
   - *Source*: **Deploy from a branch**
   - *Branch*: **main**, folder **/(root)** → **Save**
5. Wait ~1 minute, refresh that page, and your link appears:

   ```
   https://YOUR-USERNAME.github.io/bio2ee3-flashcards/
   ```

That's the link you share. 🎉

**To update later** (e.g. I send you Chapter 3): repo → **Add file → Upload files** → drag the
new/updated file in → Commit. It goes live in about a minute.

---

## Option B — Netlify Drop (fastest, ~30 seconds)

1. Go to **https://app.netlify.com/drop** and sign in (free).
2. Drag this **whole folder** onto the page.
3. You instantly get a link like `https://random-name-123.netlify.app`.
4. Optional: **Site settings → Change site name** to something like `bio2ee3-flashcards`.

Just as good for sharing; GitHub Pages is nicer if you'll keep updating it.

---

## What your classmates get

- Works on **phone and laptop**, no login, no install. On mobile they can tap
  **Share → Add to Home Screen** for an app icon.
- Works **offline** after the first load (everything is baked into the files —
  images and all).
- **Everyone's progress is their own.** Stats save in each person's own browser
  (`localStorage`), so your ✓/✗ and mastery levels are never mixed with theirs.
- Nothing is uploaded anywhere and there's no tracking.

---

## ⚠️ One thing to know about cloud sync before you share

Chapter 2 has an optional cloud-sync feature (see *BIO 2EE3 Flashcards - SYNC SETUP.md*).
**The copy in this folder has sync switched off on purpose**, which is exactly what you
want for a shared class link — everyone just keeps local stats.

If you set up Supabase for yourself, **don't paste your keys into the shared `ch2.html`**:
- everyone using the link would be writing into *your* database, and
- anyone could guess a sync code and read/overwrite someone's stats.

Instead keep **two copies**:
- `ch2.html` in this folder → blank config → the version you share.
- Your own personal copy (e.g. the one in your Week 2 folder) → your keys filled in →
  the version you use across your laptop and phone.

---

## Sharing message you can paste into the group chat

> Made interactive flashcards for BIO 2EE3 Ch 1 & 2 — 175 cards total, including every
> question from the Week 1 quiz, fill-in-the-blanks, and diagram labelling for the
> Gram +/− envelopes. Works on your phone, no login:
> `https://YOUR-USERNAME.github.io/bio2ee3-flashcards/`

---

*Study aid built from the course slides + lectures (Wessner et al., Microbiology, 3rd ed.).
It's a revision tool — the lecture material is always the source of truth.*
