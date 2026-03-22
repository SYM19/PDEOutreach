# PDEOutreach 🧬

**Cancer science, made for everyone.**  
癌症科学，人人可懂。

> A public science education platform translating the mathematics of [PDEOncology](https://pdeoncology.com) — a reaction-diffusion PDE model of drug penetration in solid tumours — into interactive, multilingual experiences for patients, families, and the general public.

🌐 **Live site:** [pdeoutreach.com](https://pdeoutreach.com)  
🔬 **Research companion:** [pdeoncology.com](https://pdeoncology.com)  
📄 **License:** [CC BY-NC 4.0](./LICENSE)

---

## Overview

The gap between what cancer researchers know and what patients understand is large and consequential. Most people are unaware that chemotherapy can fail not because of drug resistance, but because the drug physically cannot penetrate deep enough into solid tumours to reach the cells it needs to kill — a problem modelled by reaction-diffusion partial differential equations.

PDEOutreach makes this science accessible. It runs a simplified PDE solver entirely in the browser, visualises drug concentration gradients as real-time heatmaps, and contextualises the physics within clinically meaningful outcomes (survival rates, screening guidelines, biomarker testing). The platform is designed for audiences with no mathematical background, with full trilingual support (English / 中文 / Deutsch).

---

## Features

### Five Interactive Modules

| Module | Content |
|--------|---------|
| **Why Drugs Fail** | Tumour microenvironment barriers (IFP, ECM density, stroma); live PDE simulation with drug and tumour type selection; drug diffusion coefficient comparison |
| **Early Detection** | Non-linear collapse of drug coverage with tumour size; cancer-specific screening guidelines (breast, colorectal, lung, cervical, prostate, pancreatic); draggable size-survival simulator |
| **Lifestyle & Risk** | Quantified effects of smoking, BMI, inflammation, exercise, diet, sleep, and stress on diffusion coefficient D; personalised microenvironment profile with simulated heatmap |
| **Precision Medicine** | HER2/biomarker testing; molecular weight vs penetration depth; PD-L1, CAR-T, ADC explainers; side-by-side patient comparison simulation |
| **Journal** | Plain-language summaries of high-impact oncology research (CA, Nature Reviews Cancer, Lancet Oncology, Cancer Discovery) |

### Browser-Based PDE Engine
A finite-difference reaction-diffusion solver runs entirely client-side in vanilla JavaScript — no server, no dependencies. Models the equation:

```
∂C/∂t = ∇·(D∇C) − λC − k·ρ·C
```

with spatially varying D fields, tumour geometry, and drug-specific parameters for 20+ agents.

### Progressive Quiz System
Each module opens with a multiple-choice question. Correct answers unlock two further questions of increasing scientific depth — covering IFP mechanics, diffusion coefficients, biomarker testing, and CAR-T biology.

### Personalised Risk Profiling
The Lifestyle module generates an individualised tumour microenvironment profile by combining eight lifestyle parameters into a composite D modifier, displayed alongside a patient-specific drug penetration simulation.

### Trilingual Support (EN / 中文 / DE)
Complete three-language coverage with a custom `applyLang()` i18n system — no third-party localisation library. URL parameter `?lang=zh` or `?lang=de` for direct linking.

### Charity Integration
Links to verified childhood cancer charity partners across three regions — international, UK, and China — with a dedicated donation modal.

---

## Technical Implementation

| Component | Details |
|-----------|---------|
| **Frontend** | Pure HTML / CSS / JS — zero dependencies, zero build tools |
| **PDE solver** | Custom finite-difference engine; explicit Euler time-stepping; spatially varying diffusivity; 80×80 grid; chunked async execution to prevent UI blocking |
| **Visualisation** | Canvas-based magma colormap heatmap; real-time tumour boundary overlay |
| **i18n** | Custom `applyLang()` system; ~400 translated strings across EN / 中文 / DE |
| **Analytics** | Plausible Analytics (privacy-preserving, GDPR-compliant); Baidu Tongji for Chinese audience |
| **Hosting** | GitHub Pages — single-file deployment |
| **Fonts** | Space Mono + Inter (Google Fonts) |

---

## Project Structure

```
PDEOutreach/
├── index.html        # Entire platform — single self-contained file
├── LICENSE           # CC BY-NC 4.0
└── README.md
```

The platform is intentionally single-file: easy to audit, fork, and deploy with zero configuration. The complete PDE engine, i18n system, quiz logic, and simulation renderer are contained within one HTML document (~250 KB).

---

## Running Locally

No build step required:

```bash
git clone https://github.com/SYM19/PDEOutreach.git
cd PDEOutreach
open index.html
```

Or with a local server:

```bash
npx serve .
# → http://localhost:3000
```

---

## Scientific Basis

The drug penetration model is grounded in published oncology physics literature:

- **Diffusion coefficient D** is drug- and tissue-specific, ranging from D ≈ 0.20 (cisplatin in breast tissue) to D ≈ 0.005 (trastuzumab in pancreatic stroma) — reflecting the ~500× molecular weight difference between small molecules and antibodies
- **Interstitial fluid pressure (IFP)** is modelled as a convective term opposing inward diffusion, consistent with Darcy's law applied to tumour microenvironments
- **Stromal density** in pancreatic cancer reduces effective D by up to 75% relative to breast cancer, consistent with published diffusion measurements
- **Drug coverage** exhibits a highly non-linear collapse with tumour radius — from >70% at Stage I to <10% at Stage III — demonstrating why early detection produces disproportionate survival benefit

The companion research platform [PDEOncology](https://pdeoncology.com) implements the full model with AI-assisted parameter extraction, dual-drug comparison, and a 21-drug database.

---

## Roadmap

- [ ] Real patient stories (4 sections, currently placeholder)
- [ ] Charity donation links (pending partnership confirmation)
- [ ] Drug database expansion: 21 → 50+ entries (in progress)
- [ ] Childhood cancer dedicated module
- [ ] Potential academic publication — target journals: *Journal of Emerging Investigators*, *Young Scientists Journal*

---

## Related Project

**PDEOncology** — research-grade PDE drug penetration simulator  
Full parameter control · dual-drug comparison · AI parameter extraction · 21-drug database · dark academic UI  
→ [pdeoncology.com](https://pdeoncology.com) · [GitHub](https://github.com/SYM19/tumor-drug-penetration-model)

---

## Team

| | |
|---|---|
| **Yumeng S.** | Platform development, Chinese content, UX — NSFZ IB (exchange, Washington State) |
| **Tracey Y.** | Literature research, drug database, English/German content — Wycombe Abbey, UK |

*Built independently by two secondary school students as a science communication and public health initiative.*

---

## License

Licensed under [CC BY-NC 4.0](./LICENSE).  
Free to share and adapt for non-commercial purposes with attribution.

> *Educational use only. Not medical advice. Always consult a qualified clinician.*
