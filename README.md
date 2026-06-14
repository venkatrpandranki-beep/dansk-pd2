# Dansk PD2 App — iPhone PWA Setup (Netlify)

## Files
- `index.html` — full app (no API key inside — safe to share publicly)
- `manifest.json` — PWA config
- `sw.js` — service worker
- `icon-192.png` / `icon-512.png` — app icons
- `netlify.toml` — Netlify config
- `netlify/functions/chat.js` — secure API proxy (key never in browser)

---

## Step 1: Revoke your old API key (URGENT if exposed)
Go to https://console.anthropic.com → API Keys → Delete the exposed key → Create a new one

## Step 2: Push code to GitHub (key is NOT in the code — safe)
1. Go to https://github.com → New repository → name: `dansk-pd2` → Public → Create
2. Upload ALL files including the `netlify/` folder and `netlify.toml`
3. Commit

## Step 3: Deploy to Netlify (free)
1. Go to https://netlify.com → Sign up free (use GitHub login)
2. Click "Add new site" → "Import an existing project" → GitHub
3. Select your `dansk-pd2` repo
4. Build settings: leave blank (static site)
5. Click "Deploy site"
6. Netlify gives you a URL like `https://your-site-name.netlify.app`

## Step 4: Add API key securely in Netlify
1. In Netlify dashboard → your site → **Site configuration** → **Environment variables**
2. Click "Add a variable"
3. Key: `ANTHROPIC_API_KEY`
4. Value: your new Anthropic API key (from console.anthropic.com)
5. Click Save → then **Trigger deploy** (Deploys tab → Trigger deploy)

The key now lives only on Netlify's servers. It is NEVER in your HTML. GitHub can scan forever and find nothing.

## Step 5: Install on iPhone
1. Open **Safari** on iPhone
2. Go to your Netlify URL (e.g. `https://dansk-pd2.netlify.app`)
3. Tap the **Share** button (box with arrow at bottom)
4. Tap **"Add to Home Screen"**
5. Tap **"Add"**

Done! Full-screen app on your home screen.

---

## Why this is secure
- `index.html` calls `/.netlify/functions/chat` (your own server)
- The Netlify function calls Anthropic with the key from environment variable
- The key never travels to the browser — not in HTML, not in JavaScript
- GitHub sees zero secrets

## Pronunciation note
Speech mic (🎤) works best in Chrome.
On iPhone Safari it works but quality varies — go to Settings → Safari → Microphone → Allow.
