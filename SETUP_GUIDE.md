# 🚀 Setup Guide — 100 Day Trading Challenge

Complete this 3-part guide to get your dashboard live with Firebase + GitHub Pages.

---

## PART 1 — Firebase Setup (5 minutes)

### Step 1: Create Firebase Project
1. Go to **https://console.firebase.google.com**
2. Click **"Add project"**
3. Name it: `trading-challenge` (or anything)
4. Disable Google Analytics (optional), click **Create project**

### Step 2: Enable Google Authentication
1. In your project → click **Authentication** (left sidebar)
2. Click **"Get started"**
3. Click **Google** under Sign-in providers
4. Toggle **Enable** → set Project support email → **Save**

### Step 3: Create Firestore Database
1. Click **Firestore Database** (left sidebar)
2. Click **"Create database"**
3. Choose **"Start in test mode"** → **Next**
4. Choose a location (e.g. `us-central`) → **Done**

### Step 4: Add Your Web App & Get API Keys
1. Click **Project Overview** (top left, the ⚙️ gear icon → Project settings)
2. Scroll down to **"Your apps"** → click **</>** (Web)
3. App nickname: `Trading Dashboard` → **Register app**
4. You'll see a `firebaseConfig` object like this:

```javascript
const firebaseConfig = {
  apiKey: "AIzaSy...",
  authDomain: "trading-challenge-xxxxx.firebaseapp.com",
  projectId: "trading-challenge-xxxxx",
  storageBucket: "trading-challenge-xxxxx.appspot.com",
  messagingSenderId: "123456789",
  appId: "1:123456789:web:abcdef"
};
```

### Step 5: Paste Config into index.html
1. Open `index.html` in any text editor (Notepad, VS Code, etc.)
2. Find this section near the top (around line 15):
```javascript
const firebaseConfig = {
    apiKey:            "PASTE_apiKey",
    authDomain:        "PASTE_authDomain",
    ...
```
3. Replace each `"PASTE_..."` value with your actual values from Firebase
4. **Save the file**

### Step 6: Add Authorized Domain
1. In Firebase → Authentication → **Settings** tab → **Authorized domains**
2. Add your GitHub Pages URL: `yourusername.github.io`

---

## PART 2 — GitHub Setup & Deploy (5 minutes)

### Step 1: Create GitHub Repository
1. Go to **https://github.com/new**
2. Repository name: `100-day-trading-challenge`
3. Set to **Public**
4. Click **Create repository**

### Step 2: Upload Files
**Option A — GitHub Desktop (easiest):**
1. Download GitHub Desktop: https://desktop.github.com
2. Clone your new repo
3. Copy all files from this folder into it
4. Commit → Push

**Option B — Git command line:**
```bash
cd "100 Days Trading Challenge"
git init
git add .
git commit -m "Initial commit: 100 Day Trading Dashboard"
git remote add origin https://github.com/YOUR_USERNAME/100-day-trading-challenge.git
git branch -M main
git push -u origin main
```

### Step 3: Enable GitHub Pages
1. In your GitHub repo → **Settings** → **Pages** (left sidebar)
2. Source: **GitHub Actions**
3. The workflow (`.github/workflows/deploy.yml`) will auto-deploy on every push

### Step 4: Your Live URLs
After deployment (takes ~2 minutes):
- **Landing page:** `https://yourusername.github.io/100-day-trading-challenge/landing.html`
- **Dashboard:** `https://yourusername.github.io/100-day-trading-challenge/index.html`

---

## PART 3 — Make landing.html Your Homepage (Optional)

Rename `landing.html` to `landing_page.html` and `index.html` stays as-is
OR create an `index.html` redirect:

If you want the landing page to show first when someone visits your link:
1. Rename your current `index.html` → `dashboard.html`
2. Rename `landing.html` → `index.html`
3. Update the "Open Dashboard" links in landing.html to point to `dashboard.html`

---

## File Summary

| File | Purpose |
|------|---------|
| `index.html` | Main trading dashboard (all features) |
| `landing.html` | Marketing landing page |
| `firebase-config.js` | Firebase config reference (not used directly) |
| `.github/workflows/deploy.yml` | Auto-deploy to GitHub Pages |
| `SETUP_GUIDE.md` | This guide |

---

## Features in index.html

- ✅ Light / Dark mode toggle
- ✅ Daily Focus Quiz (Prequiz required before logging)
- ✅ Transaction Edit & Delete (with auto-recalculation)
- ✅ PDF Report download
- ✅ CSV Export
- ✅ Dashboard Screenshot (PNG)
- ✅ Daily Trading Rules Checklist (10 rules + add custom)
- ✅ Account Health Score
- ✅ Compounding projections
- ✅ Google Sign-In via Firebase Auth
- ✅ Cloud data sync via Firestore
- ✅ Falls back to localStorage if not signed in

---

Built by Khizar | LinkedIn: https://linkedin.com/in/khizar226 | Instagram: @khizar226
