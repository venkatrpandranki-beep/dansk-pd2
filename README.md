# Dansk PD2 App — iPhone PWA Setup Guide

## What you have
- `index.html` — the full app
- `manifest.json` — PWA config
- `sw.js` — service worker (offline support)
- `icon-192.png` / `icon-512.png` — app icons

## Step 1: Get a free GitHub account
Go to https://github.com and sign up (free).

## Step 2: Create a new repository
1. Click the **+** button → "New repository"
2. Name it: `dansk-pd2`
3. Set to **Public**
4. Check "Add a README file"
5. Click "Create repository"

## Step 3: Upload your files
1. In your new repo, click "Add file" → "Upload files"
2. Upload ALL 5 files:
   - index.html
   - manifest.json
   - sw.js
   - icon-192.png
   - icon-512.png
3. Click "Commit changes"

## Step 4: Enable GitHub Pages
1. Go to repo **Settings** → **Pages** (left sidebar)
2. Under "Source" → select **main** branch → **/ (root)**
3. Click **Save**
4. Wait 2 minutes — your URL will be:
   `https://YOUR-USERNAME.github.io/dansk-pd2/`

## Step 5: Add API Key (for AI Tutor)
1. Go to https://console.anthropic.com
2. Create an API key (free tier available)
3. In index.html, find this line near the top:
   `const API_KEY = "YOUR_ANTHROPIC_API_KEY_HERE";`
4. Replace with your actual key
5. Re-upload index.html to GitHub

## Step 6: Install on iPhone
1. Open Safari on your iPhone
2. Go to your GitHub Pages URL
3. Tap the **Share** button (box with arrow) at the bottom
4. Scroll down and tap **"Add to Home Screen"**
5. Tap **"Add"**

Done! The app now appears on your home screen like a real app — full screen, no browser bar.

## Features
- 📚 Daily vocabulary flashcards with flip animation
- 🔊 Hear Danish pronunciation (tap the speaker button)
- 🎤 Speak and get feedback (tap the mic button — uses da-DK recognition)
- 🔤 Grammar lessons with examples
- ✏️ Quiz after each lesson
- 📊 Progress tracking & streak counter
- 🤖 AI Tutor (needs internet, powered by Claude)
- 16 lessons cycling daily through your 1-year plan

## Pronunciation note
Speech recognition (🎤) works best in Chrome.
On iPhone Safari, mic works but recognition quality varies.
For best results: use Chrome on Android or desktop for pronunciation practice.
