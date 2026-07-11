# Deploying the Wima Ecosystem Hub to GitHub Pages

A step-by-step guide to publishing this hub as a live website — free, on GitHub Pages.
Two paths below: **Path A (no tools, all in the browser)** is the easiest. **Path B (Git)** is for when you're comfortable with the command line.

---

## What's in this folder

Keep all these files together — `index.html` links to the others by name, so **don't rename them**.

```
index.html                          ← the landing page (must be named exactly this)
wima-media-platform-strategy.html   ← Doc 07
wima-seo-target-map.html            ← Doc 08
wima-competitive-brief.html         ← Doc 09
wima-ecosystem-flywheel.html        ← Doc 10
wima-bank-partnership-pitch.html    ← Doc 11
wima-social-mba.html                ← Doc 12 (incl. marketing training)
wima-social-playbook.html            ← Doc 13 (middle class + diaspora)
wima-supplier-onboarding.html        ← Doc 14 (supplier onboarding)
wima-research-investment-thesis.html ← Doc 15 (Research)
wima-founders-verdict.html           ← Doc 16 (Research)
wima-learning-from-meqasa.html       ← Doc 17 (Research)
wima-global-players.html             ← Doc 18 (Research)
wima-community-content-playbook.html ← Doc 19 (Consolidated Playbook)
wima-resource-hub-plan.html          ← Doc 20 (Resource Hub Plan)
wima-mba-lecture-notes.html          ← Doc 21 (MBA Lecture Notes)
.nojekyll                           ← empty file — IMPORTANT, see note below
DEPLOY.md                           ← this guide (optional to upload)
```

### The `.nojekyll` file — don't skip it
GitHub Pages runs a system called **Jekyll** by default, which can silently break pages that use certain characters. The empty **`.nojekyll`** file switches that off so your pages render exactly as built. It starts with a dot, so it may be hidden in your file browser — make sure "show hidden files" is on when you upload, or use Path B.

---

## Path A — The browser method (no tools, ~10 minutes)

### Step 1 — Create a free GitHub account
Go to **github.com** and sign up (skip if you already have one).

### Step 2 — Create a new repository
1. Click the **+** icon (top-right) → **New repository**.
2. **Repository name:** `wima-hub` (or any name you like — this becomes part of your web address).
3. Set it to **Public**.
4. Tick **Add a README file**.
5. Click **Create repository**.

### Step 3 — Upload the hub files
1. On the repo page, click **Add file** → **Upload files**.
2. Drag in **all the `.html` files** at once.
3. **For `.nojekyll`:** if it won't drag in (because it's hidden), do this after the HTML files are up — click **Add file → Create new file**, type `.nojekyll` as the filename, leave the contents empty, and **Commit** it. That's the reliable way to get it in.
4. Scroll down and click **Commit changes**.

### Step 4 — Turn on GitHub Pages
1. In the repo, click **Settings** (top menu).
2. In the left sidebar, click **Pages**.
3. Under **Build and deployment → Source**, choose **Deploy from a branch**.
4. Under **Branch**, select **main** and folder **/ (root)**, then click **Save**.

### Step 5 — Visit your live site
1. Wait 1–2 minutes (GitHub is building it).
2. Refresh the **Pages** settings — a green banner shows your live link:
   ```
   https://YOUR-USERNAME.github.io/wima-hub/
   ```
3. Open it. The landing page loads, and every document links from it. **You're live.**

---

## Path B — The Git method (command line)

If you have **Git** installed and prefer the terminal:

```bash
# 1. Put all the hub files in one folder, then from inside that folder:
git init
git add .
git commit -m "Wima Ecosystem Hub — Documents 07-14"

# 2. Create an empty repo on github.com first (named e.g. wima-hub), then:
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/wima-hub.git
git push -u origin main
```

Then do **Step 4** above (Settings → Pages → Deploy from a branch → main → root → Save).

> Tip: `git add .` includes the hidden `.nojekyll` automatically — one reason Path B is cleaner.

---

## Updating a document later

**Browser:** open the file in your repo → click the **pencil (Edit)** icon → paste the new version → **Commit changes**. The live site updates in ~1 minute.

**Git:**
```bash
# replace the changed file(s) in your folder, then:
git add .
git commit -m "Update Doc 14"
git push
```

---

## Optional — a custom domain (e.g. hub.wimabuilders.com)

1. Buy the domain (or use one you own).
2. In your domain provider's DNS settings, add a **CNAME** record pointing your chosen subdomain (e.g. `hub`) to `YOUR-USERNAME.github.io`.
3. In the repo: **Settings → Pages → Custom domain**, enter `hub.wimabuilders.com`, **Save**.
4. Tick **Enforce HTTPS** once it's available.

---

## Troubleshooting

| Problem | Fix |
|---|---|
| Page shows a 404 | Wait 2–3 minutes after enabling Pages; confirm the file is named `index.html` (all lowercase). |
| Links between documents are broken | The filenames must match exactly — don't rename any `.html` file. |
| Styling or fonts look wrong / raw text shows | Confirm `.nojekyll` is in the repo (root level). This is the usual cause. |
| Changes not showing | Hard-refresh (Ctrl/Cmd + Shift + R); GitHub caches for ~1 minute. |
| `.nojekyll` won't upload | Use **Add file → Create new file**, name it `.nojekyll`, leave empty, commit. |

---

## After you're live

- The landing page (`index.html`) is your shareable link — send **one URL**, it opens the whole hub.
- To add future documents (Doc 15, 16…), upload the new `.html` file and add a matching card to `index.html` following the pattern already there.
- Keep the design system consistent (the fonts and CSS variables are the same across every document), so new pages match automatically.
