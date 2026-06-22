# The CPA Firm Growth Offer — Landing Page

**Aero Eagle Limited** · AI-Assisted Practice Solutions for Hong Kong CPA Firms

---

## Overview

A single-file, zero-dependency landing page built for Hong Kong CPA firm proprietors. The page follows Alex Hormozi's **$100M Grand Slam Offer** framework, structured around a single conversion goal: booking a free 20-minute Discovery Call via Calendly.

**Design principle:** 三秒看到自己的痛。三分鐘看到解決方案。一個按鈕預約通話。  
*(3 seconds to see the pain. 3 minutes to see the solution. One button to book the call.)*

**Live file:** `cpa-growth-offer.html`

---

## Target Audience

| Attribute | Detail |
|---|---|
| **Buyer** | Sole proprietor of a one-CPA Hong Kong accounting firm |
| **Firm size** | 100–200 SME clients |
| **Key pain** | Staff turnover, 1,550 hrs/year of repetitive pre-work, dormant revenue |
| **Mindset** | Treats expenditure as expense — must be reframed as investment |
| **Language** | English (page), Cantonese (WhatsApp templates in service) |

---

## Page Structure

### Main Flow (12 sections)

| # | Section | Hormozi Element | Key Message |
|---|---|---|---|
| S1 | Hook Hero | Problem Awareness | *"Your best staff member is going to resign. Here is how to make sure it does not matter."* |
| S2 | Are You This Firm? | Buyer Qualification | 4-point self-identification checklist |
| S3 | HK$178,000 | Cost of Inaction | Monthly hidden cost — one number, nothing else |
| S4 | Staff Problem | Deepest Pain | Staff turnover as knowledge and revenue crisis |
| S5 | Three Pains | Problem Agitation | 1,550 hrs · 1,500 touchpoints · HK$1.5M dormant |
| S6 | 12 Months From Now | Dream Outcome | 6 concrete results, one sentence each |
| S7 | New Associate | Expense → Investment Reframe | Side-by-side: hire vs. this system |
| S8 | The CPA Growth System | Value Stack | 3 systems with outcome-first language |
| S9 | The Numbers | ROI Proof | 4 stats + Before/After table |
| S10 | Industry Context | Social Proof | Industry stats + case study placeholders |
| S11 | Zero Risk | Risk Reversal | 4 guarantees incl. HKICPA §140 compliance |
| S12 | Book Your Call | Call to Action | Single Calendly button + scarcity context |

### Appendix (5 collapsible sections)

| ID | Content |
|---|---|
| A1 | The 3 Audit Pre-Work Tasks — technical detail |
| A2 | Complete Value Stack & Bonus Breakdown |
| A3 | Client Data Confidentiality Framework (HKICPA §140) |
| A4 | AI Platform Independence & Model Selection |
| A5 | Offer Terms, Scarcity & Next Steps |

---

## Technical Specification

### Architecture

```
cpa-growth-offer.html          # Single self-contained file
├── <style>                    # All CSS (~530KB incl. embedded image)
│   ├── CSS custom properties  # Design tokens (colours, spacing)
│   ├── Mobile base styles     # 320px+ default
│   ├── @media (min-width: 580px)   # Tablet
│   ├── @media (min-width: 768px)   # Desktop
│   └── @media (min-width: 1024px)  # Wide desktop
└── <body>                     # All HTML (~35KB)
    ├── <nav>                  # Sticky navbar with persistent CTA
    ├── 12 × <section>        # Main conversion flow
    ├── <section> appendix     # 5 × <details> collapsible
    └── <footer>
```

### Dependencies

**None.** The file is entirely self-contained:

- ✅ Zero JavaScript
- ✅ Zero external CSS frameworks
- ✅ Zero web fonts (system font stack: Calibri → Segoe UI → Arial)
- ✅ Zero external images (HK wallpaper base64-encoded inline)
- ✅ Zero CDN dependencies
- ✅ One external link: Calendly booking URL

### File Size

| Component | Size |
|---|---|
| HK wallpaper (base64 JPEG) | ~258KB |
| CSS | ~268KB |
| HTML content | ~35KB |
| **Total** | **~576KB** |

> The image is compressed from the original 1536×1024 PNG (~3MB) to a 1350×900 JPEG at quality 82 before base64 encoding.

### Responsive Breakpoints

| Breakpoint | Target | Layout changes |
|---|---|---|
| **320px+** (base) | Mobile | Single column, full-width buttons, stacked grids |
| **≥ 580px** | Tablet | 2-column grids, horizontal pills, side-by-side stats |
| **≥ 768px** | Desktop | Centred containers (760px/980px), horizontal pricing box, 4-column ROI |
| **≥ 1024px** | Wide | Maximum heading sizes |

### Accessibility

- `prefers-reduced-motion` respected (no transitions)
- `scroll-behavior: smooth` disabled for reduced-motion users
- Semantic HTML5 elements (`<nav>`, `<section>`, `<details>`, `<summary>`, `<footer>`)
- Touch-friendly: all interactive elements ≥ 44px tap target on mobile
- Horizontal scroll with `-webkit-overflow-scrolling: touch` for tables on iOS

---

## Design System

### Colour Palette

| Token | Hex | Usage |
|---|---|---|
| `--navy` | `#1E2761` | Primary text, headings |
| `--navyDk` | `#141B4D` | Dark backgrounds (hero, CTA, navbar) |
| `--navyMd` | `#1A2550` | Card backgrounds on dark sections |
| `--gold` | `#C9A84C` | Brand accent, section borders |
| `--goldLt` | `#F0D080` | Secondary accent text on dark |
| `--teal` | `#0D9488` | Primary CTA buttons, System 01 |
| `--coral` | `#E05C3A` | Warnings, eyebrows, System 03 |
| `--red` | `#DC2626` | HK$178,000 impact slide, scarcity |
| `--amber` | `#D97706` | System 02, secondary accents |
| `--green` | `#16A34A` | After-column in tables, positive outcomes |
| `--ice` | `#EFF3F8` | Light card backgrounds |
| `--greyLt` | `#F8FAFC` | Alternating section backgrounds |

### Typography

| Role | Font | Size |
|---|---|---|
| Display / Headings | Cambria, Times New Roman (serif) | `clamp(24px–52px)` |
| Body | Calibri, Segoe UI, Arial (system sans) | 16px base |
| Labels / Eyebrows | Same sans, uppercase + letter-spacing | 10–12px |

### Key Components

- **Sticky navbar** — always-visible booking CTA
- **Hero** — HK wallpaper with layered gradient overlay for text legibility
- **Qualify cards** — 4-point buyer self-identification
- **Pain cards** — large stat number + label + detail
- **Compare table** — hire vs. system, horizontally scrollable on mobile
- **Offer items** — outcome-first language, system name as subtitle
- **Pricing box** — value / setup / retainer / savings badge
- **Guarantee cards** — 4 risk-reversal points incl. HKICPA §140
- **`<details>` appendix** — 5 collapsible sections, default closed

---

## Services Described

### 1. Annual Audit Pre-Work Engine · HK$22,000
Automates three zero-judgement tasks that consume 1,150–1,950 staff hours per year:
- TB → Proforma FS mapping (3–5 hrs/client → 20 mins)
- Profits Tax computation first draft (2–4 hrs/client → 15 mins)
- Audit confirmation letters batch production (2–3 hrs/client → 5 mins)

### 2. Compliance Calendar & CRM · HK$22,000
- 1,500 client compliance touchpoints automated annually
- WhatsApp reminders in Cantonese
- Zero missed deadlines across 150 clients

### 3. Dormant Client Recovery Engine · HK$15,000
- Re-engages 100+ dormant leads from existing contact list
- Target: 5–8 new client sign-ups per quarter
- No cold calls required

**Compatible accounting software:** Xero, QuickBooks, MYOB, Excel

---

## Customisation Guide

### Update the Calendly Link

Search and replace all instances of:
```
https://calendly.com/aero-eagle/discovery
```

### Update Contact Details

```html
<!-- Footer -->
<a href="mailto:hello@aero-eagle.com">hello@aero-eagle.com</a>
```

### Update Pricing

All prices appear inline in the HTML. Search for `HK$22,000`, `HK$28,000`, `HK$6,000` etc.

### Replace the Hero Image

To swap the HK wallpaper, replace the base64 string in the CSS:

```css
.hook-section {
  background:
    linear-gradient(...),
    url('data:image/jpeg;base64,YOUR_BASE64_HERE') center 30%/cover no-repeat;
}
```

To generate a new base64 string from a file:
```python
import base64
with open("your-image.jpg", "rb") as f:
    print(base64.b64encode(f.read()).decode())
```

> **Tip:** Compress the image to JPEG quality 80–85 at max 1400px wide before encoding. Target under 300KB base64 to keep total page size reasonable.

### Add Real Testimonials

Replace the placeholder proof cards in Section S10:

```html
<div class="proof-card">
  <div class="proof-card__quote">"Your actual client quote here."</div>
  <div class="proof-card__tag">
    Firm name · City · <strong>Year enrolled</strong>
  </div>
</div>
```

---

## Deployment

### Option 1: Cloudflare Pages (Recommended)

1. Push this repository to GitHub
2. Log in to [Cloudflare Pages](https://pages.cloudflare.com)
3. Connect your GitHub repository
4. Set build output directory to `/` (or wherever `cpa-growth-offer.html` lives)
5. Rename `cpa-growth-offer.html` to `index.html` for root URL serving

### Option 2: GitHub Pages

1. Go to repository **Settings → Pages**
2. Set source to `main` branch, `/ (root)` folder
3. Rename `cpa-growth-offer.html` to `index.html`
4. Site available at `https://yourusername.github.io/repo-name/`

### Option 3: Any Static Host

Upload `cpa-growth-offer.html` (renamed to `index.html`) to any static file host:
- Netlify Drop
- Vercel
- AWS S3 + CloudFront
- Any web hosting with file upload

No build step. No server-side processing. No database. Just one file.

---

## Development Notes

### PPT → Landing Page Pipeline

This landing page was produced as part of a broader asset suite:

| Asset | File | Tool |
|---|---|---|
| Main sales deck | `HK_CPA_Grand_Slam_Offer_v3.pptx` | pptxgenjs |
| Print version | `HK_CPA_Grand_Slam_Offer_v3_print.pptx` | python-pptx |
| Landing page | `cpa-growth-offer.html` | Hand-coded HTML/CSS |
| 21-day blueprint | `21Day_AI_Solopreneur_Blueprint.pptx` | pptxgenjs |

### Design Decisions

**Why no JavaScript?**
The target audience includes sceptical, time-poor professionals. Page load speed and reliability matter. A pure HTML/CSS page loads instantly on any connection, requires no runtime dependencies, and cannot break due to a failed script.

**Why base64 inline image?**
Eliminates one HTTP request, ensures the hero image always loads (no broken image on slow connections), and makes the file fully portable — one file is the entire deployment.

**Why system fonts?**
Calibri and Cambria ship with Microsoft Office — the CPA's daily environment. Using the same typefaces creates unconscious familiarity and trust. No web font latency.

**Why `<details>` for appendix?**
Hormozi principle: keep the main flow focused on the single conversion goal. All persuasion evidence lives in the appendix, collapsed by default, available on demand. The buyer who wants evidence can find it; the buyer who is ready to book is not slowed down by it.

---

## Prompt Attribution

This landing page was built using the following reusable prompt:

```
Prompt ID:    DECK_REVIEW_PRO_SERVICES_HK_CPA
Version:      v1.0
Created:      2026-06-22
Author:       Ambrose Cheng / Aero Eagle Limited
Category:     Sales & Pitch Strategy
Tags:         deck review, Hormozi, CPA, HK, buyer persona,
              professional services, Grand Slam Offer
Reusable for: Any professional services firm pitch to a
              time-poor, sceptical, traditional buyer
```

---

## Ecclesiastes 9:10

*"Whatever your hand finds to do, do it with all your might."*

---

**Aero Eagle Limited** · Southampton, UK & Hong Kong · hello@aero-eagle.com
