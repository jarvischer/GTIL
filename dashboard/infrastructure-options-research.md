# GTIL Dashboard — Infrastructure Options Research

## Executive Summary

We have 3 paths forward:

| Path | Time to MVP | Complexity | Cost | Control |
|------|--------------|-------------|-------|---------|
| **No-Code Platform (Base44)** | 3–5 days | Low | Low (platform limits) |
| **No-Code with Data Source (Softr/Glide)** | 5–7 days | Medium | Medium (data your own) |
| **Custom Development (Next.js/Vue)** | 10–14 days | High | High (full control) |

**Recommendation:** Explore no-code first. If it doesn't meet requirements, fall back to custom dev.

---

## Option 1: Lovable (AI-Powered Full-Stack) ⭐ NEW

### Overview
Lovable is an AI platform that builds full-stack apps from natural language. Includes frontend, backend, database, and auth.

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
| **GitHub sync** | ✅ Yes (code ownership) |
| **Custom domain** | ❓ Unknown |

### Pros
- **Code ownership:** You own and can edit all code
- **GitHub sync:** Full version control, exportable
- **Full-stack:** Frontend + backend + database built
- **Natural language:** Describe app → AI generates it
- **Collaboration:** Shared workspaces for 3 admins
- **Enterprise-grade:** Security, privacy, governance

### Cons
- **Unknown RTL/Hebrew** (critical blocker?)
- **Unknown pricing** (need to check)
- **Unknown public access** (need to test)
- **Platform learning curve** (need to understand how to iterate)

### Cost
- **Free:** Unknown limits
- **Paid:** Unknown pricing tiers

### Use Case Fit

| Requirement | Fit | Notes |
|--------------|-------|-------|
| Standings tables (3 tiers) | 🟡 | Should work, but need to test |
| Calendar (18 rounds) | 🟡 | Should work, but need to test |
| Driver profiles | 🟡 | Should work, but need to test |
| Admin forms (add results) | 🟡 | Should work, but need to test |
| RTL/Hebrew | ❓ **CRITICAL** | Must test before committing |
| Public access (spectators) | ❓ Need to test | Must confirm |
| Multi-admin (3 users) | ✅ | Shared workspaces |

### Verdict
**⏳ TEST FIRST** — Better than Base44 (code ownership + GitHub sync), but RTL/Hebrew unknown.

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

### Pros
- **Code ownership:** You own and can export to GitHub
- **GitHub sync:** Full integration with version control
- **Full-stack:** Frontend + backend + database built
- **More control:** SSH access, full editor
- **Transparent pricing:** Clear specs (vCPUs, RAM, storage)
- **Proven platform:** Well-established, used by teams
- **Autoscaling:** Built-in for production
- **Multiple AI modes:** Agent + Code Completion

### Cons
- **More coding-focused:** Less "no-code" than Lovable
- **Learning curve:** More technical for non-coders
- **Unknown RTL/Hebrew** (critical blocker?)
- **Free tier limits:** 120 min dev time/month
- **Platform complexity:** More options = more to learn

### Cost
- **Basic:** Free (4 vCPUs, 2GiB, 120 min/month)
- **Advanced:** Unknown pricing (better specs, unlimited time)

### Use Case Fit

| Requirement | Fit | Notes |
|--------------|-------|-------|
| Standings tables (3 tiers) | ✅ | Should work with AI generation |
| Calendar (18 rounds) | ✅ | Should work with AI generation |
| Driver profiles | ✅ | Should work with AI generation |
| Admin forms (add results) | ✅ | Should work with AI generation |
| RTL/Hebrew | ❓ **CRITICAL** | Must test before committing |
| Public access (spectators) | ✅ | Can publish apps |
| Multi-admin (3 users) | ✅ | Team collaboration |
| GitHub sync | ✅ | Full integration |
| PostgreSQL database | ✅ | Built-in support |

### Verdict
**⏳ TEST OPTION** — Strong contender, more control than Lovable, same timeline (3–5 days if works).

---

## Option 3: Base44 (AI-Powered No-Code)

### Overview
Base44 is an AI platform that builds apps from natural language descriptions. No coding required.

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
| **Analytics** | ✅ Built-in |

### Pros
- Fastest path: Describe app → AI builds it
- Built-in auth, permissions, database
- Instant hosting (no Vercel/Netlify needed)
- No infrastructure to manage
- $0 to start, paid plans from $20/mo

### Cons
- Limited UI customization (AI generates, not you)
- Unknown RTL/Hebrew support (critical blocker?)
- Unknown JSON import/export (need to test)
- Platform lock-in (data in their system)
- Scaling limits on free tier

### Cost
- **Free:** All core features (limits unknown)
- **Paid:** $20/mo+ (more credits, features, support)

### Use Case Fit

| Requirement | Fit | Notes |
|--------------|-------|-------|
| Standings tables (3 tiers) | 🟡 | AI should generate, but may be basic |
| Calendar (18 rounds) | 🟡 | Should work, but styling limited |
| Driver profiles | 🟡 | Depends on AI capability |
| Admin forms (add results) | 🟡 | Need to test if complex forms work |
| RTL/Hebrew | ❓ **CRITICAL** | Must test before committing |
| Public access (spectators) | ✅ | Supported |
| Multi-admin (3 users) | ✅ | Built-in permissions |

### Verdict
**⏳ TEST FIRST** — Promising, but RTL/Hebrew support is unknown. Must try before committing.

---

## Option 2: Softr (No-Code Frontend + External Data)

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
| **Analytics** | ✅ Built-in |

### Pros
- **Data ownership:** Use Airtable/GSheets as backend (you control data)
- **High customization:** Drag-drop blocks, templates, styling
- **Multi-source:** Connect to existing tools (Notion, Airtable, etc.)
- **AI features:** Ask AI, AI Agents, AI Co-builder
- **Fast setup:** Minutes to hours, not days
- **Good for:** Portals, dashboards, internal tools

### Cons
- **RTL manual:** Need to configure `dir="rtl"` manually
- **Bilingual manual:** Need to translate all UI text manually
- **Subscription-based:** Free tier limited
- **Design limits:** Blocks-based, not full design freedom

### Cost
- **Starter:** $49/mo (5 users, 5000 records)
- **Professional:** $149/mo (20 users, 50,000 records)
- **Business:** $349/mo (unlimited users, 500,000 records)

*Alternative:* Use Airtable as backend + build own frontend (custom path)

### Use Case Fit

| Requirement | Fit | Notes |
|--------------|-------|-------|
| Standings tables (3 tiers) | ✅ | Can use list/table blocks |
| Calendar (18 rounds) | ✅ | Can use list/grid blocks |
| Driver profiles | ✅ | Can use detail pages |
| Admin forms (add results) | ✅ | Can use form blocks + permissions |
| RTL/Hebrew | 🟡 Manual | Possible with RTL CSS |
| Public access (spectators) | ✅ | Supported |
| Multi-admin (3 users) | ✅ | Built-in auth |

### Verdict
**✅ STRONG OPTION** — Best balance of speed, data ownership, and customization.

---

## Option 3: Glide (No-Code + Google Sheets)

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
| **Analytics** | ✅ Built-in |

### Pros
- **Familiar data model:** Google Sheets (you already know it)
- **Fast to build:** Minutes to prototype
- **AI generation:** Describe app → AI builds it
- **Good for:** Simple CRUD apps, data dashboards
- **Low learning curve:** Spreadsheet-based

### Cons
- **RTL manual:** Need to configure manually
- **Limited UI:** Templates-based, not full design freedom
- **Sheet dependency:** Data lives in GSheets (Google account)
- **Scalability:** GSheets limits (50,000 cells per sheet)

### Cost
- **Free:** Limited features
- **Maker:** $29/mo (more features)
- **Team:** $99/mo (collaboration, unlimited apps)

### Use Case Fit

| Requirement | Fit | Notes |
|--------------|-------|-------|
| Standings tables (3 tiers) | ✅ | Table views work well |
| Calendar (18 rounds) | ✅ | List/grid views |
| Driver profiles | 🟡 | Detail pages possible but basic |
| Admin forms (add results) | ✅ | Forms connect to sheets |
| RTL/Hebrew | 🟡 Manual | Possible with RTL config |
| Public access (spectators) | ✅ | Supported |
| Multi-admin (3 users) | ✅ | Supported |

### Verdict
**✅ GOOD OPTION** — Fast, familiar (GSheets), but limited UI customization.

---

## Option 4: Airtable (Database + Custom Frontend)

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
| **Analytics** | ✅ Built-in |

### Pros
- **Best data model:** Relational database (better than GSheets)
- **High customization:** Interface designer for custom UI
- **Scalable:** Millions of records, tens of thousands of users
- **AI workflows:** Automations, AI agents
- **Enterprise-grade:** Trusted by 500k+ teams
- **API access:** Can build custom frontend on top

### Cons
- **More complex:** Learning curve for relational DB
- **Two-tier approach:** Airtable + custom frontend for full control
- **RTL manual:** Need manual RTL implementation
- **Bilingual manual:** Need manual translations

### Cost
- **Free:** 1,000 records, 0.5GB attachments
- **Plus:** $20/mo (5,000 records, 5GB)
- **Pro:** $45/mo (50,000 records, 50GB)

### Use Case Fit

| Requirement | Fit | Notes |
|--------------|-------|-------|
| Standings tables (3 tiers) | ✅ | Table views, sorting, filtering |
| Calendar (18 rounds) | ✅ | Calendar views, date filtering |
| Driver profiles | ✅ | Detail views, linked records |
| Admin forms (add results) | ✅ | Forms with permissions |
| RTL/Hebrew | 🟡 Manual | Possible with extensions/custom CSS |
| Public access (spectators) | ✅ | Shareable views |
| Multi-admin (3 users) | ✅ | RBAC, fine-grained permissions |

### Verdict
**✅ STRONG OPTION** — Best for long-term scalability, but more setup time.

---

## Option 5: Custom Development (Next.js + Mantine or Vue + shadcn/ui)

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
- **Git management:** Need to handle conflicts between admins

### Cost
- **Hosting:** $0 (Vercel free tier) or $5/mo (starting paid)
- **Domain:** $10–15/year (if not subdomain)
- **Developer:** $0 (if you build) or $50–100/hr (if hiring)

### Use Case Fit

| Requirement | Fit | Notes |
|--------------|-------|-------|
| Standings tables (3 tiers) | ✅ | Full control |
| Calendar (18 rounds) | ✅ | Full control |
| Driver profiles | ✅ | Full control |
| Admin forms (add results) | ✅ | Full control |
| RTL/Hebrew | ✅ | Native support |
| Public access (spectators) | ✅ | Built-in |
| Multi-admin (3 users) | 🟡 Need to build auth |

### Verdict
**⏳ FALLBACK** — Best long-term, but takes longest. Use if no-code doesn't fit.

---

## Comparison Matrix

| Criteria | Lovable | Base44 | Softr | Glide | Airtable | Custom (Next.js/Vue) |
|----------|---------|---------|--------|-------|----------|----------------------|
| **Time to MVP** | 3–5 days | 3–5 days | 5–7 days | 5–7 days | 10–14 days |
| **RTL Support** | ❓ Unknown | ❓ Unknown | 🟡 Manual | 🟡 Manual | ✅ Native |
| **Bilingual (EN/HE)** | ❓ Unknown | ❓ Unknown | 🟡 Manual | 🟡 Manual | ✅ Native |
| **Data Ownership** | ✅ Full (code) | 🟡 Platform | ✅ External | ✅ External | ✅ Full |
| **Custom UI** | ✅ High (you own code) | 🟡 AI-generated | ✅ High | ✅ High | ✅ Full |
| **Multi-Admin** | ✅ Built-in | ✅ Built-in | ✅ Built-in | ✅ Built-in | 🟡 Custom |
| **Public Access** | ❓ Unknown | ✅ Supported | ✅ Supported | ✅ Supported | ✅ Built-in |
| **Hosting** | ✅ Built-in | ✅ Built-in | ✅ Built-in | ✅ Built-in | ✅ Vercel/Netlify |
| **GitHub Sync** | ✅ Yes | ❓ Unknown | ❌ No | ❌ No | ✅ Native |
| **Custom Domain** | ❓ Unknown | ✅ Yes | ✅ Yes | ❌ No | ✅ Yes |
| **Cost (MVP)** | ❓ Unknown | Free/$20/mo | $49/mo | Free/$29/mo | $20/mo | Free |
| **Scalability** | ✅ High | 🟡 Platform limits | 🟡 Platform limits | ✅ High | ✅ High | ✅ Full |

---

## Recommendation Strategy

### Step 1: Test Lovable First (1–2 days) ⭐ NEW PRIORITY
- Sign up for free account
- Describe GTIL app in natural language
- **Critical test:** Does RTL/Hebrew work?
- **Critical test:** Can we build 3-tier standings table?
- **Critical test:** Can we build race calendar?
- **Critical test:** Can we import JSON or build data structure?
- **Critical test:** Can 3 admins collaborate?
- **Critical test:** Can we export to GitHub?

### Step 2: Test Base44 If Lovable Fails (1–2 days)
- Sign up for free account
- Describe GTIL app
- **Critical test:** RTL/Hebrew support
- **Critical test:** Data structure capabilities

### Step 3A: If Lovable Works → Build on Lovable
- Timeline: 3–5 days to MVP
- Cost: Free or unknown paid tier
- Pros: Code ownership + GitHub sync

### Step 3B: If Base44 Works → Build on Base44
- Timeline: 3–5 days to MVP
- Cost: Free or $20/mo
- Pros: Fastest path

### Step 3C: If Both Fail → Test Softr + Airtable
- Set up Airtable database (our JSON structure)
- Build Softr app on top
- Timeline: 5–7 days to MVP
- Cost: $49/mo (Softr) + $20/mo (Airtable Plus)

### Step 2C: If No-Code Doesn't Fit → Custom Development
- Use tech stack decision matrix to choose
- Follow MVP implementation checklist
- Timeline: 10–14 days to MVP
- Cost: Free (Vercel hosting)

---

## Decision Tree

```
START
  │
  ├─ Can Lovable do RTL/Hebrew?
  │   ├─ YES → Build on Lovable (3–5 days) ⭐ PRIORITY
  │   └─ NO → Go to next
  │
  ├─ Can Base44 do RTL/Hebrew?
  │   ├─ YES → Build on Base44 (3–5 days)
  │   └─ NO → Go to next
  │
  ├─ Is Softr + Airtable fast enough?
  │   ├─ YES → Build Softr + Airtable (5–7 days)
  │   └─ NO → Go to next
  │
  └─ Go custom dev (10–14 days)
```

---

## Critical Questions to Answer

### Before Testing Lovable ⭐ NEW PRIORITY
1. Does Lovable support RTL layouts natively?
2. Can we import JSON data or build our data structure manually?
3. Can 3 admins collaborate on the same project?
4. Is public access supported (no login for spectators)?
5. What's the pricing (free tier limits, paid tiers)?
6. Can we export to GitHub?

### Before Testing Base44
1. Does Base44 support RTL layouts natively?
2. Can we import JSON data or build our data structure manually?
3. Can 3 admins have separate accounts with shared access?
4. Is public access free (no login for spectators)?

### Before Testing Softr
1. Can Softr apps support RTL (manual `dir="rtl"`)?
2. Can we connect to Airtable and build custom views?
3. Is $49/mo acceptable for MVP (or start on free tier)?

### Before Custom Dev
1. Do you have 10–14 days to build?
2. Are you comfortable with React/Vue development?
3. Can you handle Git conflicts between 3 admins?

---

## Research Tasks for This Week

**Priority 1: Test Lovable** ⭐ NEW
- [ ] Sign up for Lovable free account
- [ ] Describe GTIL app in natural language
- [ ] Test RTL/Hebrew support
- [ ] Test data structure (can we build drivers/standings/calendar/results?)
- [ ] Test multi-admin collaboration
- [ ] Test GitHub sync
- [ ] Evaluate if it meets requirements

**Priority 2: Test Base44 (if Lovable fails)**
- [ ] Sign up for Base44 free account
- [ ] Describe GTIL app in natural language
- [ ] Test RTL/Hebrew support
- [ ] Test data import/structure
- [ ] Test multi-admin access
- [ ] Evaluate if it meets requirements

**Priority 3: Test Softr (if both fail)**
- [ ] Sign up for Softr free trial
- [ ] Set up Airtable database
- [ ] Connect Softr to Airtable
- [ ] Build standings table
- [ ] Build calendar view
- [ ] Test RTL/Hebrew (manual config)

**Priority 3: Prepare Custom Dev (if no-code fails)**
- [ ] Review tech stack decision matrix
- [ ] Choose framework (Next.js vs. Vue)
- [ ] Choose UI library (Mantine vs. shadcn/ui)
- [ ] Review MVP implementation checklist

---

## Timeline

| Days | Task |
|-------|-------|
| **Day 1** | Test Lovable (RTL, data structure, multi-admin, GitHub) |
| **Day 2** | Decision: Lovable ✅ OR ❓ |
| **Day 2–3** | If Lovable fails → Test Base44 |
| **Day 3** | Decision: Base44 ✅ OR ❓ |
| **Day 3–5** | If one works → Build on chosen platform |
| **Day 3–7** | If both fail → Test Softr + Airtable |
| **Day 7** | Decision: Softr ✅ OR ❓ |
| **Day 8–14** | If no-code fails → Custom dev (fallback) |

**Hard Deadline:** February 26, 2026 (R4 — Sardegna A)

---

## Conclusion

**Recommended path:** Test AI platforms first, starting with Lovable.

1. **Lovable** is top choice (3–5 days) if RTL/Hebrew works + GitHub sync confirmed
2. **Base44** is second choice (3–5 days) if Lovable fails
3. **Softr + Airtable** is solid backup (5–7 days) if both fail
4. **Custom dev** is fallback (10–14 days) if no-code doesn't fit

**Why Lovable first:**
- **Code ownership** (can export to GitHub) — Base44 unknown
- **GitHub integration** — Base44 unknown
- **Full-stack confirmed** — Base44 implied but unknown
- **Enterprise-grade** — Security, governance built in

**Action items:**
1. Test Lovable RTL/Hebrew support
2. Test Lovable multi-admin collaboration
3. Test Lovable GitHub sync
4. Evaluate if UI matches our design
5. Make decision: Lovable ✅ OR ❓ → Base44 ✅ OR ❓

---

*Infrastructure Options Research Version: 1.0*
*Last Updated: February 12, 2026*
