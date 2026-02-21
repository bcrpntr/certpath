# CertPath

A single-file, offline-capable cybersecurity certification tracker and career planning tool built with React.

No build step. No backend. No dependencies to install. Open the HTML file in a browser and it works.

---

## What It Does

CertPath tracks your certification portfolio, maps a path to your goal certifications, and surfaces actionable next steps — all persisted in `localStorage`.

**Core views:**

| Tab | Purpose |
|-----|---------|
| **Dashboard** | Expiring certs, CE deficit alerts, goal progress, AI-ranked recommendations |
| **Portfolio** | All held/studying/planned certs with status, CE hours, expiry dates |
| **Roadmap** | Career track selector with phase-by-phase progression paths |
| **Catalog** | Full cert database — filterable by vendor, domain, tier, status |
| **Action Plan** | Prioritized task list generated from your current state |

---

## Cert Database

539 certifications across 12 domains from 12 vendors:

`AWS` · `Cisco` · `CompTIA` · `EC-Council` · `GIAC` · `Google Cloud` · `ISACA` · `ISC²` · `ITIL` · `Microsoft` · `OffSec` · `PMI`

Each cert carries: tier (1–4), cost, CE requirement, cycle length, prerequisites, domain, difficulty score, and CE pool membership.

---

## Career Tracks

20 tracks with Foundation → Core → Expert phase structure:

- Red Team, Blue Team, DFIR, GRC/Risk
- Cloud Security, AppSec, IAM, Network Defense
- Threat Intel, Malware Analysis, Security Architecture, Executive/CISO
- And more

---

## Recommendations Engine

Tiered scoring on the full catalog against your current portfolio state:

- **+100** — prerequisites met, logical next cert
- **+70** — cert grants CE toward a held cert you're lacking
- **+60** — same-vendor progression
- **+20** — one prerequisite away

Top 6 results surfaced on the Dashboard.

---

## Features

- **Portfolio sort by vendor** — grouped view with vendor-ordered tiles
- **Tile context menu** — right-click/long-press any cert to set as goal or open exam page
- **CE tracking** — per-cert CE hours with deficit alerts
- **Auto-renew flags** — track certs eligible for automatic renewal
- **Goal tracking** — set a target cert, see prerequisite gap on the roadmap
- **Track selector** — persistent career track filter across roadmap view
- **Mobile responsive** — bottom nav, FAB, touch-optimized

---

## Usage

```bash
# Clone or download
git clone https://github.com/youruser/certpath.git

# Open in browser
open certpath-v7.html
```

No npm. No webpack. No server.

All state is stored in `localStorage` under the key `certpath_v7`. Export/import not yet implemented — clearing browser data clears your portfolio.

---

## File Structure

```
certpath-v7.html    # Entire application — 3,040 lines, ~252KB
README.md
```

The file embeds:
- React 18 + ReactDOM (CDN)
- Babel standalone (in-browser JSX transpile)
- Inter + JetBrains Mono (Google Fonts)
- All cert data, track definitions, CE activity catalog
- All components and application logic

---

## Tech

| Layer | Choice |
|-------|--------|
| UI framework | React 18 (UMD, no JSX build) |
| Transpiler | Babel standalone |
| Styling | Vanilla CSS custom properties |
| State | React hooks + localStorage |
| Fonts | Inter, JetBrains Mono |
| Build tooling | None |

---

## Status

Current version: **v7.3**

Actively developed. Known gaps:
- No data export/import
- No sync across devices
- Exam links are static; some may go stale
- CE pool logic covers major vendors; niche certs may be incomplete
