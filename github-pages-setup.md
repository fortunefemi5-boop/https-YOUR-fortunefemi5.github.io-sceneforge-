# Getting SceneForge onto GitHub Pages

GitHub Pages is free and gives you the `https://` URL that both Chrome's
"Install app" prompt and the Play Store publishing guide need. This takes
about 5 minutes.

---

## Step 1 — Create the repo

1. Go to [github.com/new](https://github.com/new)
2. Repository name: `sceneforge` (or anything you like — it becomes part of your URL)
3. Set it to **Public** (Pages on a free account needs a public repo)
4. Leave "Add a README" unchecked
5. Click **Create repository**

---

## Step 2 — Upload the files

Easiest way, no terminal needed:

1. On your new repo's page, click **uploading an existing file**
2. Drag in all 8 files together:
   - `sceneforge.html`
   - `index.html`
   - `manifest.json`
   - `sw.js`
   - `icon-192.png`
   - `icon-512.png`
   - `icon-512-maskable.png`
   - `icon-180.png`
3. Scroll down, click **Commit changes**

*(Prefer git? `git clone` your new empty repo, copy the files in, then
`git add . && git commit -m "SceneForge" && git push`.)*

---

## Step 3 — Turn on Pages

1. In your repo, go to **Settings** → **Pages** (left sidebar)
2. Under **Build and deployment** → **Source**, choose **Deploy from a branch**
3. Branch: `main`, folder: `/ (root)` → **Save**
4. Wait about a minute — GitHub builds and shows a banner with your live URL

Your app is now at:

```
https://YOUR-USERNAME.github.io/sceneforge/
```

(`index.html` automatically redirects that root URL straight into
`sceneforge.html` — no need to type the filename.)

---

## Step 4 — Confirm it actually works

Open the URL above in Chrome and check:

- The app loads with no console errors (right-click → Inspect → Console)
- On Android Chrome, or desktop Chrome's menu, you should see an **Install SceneForge** option within a few seconds of loading
- Visiting `https://YOUR-USERNAME.github.io/sceneforge/manifest.json` directly shows the manifest JSON, not a 404

If the manifest or icons 404, double check all 8 files landed in the repo
**root** (not inside a subfolder).

---

## Step 5 — Plug the URL into the Play Store guide

Back in `publishing-to-google-play.md` and `twa-manifest.json`, replace
`YOUR-DOMAIN` with:

```
YOUR-USERNAME.github.io/sceneforge
```

and `startUrl` in `twa-manifest.json` becomes:

```
/sceneforge/sceneforge.html
```

Everything else in that guide proceeds exactly as written.

---

## Updating the app later

Any time you want to change SceneForge, upload the new `sceneforge.html` to
the same repo (Settings aren't needed again) — GitHub Pages redeploys
automatically within a minute, and anyone with it installed picks up the
change next time they open it.
