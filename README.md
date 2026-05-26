# ⚡ AnimeForge — AI Anime Image Generator

> Generate stunning **2D flat**, **3D cinematic**, and **hybrid fusion** anime art from text prompts using Hugging Face's free inference API.

![AnimeForge Banner](https://img.shields.io/badge/AnimeForge-AI%20Powered-8b5cf6?style=for-the-badge&logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI+PHBhdGggZmlsbD0id2hpdGUiIGQ9Ik0xMiAyQzYuNDggMiAyIDYuNDggMiAxMnM0LjQ4IDEwIDEwIDEwIDEwLTQuNDggMTAtMTBTMTcuNTIgMiAxMiAyem0tMiAxNWwtNS01IDEuNDEtMS40MUwxMCAxNC4xN2w3LjU5LTcuNTlMMTkgOGwtOSA5eiIvPjwvc3ZnPg==)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![HTML](https://img.shields.io/badge/Built%20with-HTML%2FCSS%2FJS-orange)](.)
[![HuggingFace](https://img.shields.io/badge/API-Hugging%20Face-FFD21E)](https://huggingface.co)

---

## ✨ Features

| Feature | Details |
|---|---|
| 🎨 **2D Flat Anime** | Classic anime cel-shading with Anything V5 |
| 💎 **3D Cinematic** | Photorealistic anime renders with Mo-Di Diffusion |
| ⚡ **Hybrid Fusion** | Semi-realistic blends with Waifu Diffusion |
| 🎛️ **Full Controls** | Steps, CFG scale, sampler, seed, aspect ratio |
| 🖼️ **Gallery** | Save & browse your generated artwork locally |
| 📋 **Prompt Tools** | Negative prompts, quick-fill suggestions |
| ⬇️ **Download** | Export generated images directly |
| 🎭 **Demo Mode** | Try without an API key using placeholder images |

---

## 🚀 Quick Start

### Option 1 — Open Locally (Zero Setup)
```bash
git clone https://github.com/YOUR_USERNAME/animeforge.git
cd animeforge
open index.html   # macOS
# or double-click index.html on Windows/Linux
```

### Option 2 — Deploy to GitHub Pages
1. Fork this repo
2. Go to **Settings → Pages → Source: main branch / root**
3. Your site will be live at `https://YOUR_USERNAME.github.io/animeforge`

### Option 3 — Serve Locally
```bash
npx serve .
# or
python -m http.server 8080
```

---

## 🔑 API Setup

AnimeForge uses the **Hugging Face Inference API** (free tier):

1. Create a free account at [huggingface.co](https://huggingface.co)
2. Go to [Settings → Access Tokens](https://huggingface.co/settings/tokens)
3. Create a **New Token** (type: `read`)
4. Paste it into AnimeForge when prompted

> **Free tier**: ~1,000 requests/month · No credit card required

---

## 🎨 Style Guide

### 2D Flat Anime
Best for: Character portraits, chibi, slice-of-life, magical girls
- Model: `Linaqruf/anything-v5`
- Auto-adds: `2D anime art style, flat shading, cel shading, clean lineart`

**Example prompts:**
```
silver hair magical girl, starry night, cherry blossoms, soft glow
samurai warrior, neon city rain, dramatic pose
chibi fox spirit, misty mountains, vibrant colors
```

### 3D Cinematic
Best for: Action scenes, dramatic portraits, fantasy environments
- Model: `nitrosocke/mo-di-diffusion`
- Auto-adds: `3D CGI anime, cinematic rendering, volumetric lighting, octane render, 8k`

**Example prompts:**
```
cinematic 3D anime portrait, dramatic lighting, bokeh background
detailed 3D render, fantasy armor, glowing runes
realistic anime warrior, studio lighting, heroic pose
```

### Hybrid Fusion
Best for: Semi-realistic art, painterly portraits, stylized realism
- Model: `hakurei/waifu-diffusion`
- Auto-adds: `hybrid anime art, semi-realistic, painterly, 2.5D`

**Example prompts:**
```
semi-realistic anime girl, watercolor texture, soft lighting
stylized realism, anime proportions, detailed eyes
2.5D anime scene, depth of field, cinematic composition
```

---

## ⚙️ Settings Reference

| Setting | Range | Description |
|---|---|---|
| **Quality Steps** | 10–50 | More steps = higher quality, slower |
| **CFG Scale** | 1–15 | How strictly AI follows your prompt (7 = balanced) |
| **Sampler** | 4 options | DPM++ 2M Karras recommended for anime |
| **Seed** | -1 to max | -1 = random, fixed seed = reproducible |
| **Aspect Ratio** | 1:1, 2:3, 3:2, 9:16, 16:9 | Output image dimensions |

---

## 📁 Project Structure

```
animeforge/
├── index.html          # Main app (single-file, no build step)
├── README.md           # This file
├── LICENSE             # MIT License
└── docs/
    └── screenshots/    # App screenshots
```

---

## 🛠️ Tech Stack

- **Frontend**: Pure HTML/CSS/JavaScript (no frameworks, no build tools)
- **AI API**: [Hugging Face Inference API](https://huggingface.co/inference-api)
- **Storage**: `localStorage` for gallery & API key
- **Fonts**: Orbitron + Syne (Google Fonts)

---

## 🔧 Extending the Project

### Add More Models
Edit the `MODELS` object in `index.html`:
```javascript
const MODELS = {
  '2d':     { id: 'Linaqruf/anything-v5', label: 'Anything V5' },
  '3d':     { id: 'nitrosocke/mo-di-diffusion', label: 'Mo-Di' },
  'hybrid': { id: 'hakurei/waifu-diffusion', label: 'Waifu Diffusion' },
  // Add yours:
  'custom': { id: 'YOUR_USER/YOUR_MODEL', label: 'Custom Model' }
};
```

### Add New Style Tabs
```javascript
// 1. Add to MODELS
// 2. Add HTML button with class style-tab tab-custom
// 3. Add prompts to SUGGESTIONS object
// 4. Add prefix to STYLE_PREFIX object
```

### Use a Backend (for rate limit bypass)
Replace the fetch call in `generate()` with your own API endpoint to proxy requests without exposing your token.

---

## 📸 Screenshots

> Add your screenshots to `docs/screenshots/` and link them here

---

## 🤝 Contributing

1. Fork the project
2. Create a feature branch: `git checkout -b feature/my-feature`
3. Commit: `git commit -m 'Add some feature'`
4. Push: `git push origin feature/my-feature`
5. Open a Pull Request

---

## 📄 License

MIT © 2025 — Free to use, modify, and distribute.

---

## 🌟 Roadmap

- [ ] Image-to-image transformation
- [ ] LoRA style mixing
- [ ] Batch generation (4 images at once)
- [ ] Inpainting / outpainting
- [ ] Style strength slider
- [ ] Prompt history & favorites
- [ ] Share generated images
- [ ] Mobile PWA support

---

*Built with ❤️ for the anime art community*
