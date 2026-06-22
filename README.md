# Felix

Personal site for Felix, the storyteller. Single self-contained static page (`index.html`) — no build step, no dependencies to install.

Live stack: plain HTML/CSS/JS, fonts + GSAP loaded from CDN. Deploys as a static site on Vercel.

---

## Deploy in ~2 minutes

> One-time cleanup: a stray, empty `.git` folder may be sitting in this directory (it was created in a sandbox that could not finish). Delete it first so git starts clean:
> - File Explorer: turn on "Hidden items", delete the `.git` folder here, **or**
> - PowerShell in this folder: `Remove-Item -Recurse -Force .git`

### 1. Create the GitHub repo named `felix`

**Option A — GitHub CLI (fastest):**
```bash
cd "felix"
git init
git add -A
git commit -m "Felix site: initial deploy"
git branch -M main
gh repo create felix --public --source=. --remote=origin --push
```

**Option B — Web UI:**
1. Go to https://github.com/new and create a repo named **felix** (public or private, no README/license).
2. Then in this folder:
```bash
cd "felix"
git init
git add -A
git commit -m "Felix site: initial deploy"
git branch -M main
git remote add origin https://github.com/<your-username>/felix.git
git push -u origin main
```

### 2. Connect to Vercel

**Option A — Dashboard (recommended):**
1. Go to https://vercel.com/new
2. **Import** the `felix` GitHub repo.
3. Framework Preset: **Other**. Build Command: **(leave empty)**. Output Directory: **(leave empty / root)**. Root Directory: `./`
4. Click **Deploy**.

**Option B — Vercel CLI:**
```bash
npm i -g vercel
cd "felix"
vercel          # preview deploy, follow prompts
vercel --prod   # production deploy
```

### 3. Result

- Vercel gives you a live URL like `https://felix-<hash>.vercel.app` (and `https://felix.vercel.app` if the name is free).
- Every `git push` to `main` auto-deploys. Pull requests get preview URLs.
- Add a custom domain later under the Vercel project's **Domains** tab.

---

## Files

| File | Purpose |
|---|---|
| `index.html` | The entire site (HTML + CSS + JS + embedded images, self-contained). |
| `vercel.json` | Static config: clean URLs, basic security headers. |
| `.gitignore` | Ignores `.vercel`, OS junk, logs. |

## Editing

Open `index.html` in any browser to preview locally (double-click it). Edit, commit, push — Vercel redeploys automatically.
