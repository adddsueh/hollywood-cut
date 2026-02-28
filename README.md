<div align="center">

# 🎬 Hollywood Cut

**Jazz & Western Edition**

*AI-Powered Cinematic Set Photo Generator — Powered by Google Gemini Imagen*

[![Deploy to GitHub Pages](https://img.shields.io/badge/Deploy-GitHub%20Pages-blue?logo=github)](https://adddsueh.github.io/HollywoodCut/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Built with Gemini](https://img.shields.io/badge/AI-Google%20Gemini-4285F4?logo=google)](https://aistudio.google.com/)

</div>

---

## ✨ What is this?

**Hollywood Cut** is a pure front-end web application. Upload a portrait photo, pick a movie title, and Gemini Imagen AI will generate a hyper-realistic behind-the-scenes set photo — placing you right on the film set, dressed in costume, Kodak Vision3 film grain and all.

No server. No backend. No API key ever leaves your browser.

---

## 🚀 Features

- 🎭 Portrait upload → AI-generated cinematic set photo
- 🎞 Customizable aspect ratios (9:16, 3:4, 4:3, 16:9)
- 📷 Depth-of-field control (f/1.2 / f/4 / f/11)
- ✍️ Editable director's prompt
- 💾 One-click image download
- 🔑 API key stored only in `localStorage` — never sent anywhere else
- 📱 Fully responsive layout

---

## 🔐 Security & Privacy

| Concern | Status |
|---------|--------|
| API Key hardcoded in source | ✅ Never — entered at runtime by user |
| API Key sent to any third-party server | ✅ Never — goes directly to Google API |
| API Key stored in repo / build | ✅ Never — lives only in `localStorage` |
| Uploaded images stored on a server | ✅ Never — processed entirely in-browser |

> **Note:** `localStorage` is browser-scoped. Clearing browser data or clicking **RESET** will remove the key immediately.

---

## 🛠 Getting Started (Local Development)

### Prerequisites

- A modern browser (Chrome / Edge recommended)
- A [Google Gemini API Key](https://aistudio.google.com/app/apikey) with **Imagen** model access
- `Node.js` (optional — only needed for the local dev server)

### 1. Clone the repo

```bash
git clone https://github.com/adddsueh/HollywoodCut.git
cd HollywoodCut
```

### 2. Copy the environment example (optional reference)

```bash
cp .env.example .env
# Edit .env and add your key — for documentation purposes only.
# The app reads the key from the browser UI, not from .env.
```

### 3. Run locally

**Option A — Node.js `http-server` (recommended):**

```bash
npx http-server . -p 8080 -c-1
# Then open http://localhost:8080
```

**Option B — Python:**

```bash
python -m http.server 8080
# Then open http://localhost:8080
```

**Option C — VS Code Live Server:**

Install the [Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) extension and click **Go Live**.

---

## ☁️ Deployment

### GitHub Pages (Recommended — Free & Zero Config)

1. Push the repo to GitHub.
2. Go to **Settings → Pages**.
3. Set **Source** to `Deploy from a branch`.
4. Select **Branch: `main`** and **Folder: `/ (root)`**.
5. Click **Save** — your site will be live at:

```
https://adddsueh.github.io/HollywoodCut/
```

> No build step needed. This is a pure static site.

### Vercel

```bash
npm i -g vercel
vercel --prod
```

Vercel auto-detects a static site — no config file required.

### Netlify

1. Drag & drop the project folder into [Netlify Drop](https://app.netlify.com/drop).
2. Done. Your site is live instantly.

---

## 🔄 GitHub Actions — Auto Deploy to GitHub Pages

Create `.github/workflows/deploy.yml` in your repo (already included):

```yaml
name: Deploy to GitHub Pages

on:
  push:
    branches: [main]

jobs:
  deploy:
    runs-on: ubuntu-latest
    permissions:
      contents: read
      pages: write
      id-token: write
    environment:
      name: github-pages
    steps:
      - uses: actions/checkout@v4
      - uses: actions/configure-pages@v5
      - uses: actions/upload-pages-artifact@v3
        with:
          path: '.'
      - uses: actions/deploy-pages@v4
```

After enabling **GitHub Pages** with **GitHub Actions** as source, every push to `main` triggers an automatic deploy.

---

## 📁 Project Structure

```
HollywoodCut/
├── index.html          # Main app (self-contained React via Babel CDN)
├── default-cast.png    # Default placeholder portrait
├── css/
│   └── style.css       # Custom styles (scrollbar, noise bg, typography)
├── js/
│   ├── app.jsx         # Full React app (Vite-ready version)
│   └── geminiService.js # Gemini API service layer
├── .env.example        # Environment variable reference (no secrets)
├── .gitignore          # Excludes .env, node_modules, etc.
├── .github/
│   └── workflows/
│       └── deploy.yml  # Auto-deploy to GitHub Pages on push
└── README.md
```

---

## 🎨 Tech Stack

| Layer | Technology |
|-------|-----------|
| UI Framework | React 18 (via CDN Babel, no build step) |
| Styling | Tailwind CSS (CDN) |
| AI | Google Gemini Imagen 3 (`imagen-3.0-generate-002`) |
| Fonts | Google Fonts — Playfair Display, Rye, Inter |
| Hosting | GitHub Pages / Vercel / Netlify |

---

## ⚙️ Environment Variables Reference

| Variable | Required | Description |
|----------|----------|-------------|
| `GEMINI_API_KEY` | Runtime (browser UI) | Your Google Gemini API key |
| `PORT` | Optional | Local dev server port (default: `8080`) |

See [`.env.example`](.env.example) for the template.

---

## 📜 License

MIT License — see [LICENSE](LICENSE) for details.

---

<div align="center">
Made with 🎬 and a lot of film grain.
</div>
