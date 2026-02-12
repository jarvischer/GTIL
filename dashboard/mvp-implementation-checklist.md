# GTIL Dashboard — MVP Implementation Checklist

## Overview

2-week sprint deadline: **February 26, 2026** (R4 — Sardegna A)

**Goal:** Working dashboard with:
- Standings (all 3 tiers)
- Calendar (18 rounds)
- Driver profiles
- Race results (R1 only, R2+ added after race)
- Admin form to add results

---

## Week 1: Foundation (Days 1–5)

### Day 1: Research & Setup

**Research Tasks:**
- [ ] Review tech stack decision matrix → Choose stack (Next.js + Mantine OR Vue + shadcn)
- [ ] Review UI/UX design → Confirm pages needed
- [ ] Review data schema → Confirm JSON structure

**Setup Tasks:**
- [ ] Create GitHub repo for frontend (separate from data repo?)
- [ ] Initialize framework (Next.js or Nuxt)
- [ ] Install UI library (Mantine or shadcn/ui)
- [ ] Configure Tailwind CSS (if using shadcn)
- [ ] Set up git repository

**Deliverable:** Empty project skeleton with UI library installed

---

### Day 2: Data Layer

**Tasks:**
- [ ] Copy JSON files from `/data/` to project (`/public/data/`)
- [ ] Create TypeScript types/interfaces for:
  - [ ] Driver
  - [ ] Standing
  - [ ] RaceResult
  - [ ] Calendar
  - [ ] Split
- [ ] Write helper functions:
  - [ ] `getStandings()` → reads standings.json
  - [ ] `getCalendar()` → reads calendar.json
  - [ ] `getDrivers()` → reads drivers.json
  - [ ] `getRaceResults(round)` → reads results.json for specific race
- [ ] Create JSON loading utility (with caching)

**Deliverable:** Data layer with typed helpers

---

### Day 3: Layout & Navigation

**Tasks:**
- [ ] Create root layout with:
  - [ ] Header (logo, nav links, language toggle, admin link)
  - [ ] Footer (copyright, links)
  - [ ] RTL support (`dir="rtl"` based on locale)
- [ ] Create navigation component:
  - [ ] Standings
  - [ ] Calendar
  - [ ] Drivers
  - [ ] Results
- [ ] Create language toggle (EN/HE)
- [ ] Create mobile menu (hamburger for phone)

**Deliverable:** Working navigation between pages

---

### Day 4: Standings Page

**Tasks:**
- [ ] Create `/standings` page
- [ ] Add tier tabs (Tier 1 / Tier 2 / Tier 3)
- [ ] Build standings table component:
  - [ ] Position column
  - [ ] Driver name (clickable → profile)
  - [ ] Points column
  - [ ] Change column (↑ ↓ →)
- [ ] Add styling:
  - [ ] Promotion zone highlight (green)
  - [ ] Relegation zone highlight (red)
  - [ ] Hover effects on rows
- [ ] Make responsive (mobile: stacked list)
- [ ] Add RTL support (Hebrew: table right-aligned)

**Deliverable:** Working standings page with all 3 tiers

---

### Day 5: Calendar Page

**Tasks:**
- [ ] Create `/calendar` page
- [ ] Add filter tabs (All / Completed / Upcoming)
- [ ] Build race card component:
  - [ ] Round number
  - [ ] Track name
  - [ ] Date
  - [ ] Car restrictions
  - [ ] Format (Sprint/Double/Triple)
  - [ ] Status badge (✅ / ⏳)
- [ ] Group races by month
- [ ] Add "Load More" for past months
- [ ] Make responsive (mobile: stacked list)

**Deliverable:** Working calendar page with all 18 rounds

---

## Week 2: Pages & Admin (Days 6–10)

### Day 6: Driver Profile Page

**Tasks:**
- [ ] Create `/drivers/:id` page
- [ ] Build profile header:
  - [ ] Driver name
  - [ ] Tier and split
  - [ ] Current position
  - [ ] Total points
- [ ] Build stats grid:
  - [ ] Races entered
  - [ ] Wins / podiums
  - [ ] Average finish
  - [ ] DNFs
- [ ] Build race history table:
  - [ ] Round
  - [ ] Track
  - [ ] Finish position
  - [ ] Points earned
- [ ] Add RTL support
- [ ] Make responsive

**Deliverable:** Working driver profile page

---

### Day 7: Race Results Page

**Tasks:**
- [ ] Create `/results/:round` page
- [ ] Add split tabs (A/B/C)
- [ ] Build results table component:
  - [ ] Position
  - [ ] Driver (clickable → profile)
  - [ ] Time gap
  - [ ] Points
  - [ ] DNF indicator
- [ ] Add fastest lap section
- [ ] Add podium highlighting (🥇🥈🥉)
- [ ] Add RTL support
- [ ] Make responsive

**Deliverable:** Working race results page

---

### Day 8: Admin Dashboard

**Tasks:**
- [ ] Create `/admin` route (protected)
- [ ] Implement simple password auth:
  - [ ] Login form (password input)
  - [ ] Store auth in localStorage
  - [ ] Protect all admin routes
- [ ] Build admin dashboard:
  - [ ] Quick stats (current round, total points, etc.)
  - [ ] Quick actions (Add Results, Edit Calendar, Manage Drivers)
  - [ ] Recent activity log
- [ ] Add "Logout" button

**Deliverable:** Working admin login and dashboard

---

### Day 9: Add Race Results Form

**Tasks:**
- [ ] Create `/admin/results/add` page
- [ ] Build race selector (dropdown R1–R18)
- [ ] Auto-fill race info (track, car, format) from calendar.json
- [ ] Build split tabs (A/B/C)
- [ ] Build results entry table:
  - [ ] Position (auto 1, 2, 3...)
  - [ ] Driver dropdown (from drivers.json, filtered by split)
  - [ ] Points (auto-calculate)
  - [ ] DNF checkbox
- [ ] Add "Paste from Clipboard" (parse Discord text)
- [ ] Add validation:
  - [ ] Each driver used once per split
  - [ ] Positions are sequential
- [ ] Add "Save Draft" (localStorage)
- [ **IMPLEMENTATION** ] Save to JSON:
  - [ ] Update `results.json`
  - [ ] Recalculate `standings.json`
  - [ ] Update `calendar.json` (race status)

**Deliverable:** Working admin form to add race results

---

### Day 10: Polish & Deploy

**Tasks:**
- [ ] Add i18n translations:
  - [ ] Create `en.json` with all UI text
  - [ ] Create `he.json` with Hebrew translations
  - [ ] Test RTL layout with Hebrew
- [ ] Add error handling:
  - [ ] JSON load errors
  - [ ] Driver not found
  - [ ] Network errors
- [ ] Add loading states:
  - [ ] Skeleton tables while loading
  - [ ] Loading spinners
- [ ] Test responsive design:
  - [ ] Mobile (320px)
  - [ ] Tablet (768px)
  - [ ] Desktop (1024px+)
- [ ] Deploy to Vercel/Netlify:
  - [ ] Connect repo
  - [ ] Configure domain (if any)
  - [ ] Test live site
- [ ] Update admin documentation:
  - [ ] How to add results
  - [ ] How to manage drivers
  - [ ] How to update calendar

**Deliverable:** Live MVP dashboard

---

## Post-MVP (Optional / Week 3)

### Nice-to-Have Features

- [ ] Edit calendar (move dates, cancel races)
- [ ] Manage drivers (add/edit/remove)
- [ ] Edit standings (manual override)
- [ ] Export standings/results to CSV
- [ ] Share results to Discord/Twitter
- [ ] Driver avatar images
- [ ] Track images
- [ ] Search/filter in standings
- [ ] Dark mode toggle
- [ ] Activity log (audit trail)

---

## Testing Checklist

### Before Deploying

**Functionality:**
- [ ] Can view standings for all 3 tiers?
- [ ] Can view calendar with all 18 rounds?
- [ ] Can view driver profile for any driver?
- [ ] Can view race results for R1?
- [ ] Can switch between EN/HE?
- [ ] Does RTL layout work correctly?

**Admin:**
- [ ] Can login with password?
- [ ] Can add race results?
- [ ] Does standings recalculate after adding results?
- [ ] Does JSON file save correctly?

**Responsiveness:**
- [ ] Mobile navigation works (hamburger menu)?
- [ ] Tables are readable on mobile?
- [ ] Forms are usable on mobile?

**Performance:**
- [ ] Page loads < 2s?
- [ ] No console errors?
- [ ] Lighthouse score > 90?

---

## Known Limitations (MVP)

1. **No live race leaderboards** — Results added manually after race
2. **No Discord integration** — Manual results posting
3. **No multi-admin conflict handling** — Last write wins
4. **No historical seasons** — 2026 season only
5. **No driver avatars** — Names only (or initials)
6. **No track images** — Text only
7. **No dark mode** — Light theme only
8. **No export features** — No CSV/PDF export

---

## Success Criteria (MVP)

**Must Have:**
- ✅ All 4 public pages working (standings, calendar, drivers, results)
- ✅ Admin can add race results
- ✅ Standings recalculate automatically
- ✅ English + Hebrew with RTL support
- ✅ Mobile responsive
- ✅ Deployed to production

**Nice to Have:**
- ✅ Admin activity log
- ✅ Search/filter in standings
- ✅ Export to CSV

---

## Risk Mitigation

**Risk 1: 2-week deadline too tight**
- **Mitigation:** Cut nice-to-have features (dark mode, avatars)
- **Mitigation:** Use pre-built component library (Mantine) to save time

**Risk 2: RTL/Hebrew layout breaks**
- **Mitigation:** Test RTL on Day 2 (layout), not Day 10 (polish)
- **Mitigation:** Use library with built-in RTL support (Mantine/next-intl)

**Risk 3: JSON conflicts between admins**
- **Mitigation:** Document "don't edit while someone else is editing"
- **Mitigation:** Last-write-wins is acceptable for MVP (add audit log to track)

**Risk 4: Hosting/deployment issues**
- **Mitigation:** Test deployment on Day 9 (polish), not Day 10
- **Mitigation:** Use Vercel/Netlify (zero config deployment)

---

## Backup Plan

**If deadline is missed:**
1. Deploy MVP without Hebrew (English only, RTL not critical for Week 1)
2. Deploy MVP without admin form (manually edit JSON files)
3. Deploy MVP without mobile responsiveness (desktop only)

**Critical Path (Must Complete):**
1. Standings page (Tier 1, 2, 3)
2. Calendar page (18 rounds)
3. Admin form (add results)
4. Deploy

Everything else is negotiable.

---

*MVP Implementation Checklist Version: 1.0*
*Deadline: February 26, 2026 (2 weeks)*
