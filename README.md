# PDEOutreach 🧬

**Cancer science, made for everyone.**  
癌症科学，人人可懂。

> A public science education platform that turns the mathematics behind [PDEOncology](https://pdeoncology.com) into interactive experiences — no equations, no textbooks required.

🌐 **Live site:** [pdeoutreach.com](https://pdeoutreach.com)  
🔬 **Research tool:** [pdeoncology.com](https://pdeoncology.com)  
📄 **License:** [CC BY-NC 4.0](./LICENSE)

---

## What is PDEOutreach?

Most people know chemotherapy can fail — but few know *why*. The answer is often physical: drugs simply cannot penetrate deep enough into solid tumours to reach the cancer cells that need killing.

PDEOutreach translates this research into four interactive modules anyone can explore, with full Chinese/English bilingual support.

---

## Features

### 📚 Four Interactive Tabs

| Tab | What you learn |
|-----|---------------|
| **Why Drugs Fail** | How tumour microenvironments physically block chemotherapy, with a live PDE simulation |
| **Early Detection** | How tumour size collapses drug coverage — drag a slider and watch survival rates change |
| **Lifestyle & Risk** | How smoking, BMI, inflammation and exercise affect your tumour microenvironment |
| **Precision Medicine** | Why the same drug works differently for different patients — HER2, molecular weight, tumour type |

### 🧪 Interactive Simulations
Each tab runs a simplified reaction-diffusion PDE model in the browser (no server required), visualised as a real-time heatmap.

### 🧠 Quizzes
Every section opens with a multiple-choice question to challenge assumptions before revealing the science.

### 👤 Personalised Risk Profile
The Lifestyle tab generates a personalised microenvironment profile based on five lifestyle sliders, with a simulated drug penetration heatmap.

### 🌏 Bilingual (中/EN)
Full Chinese and English support throughout — toggle with one click. Built for both international and Chinese-speaking audiences.

### ❤️ Charity Donation Modal
Links to four partner cancer charities — three international, one China-based — with a clean modal UI.

### 📱 Share Buttons
GitHub, WeChat (copy link), 小红书, B站, Instagram, Twitter/X — one bar per tab.

---

## Tech Stack

| | |
|---|---|
| **Frontend** | Pure HTML / CSS / JS — zero dependencies, zero build tools |
| **Simulation engine** | Custom PDE solver (reaction-diffusion, finite difference) written in vanilla JS |
| **Hosting** | GitHub Pages |
| **Fonts** | Space Mono + Inter (Google Fonts) |
| **Localisation** | Custom `applyLang()` i18n system, no library |

---

## Project Structure

```
PDEOutreach/
├── index.html        # Entire site — single file
├── LICENSE           # CC BY-NC 4.0
└── README.md
```

The site is intentionally a single-file build — easy to fork, audit, and deploy with zero configuration.

---

## Running Locally

No build step needed. Just open the file:

```bash
git clone https://github.com/SYM19/PDEOutreach.git
cd PDEOutreach
open index.html       # or double-click in file explorer
```

Or serve it with any static server:

```bash
npx serve .
# → http://localhost:3000
```

---

## Roadmap

- [ ] Add real patient stories (4 placeholders currently)
- [ ] Fill in charity donation links once confirmed
- [ ] Expand drug database (21 → 50+ entries, in progress with Tracey)
- [ ] Launch on 小红书 / B站 / Instagram
- [ ] Mobile layout refinements

---

## Related Project

**PDEOncology** — the research-grade companion tool this site is based on.  
Runs the same PDE models with full parameter control, dual-drug comparison, AI parameter extraction, and a 21-drug database.  
→ [pdeoncology.com](https://pdeoncology.com) · [GitHub](https://github.com/SYM19/tumor-drug-penetration-model)

---

## Team

| | |
|---|---|
| **Yumeng S.** | Technical development — NSFZ IB |
| **Tracey Y.** | Literature research & drug database — Wycombe Abbey, UK |

---

## License

This project is licensed under [CC BY-NC 4.0](./LICENSE).  
You are free to share and adapt the material for non-commercial purposes, with attribution.

> *Educational use only — not medical advice.*
