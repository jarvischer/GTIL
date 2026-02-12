# GTIL - Grand Turismo Israel League

[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![Status](https://img.shields.io/badge/status-active-green.svg)]()

## Overview

GTIL is a small website tracking the Grand Turismo championship in Israel — competitive GT simulator racing events.

## Project Status

🚧 **Early Development** — Vision still being drafted.

## 2026 Season Schedule

### February
| Round | Track | Date | Car | Format |
|-------|-------|------|-----|--------|
| R1 | Goodwood | 05/02/26 | Mazda Roadster Touring Car | Sprint |
| R2 | St. Croix B | 12/02/26 | Honda NSX Concept (Gr.2) | Sprint |
| R3 | Dragon Trail Gardens | 19/02/26 | Any Gr.3 (No BMW) | Sprint |
| R4 | Sardegna A | 26/02/26 | Any Gr.4 (No Citroen/Genesis) | Sprint |

### March
| Round | Track | Date | Car | Format |
|-------|-------|------|-----|--------|
| R5 | Red Bull Ring (Short) | 05/03/26 | Radical SR3 SL '13 | Sprint |
| R6 | Monza | 12/03/26 | Ferrari 296 GT3 '23 | Race 100 |
| R7 | Nürburgring GP | 19/03/26 | Any Gr.4 (German make) | Double points |

### April
| Round | Track | Date | Car | Format |
|-------|-------|------|-----|--------|
| R8 | Spa-Francorchamps | 16/04/26 | Dallara SF23 / Toyota | Double points |
| R9 | Le Mans 24H | 23/04/26 | Any Gr.1 (Hybrid) | Double points |
| R10 | Road Atlanta | 30/04/26 | Any Gr.4 (American make) | Sprint |

### May
| Round | Track | Date | Car | Format |
|-------|-------|------|-----|--------|
| R11 | Gilles Villeneuve | 07/05/26 | Any Gr.3 | Double points |
| R12 | Watkins Glen Long | 14/05/26 | Porsche 911 GT3 RS '22 | Sprint |
| R13 | Laguna Seca | 28/05/26 | Alpine A110 Premiere Edition '17 | Sprint |

### June
| Round | Track | Date | Car | Format |
|-------|-------|------|-----|--------|
| R14 | Mount Panorama | 04/06/26 | Any Gr.4 (MR drivetrain) | Double points |
| R15 | Fuji Speedway (Full) | 11/06/26 | Any Gr.3 (Japan make) | Sprint |
| R16 | Tokyo Expressway South (clockwise) | 18/06/26 | Lexus LFA | Double points |
| R17 | Yas Marina Circuit | 25/06/26 | Any Gr.3 (MR drivetrain) | Double points |

### July (Grand Final)
| Round | Track | Date | Car | Format |
|-------|-------|------|-----|--------|
| R18 | Interlagos | 02/07/26 | Any Gr.4 | Double points |

**Season Closing Event:** 16/07/26

---

## Driver Rankings (Season 2026)

### Tier 1 — Top 14 (Split 1)
| Driver |
|--------|
| Itay Sela |
| Moti Kimchi |
| Erez Ashtamker |
| Eliran Kadosh |
| Avi Shimshilashvili |
| Nir Maimon |
| Alexey Belkin |
| Haim Kleimerman |
| Yuri Kazakov |
| Jonathan Samuha |
| Amir Volinsky |
| Kelly Aiche |
| Lidor Lessner |
| Daniel Bakshi |

### Tier 2 — Positions 15–28 (Split 2)
| Driver |
|--------|
| Andrew Slobodskoy |
| Liam Kayner |
| Anton Belinenson |
| Dmitry Tokar |
| Eli Konstantini |
| Matan Gal |
| Harel Kaduri |
| Yuval Reikoren |
| Itzhak Swissa |
| Dmitri Maizenberg |
| Liron Korenblat |
| Gal Haham |
| Dor Bazak |
| Victor Gravitskii |

### Tier 3 — Positions 29–41 (Split 3)
| Driver |
|--------|
| Yuval Haim |
| Nisan Lankry |
| Aviram Tovi |
| Saar Zvi |
| Chen Simhony |
| Zohar Rabinov |
| Liron Bard |
| Dave Zichroni |
| Ben Fartouk |
| Yonathan Rahum |
| Ron Rugi |
| Bar Dalal |
| Malachi Shalom |
| Amor |

---

## Tech Stack

> To be defined

---

## Features (Planned)

- Driver standings and statistics
- Race calendar and results
- Championship points table
- Historical race data

---

## Getting Started

### Data Files

All championship data is stored in `/data/` as JSON files:

- `drivers.json` — Driver registry with tier/split assignments
- `standings.json` — Current championship standings
- `results.json` — Race results for completed rounds
- `calendar.json` — Full season schedule

See `/data/README.md` for schema documentation.

### Documentation

Planning and design docs are in `/dashboard/`:

- `prd.md` — Product Requirements Document
- `SUMMARY.md` — Quick planning overview (Lovable focus)
- `ui-ux-design.md` — Detailed UI/UX mockups
- `admin-form-spec.md` — Admin form specification
- `research-plan.md` — Research tasks (framework, hosting, i18n)
- `tech-stack-decision.md` — Tech stack comparison (custom dev only)
- `mvp-implementation-checklist.md` — 2-week sprint checklist
- `lovable-analysis.md` — Detailed Lovable platform analysis
- `infrastructure-options-final.md` — Complete comparison (Lovable, Replit, Base44, Softr, Glide, Airtable, custom)
- `INFRASTRUCTURE_SUMMARY.md` — Quick decision matrix (Lovable focus)

### Rules

See `league-rules.md` for league structure, points system, and code of conduct.

---

## Contributing

> Guidelines TBD

---

## License

MIT

---

*Project initiated: February 2026*
