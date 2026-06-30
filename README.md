# See It Clearly — Quit Coach

A private, reasoning-first quit-tobacco coach that runs entirely in your browser. Your data (chat, memory, settings) lives only in your browser's local storage. Your Anthropic API key is typed per-device and is **never** stored in this code or repo.

- **App:** `index.html` (self-contained — all HTML/CSS/JS in one file)
- **Installable:** `manifest.webmanifest` + `sw.js` make it a PWA (home-screen icon, full-screen, offline shell)
- **Docs:** `see-it-clearly-coach-v1.1.md` (the coach spec), `quit-coach-program.md`

---

## Put it on your phone (GitHub Pages)

### 1. Create a repo and push

From this folder, on your computer:

```bash
git init
git add .
git commit -m "See It Clearly quit coach"
git branch -M main
# create an EMPTY repo named quit-coach on github.com first, then:
git remote add origin https://github.com/<your-username>/quit-coach.git
git push -u origin main
```

### 2. Turn on GitHub Pages

On github.com → your repo → **Settings → Pages** → under "Build and deployment", set **Source = Deploy from a branch**, **Branch = `main` / `/ (root)`**, Save.

After a minute your app is live at:

```
https://<your-username>.github.io/quit-coach/
```

### 3. Install it on your phone

Open that URL in your phone browser → **Share → Add to Home Screen** (iPhone) or the **Install app** prompt (Android). It opens full-screen with its own icon. First launch, paste your Anthropic API key in Settings.

> The key never leaves your device and is not in this repo — so a public Pages link is safe.

---

## Edit it from your phone (Claude Code on the web)

1. Go to **claude.ai/code** (Claude Code on the web — research preview on Pro/Max/Team plans).
2. **Connect GitHub** and pick your `quit-coach` repo.
3. Start a session and tell it what to change (e.g. "tweak the proactive opener wording"). It edits `index.html`, commits to the repo, and GitHub Pages auto-redeploys — refresh the app on your phone to see it.

You can monitor and drive these sessions from the **Claude mobile app** too.

---

## After editing

If you change `index.html`, the service worker caches the old shell. To force phones to pick up changes, bump the `CACHE` version string in `sw.js` (e.g. `qc-shell-v1` → `qc-shell-v2`) and push.
