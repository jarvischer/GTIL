# GTIL Dashboard — Infrastructure Options Research

## Executive Summary

We have 4 paths forward:

| Path | Time to MVP | Complexity | Cost | Control |
|------|--------------|-------------|-------|---------|
| **AI Platform (Lovable)** | 3–5 days | Low | High (code ownership) |
| **AI Platform (Replit)** | 3–5 days | Medium | High (code ownership) |
| **AI Platform (Base44)** | 3–5 days | Low | Low (platform limits) |
| **No-Code with Data Source (Softr/Glide)** | 5–7 days | Medium | Medium (data your own) |
| **Custom Development (Next.js/Vue)** | 10–14 days | High | High (full control) |

**Recommendation:** Test Lovable and Replit first. If either works, build in 3–5 days.

---

## Option 1: Lovable (AI-Powered Full-Stack)

### Overview
Lovable is an AI platform that builds full-stack apps from natural language descriptions. No coding required.

### Key Features

| Feature | Support |
|----------|----------|
| **Multi-user admin** | ✅ Built-in (shared workspaces) |
| **Public access** | ✅ Apps can be public or private |
| **Bilingual (EN/HE)** | ❓ Unknown (need to test) |
| **RTL support** | ❓ Unknown (need to test) |
| **JSON import/export** | ❓ Unknown (need to test) |
| **Custom UI** | ✅ High (you own the code) |
| **Hosting** | ✅ Built-in (instant deployment) |
| **Custom domain** | ❓ Unknown |
| **GitHub Sync** | ✅ Yes (code ownership) |

### Pros
- Fastest path: Describe app → AI builds it
- Built-in auth, permissions, database
- Instant hosting (no Vercel/Netlify needed)
- No infrastructure to manage
- Enterprise-grade security

### Cons
- Limited UI customization (AI generates, not you)
- Unknown RTL/Hebrew support (critical blocker?)
- Unknown JSON import/export (need to test)
- Platform lock-in (data in their system)

### Cost
- **Free:** All core features (limits unknown)
- **Paid:** Unknown pricing tiers

### Verdict
**⏳ TEST FIRST** — Promising, but RTL/Hebrew support is unknown. Must try before committing.

---

## Option 2: Replit (AI-Powered Development) ⭐ NEW

### Overview
Replit is an AI-powered development platform for building apps and sites. Natural language + full coding environment.

### Key Features

| Feature | Support |
|----------|----------|
| **Multi-user admin** | ✅ Built-in (team workspaces) |
| **Public access** | ✅ Publish apps publicly |
| **Bilingual (EN/HE)** | ❓ Unknown (need to test) |
| **RTL support** | ❓ Unknown (need to test) |
| **JSON import/export** | ✅ Via GitHub sync |
| **Custom UI** | ✅ High (full code ownership) |
| **Hosting** | ✅ Built-in (autoscaling) |
| **Custom domain** | ❓ Unknown |
| **SSH access** | ✅ Yes (full control) |
| **Database** | ✅ PostgreSQL confirmed |
| **GitHub Sync** | ✅ Yes |

### Pros
- **Code ownership:** You own and can export to GitHub
- **More control:** SSH access, full editor
- **Transparent pricing:** Clear specs (vCPUs, RAM, storage)
- **Proven platform:** Well-established
- **Full-stack:** Frontend + backend + database
- **Multiple AI modes:** Agent + Code Completion

### Cons
- **More coding-focused:** Less "no-code" than Lovable
- **Learning curve:** More technical
- **Unknown RTL/Hebrew** (critical blocker?)
- **Free tier limits:** 120 min dev time/month

### Cost
- **Basic:** Free (4 vCPUs, 2GiB, 120 min/month)
- **Advanced:** Unknown pricing

### Verdict
**⏳ TEST FIRST** — Strong contender, more control than Lovable, same timeline (3–5 days if works).

---

## Option 3: Base44 (AI-Powered No-Code)

### Overview
Base44 is an AI platform that builds apps from natural language. No coding necessary.

### Key Features

| Feature | Support |
|----------|----------|
| **Multi-user admin** | ✅ Built-in (role-based permissions) |
| **Public access** | ✅ Apps can be public or private |
| **Bilingual (EN/HE)** | ❓ Unknown (need to test) |
| **RTL support** | ❓ Unknown (need to test) |
| **JSON import/export** | ❓ Unknown (need to test) |
| **Custom UI** | 🟡 AI generates, limited customization |
| **Hosting** | ✅ Built-in (instant deployment) |
| **Custom domain** | ✅ Supported |
| **GitHub Sync** | ❓ Unknown |

### Pros
- Fastest to MVP (pre-built admin forms, tables)
- Built-in auth, permissions, database
- Instant hosting (no Vercel/Netlify needed)
- No infrastructure to manage

### Cons
- Platform lock-in (data in their system)
- Limited UI customization (AI-generated)
- Unknown RTL/Hebrew (critical blocker?)
- Unknown JSON import/export (need to test)

### Cost
- **Free:** All core features (limits unknown)
- **Paid:** $20/mo (more credits, features)

### Verdict
**⏳ TEST THIRD** — Fastest for MVP, but less control than Lovable/Replit.

---

## Option 4: Softr + Airtable (No-Code Frontend + External Data)

### Overview
Softr builds AI-powered no-code apps. Can connect to existing data sources (Airtable, Google Sheets, Notion, etc.).

### Key Features

| Feature | Support |
|----------|----------|
| **Multi-user admin** | ✅ Built-in (auth + roles) |
| **Public access** | ✅ Apps can be public or private |
| **Bilingual (EN/HE)** | 🟡 Possible with manual translations |
| **RTL support** | 🟡 Possible with manual RTL config |
| **JSON import/export** | ✅ Via external data source (Airtable/GSheets) |
| **Custom UI** | ✅ High (blocks, templates, drag-drop) |
| **Hosting** | ✅ Built-in |
| **Custom domain** | ✅ Supported |
| **Database** | ✅ Airtable (relational) |
| **GitHub Sync** | ❌ No |

### Pros
- **Data ownership:** Use Airtable as backend (you control data)
- **High customization:** Drag-drop blocks, templates
- **Real-time sync:** Airtable + Softr connect
- **AI features:** Ask AI, AI Agents, AI Co-builder

### Cons
- **RTL manual:** Need to configure `dir="rtl"` manually
- **Two tiers:** Airtable + Softr (more complex)
- **Cost:** $49/mo (Softr) + $20/mo (Airtable Plus)

### Cost
- **Softr Starter:** $49/mo (5 users, 5,000 records)
- **Airtable Plus:** $20/mo (5,000 records, 5GB)
- **Total:** $69/mo

### Verdict
**✅ STRONG BACKUP** — Best balance of speed, data ownership, and customization.

---

## Option 5: Glide + Google Sheets

### Overview
Glide builds apps from Google Sheets or SQL. Spreadsheet-like interface, AI-powered app generation.

### Key Features

| Feature | Support |
|----------|----------|
| **Multi-user admin** | ✅ Built-in (auth + roles) |
| **Public access** | ✅ Apps can be public or private |
| **Bilingual (EN/HE)** | 🟡 Possible with manual translations |
| **RTL support** | 🟡 Possible with manual RTL config |
| **JSON import/export** | ✅ Via Google Sheets (export as CSV) |
| **Custom UI** | 🟡 Medium (templates, limited blocks) |
| **Hosting** | ✅ Built-in |
| **Custom domain** | ✅ Supported |
| **Database** | ✅ Google Sheets (familiar) |

### Pros
- **Familiar data model:** Google Sheets (you know it)
- **Fast to build:** Minutes to prototype
- **AI generation:** Describe app → AI builds it
- **Good for:** Simple CRUD apps, dashboards

### Cons
- **RTL manual:** Need to configure manually
- **Limited UI:** Templates-based
- **Sheet dependency:** Data lives in GSheets (Google account)
- **Scalability:** GSheets limits (50,000 cells)

### Cost
- **Free:** Limited features
- **Maker:** $29/mo
- **Team:** $99/mo

### Verdict
**🟡 GOOD OPTION** — Fast, familiar (GSheets), but limited UI.

---

## Option 6: Airtable (Database + Custom Frontend)

### Overview
Airtable is a no-code database with AI workflows. Can build custom apps on top of it.

### Key Features

| Feature | Support |
|----------|----------|
| **Multi-user admin** | ✅ Built-in (RBAC, fine-grained permissions) |
| **Public access** | ✅ Interface designer for public views |
| **Bilingual (EN/HE)** | 🟡 Manual translations needed |
| **RTL support** | 🟡 Manual RTL config needed |
| **JSON import/export** | ✅ CSV import/export (API also available) |
| **Custom UI** | ✅ High (Interface designer, extensions) |
| **Hosting** | ✅ Built-in (Airtable hosts data) |
| **Custom domain** | ❌ Requires web app (Next.js/Vue) |
| **GitHub Sync** | ❌ No (API available) |

### Pros
- **Best data model:** Relational database
- **High customization:** Interface designer
- **Scalable:** Millions of records
- **API access:** Can build custom frontend

### Cons
- **More complex:** Relational DB learning curve
- **Two-tier approach:** Airtable + custom frontend
- **RTL manual:** Need manual implementation
- **Cost:** Two separate services

### Cost
- **Free:** 1,000 records, 0.5GB
- **Plus:** $20/mo (5,000 records)
- **Pro:** $45/mo (50,000 records)

### Verdict
**✅ STRONG OPTION** — Best for long-term scalability.

---

## Option 7: Custom Development (Next.js + Mantine or Vue + shadcn/ui)

### Overview
Full custom development using chosen framework + UI library. Maximum control, but longest timeline.

### Key Features

| Feature | Support |
|----------|----------|
| **Multi-user admin** | 🟡 Custom auth needed |
| **Public access** | ✅ Built-in |
| **Bilingual (EN/HE)** | ✅ Native (next-intl, vue-i18n) |
| **RTL support** | ✅ Native (automatic switching) |
| **JSON import/export** | ✅ Built-in (JSON files) |
| **Custom UI** | ✅ Full control |
| **Hosting** | ✅ Vercel/Netlify (free) |
| **Custom domain** | ✅ Supported |
| **Database** | ✅ JSON (or PostgreSQL) |
| **GitHub Sync** | ✅ Native |

### Pros
- **Full control:** You own all code, design, data
- **Best RTL:** Native support, automatic switching
- **Best i18n:** Native English/Hebrew translations
- **Scalable:** Can add any feature later
- **Cost-effective:** Free hosting (Vercel/Netlify)
- **Long-term:** Industry-standard, maintainable

### Cons
- **Longest timeline:** 10–14 days
- **Highest complexity:** Need coding or developer
- **Auth required:** Need to build admin system
- **Git management:** Need to handle conflicts

### Cost
- **Hosting:** $0 (Vercel free tier) or $5/mo (starting paid)
- **Domain:** $10–15/year (if not subdomain)
- **Developer:** $0 (if you build) or $50–100/hr (if hiring)

### Verdict
**⏳ FALLBACK** — Best long-term, but takes longest. Use if no-code doesn't fit.

---

## Comparison Matrix

| Criteria | Lovable | Replit | Base44 | Softr | Glide | Airtable | Custom (Next.js/Vue) |
|----------|---------|--------|--------|--------|-------|----------|----------------------|
| **Time to MVP** | 3–5 days | 3–5 days | 3–5 days | 5–7 days | 5–7 days | 10–14 days |
| **RTL Support** | ❓ Unknown | ❓ Unknown | ❓ Unknown | 🟡 Manual | 🟡 Manual | ✅ Native |
| **Bilingual (EN/HE)** | ❓ Unknown | ❓ Unknown | ❓ Unknown | 🟡 Manual | 🟡 Manual | ✅ Native |
| **Data Ownership** | ✅ Full (code) | ✅ Full (code) | 🟡 Platform | ✅ External | ✅ External | ✅ Full |
| **Custom UI** | ✅ High (code) | ✅ High (code) | 🟡 AI-only | ✅ High | ✅ High | ✅ Full |
| **Multi-Admin** | ✅ Built-in | ✅ Built-in | ✅ Built-in | ✅ Built-in | ✅ Built-in | 🟡 Custom |
| **Public Access** | ❓ Unknown | ✅ Yes | ✅ Yes | ✅ Yes | ✅ Yes | ✅ Built-in |
| **Hosting** | ✅ Built-in | ✅ Built-in | ✅ Built-in | ✅ Built-in | ✅ Built-in | ✅ Vercel/Netlify |
| **GitHub Sync** | ✅ Yes | ✅ Yes | ❓ Unknown | ❌ No | ❌ No | ✅ Native |
| **SSH Access** | ❓ Unknown | ✅ Yes | ❌ No | ❌ No | ❌ No | ✅ N/A |
| **Database** | ❓ Unknown | ✅ PostgreSQL | ❓ Unknown | Airtable | GSheets | ✅ Any |
| **Custom Domain** | ❓ Unknown | ❓ Unknown | ✅ Yes | ✅ Yes | ❌ No | ✅ Yes |
| **Cost (MVP)** | ❓ Unknown | Free tier | Free/$20/mo | $49/mo | $20/mo | Free |
| **Scalability** | ✅ High | ✅ High | 🟡 Platform | 🟡 Platform | ✅ High | ✅ Full |

---

## Recommendation Strategy

### Step 1: Test Lovable (Day 1)
- Sign up for free account
- Describe GTIL app in natural language
- **Critical test:** Does RTL/Hebrew work?
- **Critical test:** Can we build our JSON structure?
- **Critical test:** Can 3 admins collaborate?
- **Critical test:** Can we export to GitHub?
- **Decision:** If all pass → build on Lovable

### Step 2: Test Replit (Day 2) ⭐ NEW
- Sign up for free account
- Describe GTIL app in natural language
- **Critical test:** Does RTL/Hebrew work?
- **Critical test:** Can we build 3-tier standings table?
- **Critical test:** Can we build race calendar?
- **Critical test:** Can we build driver profiles?
- **Critical test:** Can we publish to public URL?
- **Critical test:** SSH access (if needed for debugging)?
- **Decision:** If all pass → build on Replit

### Step 3: Test Base44 (Day 3, if both fail)
- Sign up for free account
- Describe GTIL app in natural language
- **Critical test:** Does RTL/Hebrew work?
- **Decision:** If all pass → build on Base44

### Step 4: Softr + Airtable (If all 3 fail)
- Set up Airtable database (our JSON structure)
- Build Softr app on top
- Timeline: 5–7 days
- **Decision:** If works → deploy

### Step 5: Custom Dev (If no-code doesn't fit)
- Review tech stack decision matrix
- Choose Next.js + Mantine or Vue + shadcn/ui
- Follow MVP implementation checklist
- Timeline: 10–14 days

---

## Decision Tree

```
START
  │
  ├─ Test Lovable
  │   ├─ RTL/Hebrew works? → YES → Build on Lovable (3–5 days)
  │   └─ NO → Test Replit
  │
  ├─ Test Replit
  │   ├─ RTL/Hebrew works? → YES → Build on Replit (3–5 days)
  │   └─ NO → Test Base44
  │
  ├─ Test Base44
  │   ├─ RTL/Hebrew works? → YES → Build on Base44 (3–5 days)
  │   └─ NO → Softr + Airtable
  │
  └─ Custom Dev (10–14 days)
```

---

## Critical Questions to Answer

### Before Testing Lovable/Replit ⭐ NEW PRIORITY
1. Does RTL/Hebrew work natively?
2. Can we import JSON or build our data structure manually?
3. Can 3 admins collaborate on same project?
4. Is public access supported (no login for spectators)?
5. What's the pricing for paid tiers?

### Before Testing Base44
1. Does Base44 support RTL layouts natively?
2. Can we import JSON or build our data structure manually?
3. Can 3 admins have separate accounts with shared access?
4. Is public access free (no login for spectators)?

### Before Testing Softr
1. Can Softr apps support RTL (manual `dir="rtl"`)?
2. Can we connect to Airtable and build custom views?
3. Is $69/mo acceptable for MVP (or start on free tier)?

---

## Research Tasks for This Week

**Priority 1: Test Lovable**
- [ ] Sign up for Lovable free account
- [ ] Describe GTIL app in natural language
- [ ] Test RTL/Hebrew support
- [ ] Test data structure (can we build drivers/standings/calendar/results?)
- [ ] Test multi-admin collaboration
- [ ] Test GitHub sync
- [ ] Evaluate if it meets requirements

**Priority 2: Test Replit** ⭐ NEW
- [ ] Sign up for Replit free account
- [ ] Describe GTIL app in natural language
- [ ] Test RTL/Hebrew support
- [ ] Test data structure
- [ ] Test multi-admin collaboration
- [ ] Test GitHub sync
- [ ] Test public app publishing
- [ ] Evaluate if it meets requirements

**Priority 3: Test Base44 (if both fail)**
- [ ] Sign up for Base44 free account
- [ ] Describe GTIL app in natural language
- [ ] Test RTL/Hebrew support
- [ ] Test data import/structure
- [ ] Test multi-admin access
- [ ] Evaluate if it meets requirements

**Priority 4: Softr/Airtable (if all 3 fail)**
- [ ] Set up Airtable database
- [ ] Sign up for Softr
- [ ] Connect Softr to Airtable
- [ ] Build standings table
- [ ] Build calendar view
- [ ] Test RTL/Hebrew (manual config)

---

## Timeline

| Days | Task |
|-------|-------|
| **Day 1** | Test Lovable (RTL, data structure, multi-admin, GitHub) |
| **Day 2** | Test Replit (RTL, data structure, multi-admin, GitHub, SSH) |
| **Day 3** | Decision: Lovable ✅ OR Replit ✅ OR Test Base44 |
| **Day 3–5** | If one works → Build on chosen platform |
| **Day 3–7** | If both fail → Test Softr + Airtable |
| **Day 7** | Decision: Softr ✅ OR ❓ OR ❓ |
| **Day 8–14** | If no-code fails → Custom dev (fallback) |

**Hard Deadline:** February 26, 2026 (R4 — Sardegna A)

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
- **Mitigation:** Use pre-built component library (Mantine/Softr blocks)
- **Mitigation:** Test Lovable and Replit first (fastest AI platforms)

**Risk 2: RTL/Hebrew layout breaks**
- **Mitigation:** Test RTL on Day 1 (Lovable) and Day 2 (Replit), not Day 10
- **Mitigation:** Use library with built-in RTL support

**Risk 3: JSON conflicts between admins**
- **Mitigation:** Document "don't edit while someone else is editing"
- **Mitigation:** Last-write-wins is acceptable for MVP (add audit log to track)

**Risk 4: Hosting/deployment issues**
- **Mitigation:** Test deployment on Day 9 (polish), not Day 10
- **Mitigation:** Use built-in hosting (Lovable/Replit/Base44/Softr)

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

*Infrastructure Options Research Version: 2.0*
*Last Updated: February 12, 2026*
