# Deployment Guide — Hosting on GitHub Pages

This guide walks you through getting your live URL and GitHub repository link for submission.

---

## What You'll Get

After following these steps:

- ✅ **Live URL:** `https://xrisxi.github.io/itzfizz/`
- ✅ **Repo URL:** `https://github.com/XrisXi/itzfizz`

---

## Prerequisites

- A [GitHub account](https://github.com) (free)
- Git installed — download at [git-scm.com](https://git-scm.com)
- Your `index.html` file ready

---

## Step 1 — Create a GitHub Repository

1. Go to [github.com](https://github.com) and sign in
2. Click the **`+`** button (top right) → **New repository**
3. Fill in:
   - **Repository name:** `itzfizz-hero`
   - **Description:** `Scroll-driven hero section animation`
   - **Visibility:** ✅ Public ← **must be public for free GitHub Pages**
   - Leave all other options as default
4. Click **Create repository**

---

## Step 2 — Upload Your Files

### Option A — Upload via Browser (Easiest)

1. On your new empty repo page, click **"uploading an existing file"**
2. Drag and drop both files:
   - `index.html`
   - `README.md`
3. At the bottom, write a commit message: `Initial commit`
4. Click **Commit changes**

### Option B — Upload via Git (Terminal)

```bash
# 1. Create a folder and add your files
mkdir itzfizz-hero
cd itzfizz-hero
# Copy index.html and README.md into this folder

# 2. Initialize git
git init
git add .
git commit -m "Initial commit"

# 3. Connect to GitHub (replace YOUR-USERNAME)
git remote add origin https://github.com/YOUR-USERNAME/itzfizz-hero.git
git branch -M main
git push -u origin main
```

---

## Step 3 — Enable GitHub Pages

1. In your repository, click **Settings** (top menu bar)
2. In the left sidebar, scroll down to **Pages**
3. Under **Source**, select:
   - Branch: **`main`**
   - Folder: **`/ (root)`**
4. Click **Save**

GitHub will show a banner:

> ✅ Your site is being published at `https://YOUR-USERNAME.github.io/itzfizz-hero`

---

## Step 4 — Wait for Deployment

GitHub Pages takes **1–3 minutes** to go live.

You can check the status:
1. Go to your repo → **Actions** tab
2. Look for a workflow called **"pages build and deployment"**
3. A green ✅ means your site is live

---

## Step 5 — Verify Your Live Site

Open your browser and go to:

```
https://YOUR-USERNAME.github.io/itzfizz-hero
```

You should see the hero section with the Porsche animation. Test:
- The car enters from the left on page load
- Scrolling down reveals the letters one by one
- The car drives across the full screen

---

## Your Submission Links

Once live, your two submission links are:

```
Live webpage:        https://YOUR-USERNAME.github.io/itzfizz-hero
GitHub repository:   https://github.com/YOUR-USERNAME/itzfizz-hero
```

Paste both into the Google Form.

---

## Troubleshooting

### Site shows a 404 error

- Make sure the file is named exactly `index.html` (lowercase)
- Check Settings → Pages → confirm source is set to `main` branch
- Wait another minute and hard-refresh (`Ctrl + Shift + R`)

### Car image not showing

- The car is embedded as base64 inside `index.html` — it requires no separate image file
- If you edited the HTML, make sure you didn't accidentally remove the base64 data

### Fonts not loading

- The site requires an internet connection to load Google Fonts
- Open browser DevTools → Console for any errors

### Animation not smooth

- Use a Chromium-based browser (Chrome, Edge, Brave) for best performance
- Make sure hardware acceleration is enabled in your browser settings

---

## Updating the Site

Every time you push changes to the `main` branch, GitHub Pages automatically redeploys:

```bash
# Make your edits to index.html, then:
git add index.html
git commit -m "Update animation"
git push
```

Redeploy takes about 1–2 minutes.

---

## Repository Settings to Check

Go to your repo → **Settings** → verify:

| Setting | Value |
|---|---|
| Visibility | Public |
| Default branch | main |
| Pages source | main / root |

---

## Done!

Submit these two links to your Google Form:

| Field | Your Link |
|---|---|
| Live webpage | `https://YOUR-USERNAME.github.io/itzfizz-hero` |
| GitHub repository | `https://github.com/YOUR-USERNAME/itzfizz-hero` |
