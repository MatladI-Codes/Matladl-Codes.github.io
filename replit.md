# Ofentse Matladi — Portfolio Site

## Project Overview

A personal portfolio website for **Ofentse Thapelo Chinedu Matladi** — tech founder, self-taught developer, and creator of SEDIQ. The site is built as a single static HTML/CSS/JS file with a retro gaming aesthetic (PS1/early Macintosh pixel crossover, Super Mario Bros energy). It is served from Replit using Python's built-in HTTP server.

---

## Tech Stack

| Layer | Technology |
|---|---|
| Markup | HTML5 |
| Styling | CSS3 (embedded in `index.html`) |
| Interactivity | Vanilla JavaScript (embedded in `index.html`) |
| Fonts | Google Fonts — Press Start 2P, Inter, Space Mono |
| Server | Python 3 `http.server` on port 5000 |
| Hosting | Replit (dev) — deployable as static site |

No build tools, no frameworks, no package manager. Everything runs from one file.

---

## Design System

**Color Palette**
- Background: `#1A1A2E` (deep navy)
- Primary accent: `#E8121C` (Mario red)
- Secondary accent: `#F7C948` (coin yellow)
- Green: `#2D7A1F` (pipe green)
- Blue: `#2E5EAA` (Mario sky blue)
- Text: `#F5F5F0` (off-white)
- Muted text: `#9999AA`

**Typography**
- `Press Start 2P` — section titles and hero name only
- `Inter` — all body text
- `Space Mono` — badges, tags, labels, code-style elements

**Background**
Dot-grid with faint Mario-tile crosslines using pure CSS `radial-gradient` + `linear-gradient` layering. No image file needed.

**Aesthetic rules**
- Chunky 2px red pixel borders on all cards
- Yellow `box-shadow` offset on hover (`4px 4px 0 var(--yellow)`)
- Pixel-style dashed timeline connector
- Repeating 4-color pixel divider strips between sections

---

## File Structure

```
/
├── index.html                        — entire site (HTML + CSS + JS)
├── replit.md                         — this file
├── assets/
│   ├── 1000920127.png                — BeasyBaby logo
│   ├── 20260517_210937.png           — hero photo (Ofentse on stage, Red Bull World Final)
│   ├── introduction_to_cip.png       — OPSWAT ICIP certificate image
│   ├── opswat-introduction-to-
│       critical-infrastructure-
│       protection-icip.png           — OPSWAT badge logo
│   ├── 1782494566012.png             — NWU Chess Marketing & PR certificate
│   ├── 1782494992588.png             — National Senior Certificate (Umalusi)
│   ├── nwu-logo.png                  — NWU Eagles logo
│   └── umalusi-logo.png              — Umalusi logo
├── Mr Matladi -Resume.pdf            — resume (referenced in original project)
└── media/                            — placeholder folder (legacy)
```

All other image files in the project root are legacy assets from the original portfolio and are no longer referenced in the current `index.html`.

---

## Sections

| # | Section ID | Title | Description |
|---|---|---|---|
| — | Boot screen | — | Full-screen terminal animation on page load. Progress bar fills 0–100%, then types: Initializing, Loading full name, Goal pivot (Biochemistry struck through → Computer Science), Initialization Complete, Status: ONLINE |
| 1 | `#home` | Hero | Name in Press Start 2P with red shadow, 4 bylines appearing in sequence, hero photo (stage/Red Bull pitch), story quote |
| — | `#badges` | Badges strip | Horizontally scrollable credential chips: OPSWAT ICIP, TryHackMe PT1, NWU Chess PR, NSC NQF L4 |
| 2 | `#about` | Chapter One: The Builder | Two paragraphs on background and pivot; closing quote in yellow Space Mono |
| 3 | `#arsenal` | Arsenal | 4 pixel stat cards: Code & Build, Security & Infrastructure, AI & Prompt Engineering, Leadership & Strategy |
| 4 | `#timeline` | The Timeline | Vertical dashed pixel timeline with 6 entries (CATHSSETA, NWU Chess PR, Chess Instructor, BSc Biochemistry, NSC, Self-Taught Developer) |
| 5 | `#ventures` | SEDIQ. Ventures | NOUS and BeasyBaby venture cards; Red Bull Basement feature block with credential card |
| 6 | `#chess` | The Chess Files | Background, ELO stats, quote card, funny closer |
| 7 | `#credentials` | Proof of Work | 2×2 credential grid: OPSWAT, TryHackMe, NWU Chess, NSC (locked — modal on click) |
| 8 | `#connect` | Let's Build | 4 pixel contact buttons: Email, LinkedIn, GitHub, WhatsApp |
| — | Footer | — | Space Mono copyright line |

---

## Key Interactive Features

**Boot sequence** — runs on every page load. Non-skippable. Fades out after "Status: ONLINE" then triggers byline animations.

**Bylines** — appear one by one with 300ms delay each after boot ends.

**NSC certificate modal** — clicking "LOCK — Restricted" on the credential card or the timeline padlock link opens a modal with the Umalusi restricted-access disclaimer instead of showing the certificate publicly.

**Scroll fade-in** — all major content blocks use `IntersectionObserver` to fade up on scroll.

**Mobile hamburger nav** — nav collapses to a toggle button on screens under 768px. Clicking a nav link closes the menu.

**Smooth scroll** — all `href="#..."` anchor links scroll smoothly to their target.

---

## Running the Site

The site is served by a Replit workflow:

```
python3 -m http.server 5000 --bind 0.0.0.0
```

**Workflow name:** `Start application`
**Port:** `5000`
**Output type:** `webview`

To restart after edits: use the workflow restart button in Replit, or call `restart_workflow`.

---

## Deployment

Configured as a **static** deployment:

```
deploymentTarget = "static"
publicDir = "."
```

The entire project root is the public directory — `index.html` is the entry point.

---

## Credentials & Links Referenced

| Credential | Issuer | Date | Status |
|---|---|---|---|
| OPSWAT ICIP | OPSWAT Academy | Jun 2026 (exp. Jul 2027) | Verified — cert image in assets |
| Junior Penetration Tester PT1 | TryHackMe | Apr 2026 | Links to tryhackme.com |
| Chess Marketing & PR Officer | NWU Sport | Feb–Nov 2025 | Verified — cert image in assets |
| National Senior Certificate NQF L4 | Umalusi | Dec 2023 | Restricted — modal only |
| CATHSSETA Learnership NQF L3 | CATHSSETA / McDonald's | Jun 2026 – May 2027 | Underway |
| Red Bull Basement 2026 | Red Bull South Africa | Mar 2026 | National Finalist — World Final SF |

---

## Contact

- **Email:** thapelomatladi@outlook.com
- **LinkedIn:** linkedin.com/in/ofentsematladi-tc
- **GitHub:** github.com/MatladI-Codes
- **WhatsApp:** +27 63 181 9590

---

## User Preferences

- No emojis anywhere in the site
- No placeholder content — every section uses exact provided copy
- All credential images served locally from `assets/` (no broken external CDN links)
- Site must be fully mobile responsive
- Smooth scroll on all nav links
- Preserve existing file names — do not rename `index.html`
