# JUVO — Official Website

**Shop Smarter. Decide Faster.**

AI-powered shopping assistant landing page for myJUVO LLC.

---

## 🚀 Deploy to Vercel

### Prerequisites
- [Node.js](https://nodejs.org/) installed (v18+)
- [Vercel CLI](https://vercel.com/docs/cli) installed globally
- A GitHub account and Vercel account

---

### Step 1 — Initialize Git Repo

```bash
cd juvo-website
git init
git add .
git commit -m "Initial commit — JUVO website"
```

### Step 2 — Push to GitHub

```bash
# Create a new repo on GitHub (github.com/new), then:
git remote add origin https://github.com/YOUR_USERNAME/juvo-website.git
git branch -M main
git push -u origin main
```

### Step 3 — Deploy with Vercel CLI

```bash
# Install Vercel CLI if you haven't already
npm install -g vercel

# Deploy
vercel

# Follow the prompts:
# - Link to your Vercel account
# - Set up project (use defaults)
# - Framework: Other
# - Root directory: ./
```

### Step 4 — Connect Custom Domain

1. Go to your project on [vercel.com](https://vercel.com)
2. Click **Settings → Domains**
3. Add your custom domain (e.g. `myjuvo.com`)
4. Follow Vercel's DNS instructions to point your domain:
   - Add a **CNAME** record: `www` → `cname.vercel-dns.com`
   - Add an **A** record: `@` → `76.76.21.21`
5. Wait for DNS propagation (usually 5–30 minutes)

---

## 📁 Project Structure

```
juvo-website/
├── index.html        ← All pages (SPA with JS routing)
├── css/
│   └── style.css     ← All styles
├── js/
│   └── main.js       ← Interactivity, navigation, animations
├── vercel.json       ← Vercel deployment config
└── README.md
```

## 🌐 Pages

| Page | Route | Description |
|------|-------|-------------|
| Home | `/` | Hero, waitlist, stats, how-it-works |
| Demo | `/` (tab) | Features explanation + live demo button |
| Investors | `/` (tab) | Executive summary + pitch deck slides |

---

## 🎨 Design Notes

- **Dark theme** — deep navy background with electric teal (#0FD4C0) accents
- **Typography** — Syne (headings) + DM Sans (body) via Google Fonts
- **3D Hero** — CSS 3D animated orb with mouse-tracking parallax
- **Animations** — scroll-triggered reveals, counter animations, floating cards
- **Waitlist** — email capture (mock — connect to your backend or Mailchimp)

---

## 🔌 Connecting the Real Waitlist

To make the waitlist functional, replace the mock in `js/main.js`:

```javascript
// In handleWaitlist(), replace:
console.log('Waitlist signup:', email);

// With a real API call, e.g. Mailchimp, ConvertKit, or your own endpoint:
await fetch('/api/waitlist', {
  method: 'POST',
  headers: { 'Content-Type': 'application/json' },
  body: JSON.stringify({ email })
});
```

---

© 2025 myJUVO LLC. All rights reserved.
