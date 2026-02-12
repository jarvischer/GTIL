# GTIL Dashboard — Research Plan

## Overview

Separate research tasks to complete before or during development. Prioritized by impact and dependencies.

---

## Priority 1: Framework & Hosting (Before Development)

### 1.1 Frontend Framework Selection

**Goal:** Choose the right framework for rapid MVP delivery + long-term maintainability

**Options to Research:**
| Framework | Pros | Cons | Learning Curve |
|-----------|------|------|----------------|
| **Next.js** | Built-in routing, SSR, API routes, Vercel deployment | Overkill for simple dashboard? | Medium |
| **Vue 3** | Simple, fast, great docs | Smaller ecosystem than React | Low |
| **React + Vite** | Popular, fast dev, simple setup | Manual routing setup | Medium |
| **Svelte** | Fast, small bundle | Smaller ecosystem | Low |

**Research Questions:**
1. Which framework has the best RTL/i18n libraries for Hebrew support?
2. Which has the best UI component library (shadcn, Chakra, etc.)?
3. Which is fastest to prototype for a 2-week deadline?
4. Which has the easiest deployment workflow?

**Deliverable:** Framework recommendation with 3 key reasons

**Timeline:** Day 1–2

---

### 1.2 UI Component Library Selection

**Goal:** Choose a component library that supports RTL, has good table components, and fits the design system

**Options to Research:**
| Library | RTL Support | Tables | Documentation |
|---------|-------------|--------|---------------|
| **shadcn/ui** | ✅ Good | ✅ Excellent | ✅ Excellent |
| **Chakra UI** | ✅ Excellent | ✅ Good | ✅ Good |
| **Mantine** | ✅ Excellent | ✅ Excellent | ✅ Good |
| **Tailwind UI** | ✅ Good | ✅ Good | ✅ Good |
| **Headless UI** | ✅ Manual | ✅ Manual | ✅ Good |

**Research Questions:**
1. Which has the best pre-built table component for standings/results?
2. Which has the easiest RTL setup (just add dir="rtl")?
3. Which has the most customization options without locking you in?
4. Which has the best community support for Hebrew layouts?

**Deliverable:** UI library recommendation + demo of table component

**Timeline:** Day 2 (after framework selection)

---

### 1.3 Hosting & Deployment Strategy

**Goal:** Determine where to host the dashboard and how to deploy updates

**Options to Research:**
| Platform | Cost | Deployment | Features |
|----------|------|------------|----------|
| **Vercel** | Free tier generous | Git push → auto deploy | Edge, analytics |
| **Netlify** | Free tier generous | Git push → auto deploy | Forms, functions |
| **Railway** | $5/mo starting | Docker or Git | Full app + DB |
| **Self-hosted** | $0 (if using existing server) | Manual or CI/CD | Full control |
| **Cloudflare Pages** | Free | Git push → auto deploy | Edge, analytics |

**Research Questions:**
1. Which platform is easiest for multiple admins to update (not just you)?
2. Which has the best free tier for a static dashboard (no backend needed for MVP)?
3. Which has the best preview deployments for testing?
4. Which has the best custom domain support (GTIL.il or subdomain)?

**Deliverable:** Hosting recommendation + deployment workflow document

**Timeline:** Day 2 (parallel with UI library research)

---

## Priority 2: Authentication & Admin Access (Week 1)

### 2.1 Admin Authentication Strategy

**Goal:** Secure admin access for you + 2 others

**Options to Research:**
| Approach | Complexity | Security | User Experience |
|----------|------------|----------|-----------------|
| **Simple Password** | Low | Low (shared secret) | Simple |
| **Individual Accounts** | Medium | Medium | Good |
| **Discord OAuth** | High | High | Excellent |
| **GitHub OAuth** | Medium | High | Good |

**Research Questions:**
1. Can we implement simple password for MVP and upgrade later?
2. Is Discord OAuth easy to implement with the chosen framework?
3. How do we handle admin revocation if someone leaves the team?
4. Do we need activity logging for audit trails?

**Deliverable:** Auth strategy recommendation + implementation plan

**Timeline:** Week 1, Day 3

---

### 2.2 Admin Permission Model

**Goal:** Define what each admin can do

**Questions to Answer:**
1. All admins have full access? Or different roles (admin vs. editor)?
2. Can admins delete historical data? Or only add new results?
3. How to handle conflicting edits (two admins updating same race)?

**Deliverable:** Permission matrix document

**Timeline:** Week 1, Day 4

---

## Priority 3: Internationalization (i18n) & RTL (Week 1)

### 3.1 Hebrew Localization Library

**Goal:** Choose the right i18n library for English/Hebrew switching

**Options to Research:**
| Library | Framework Support | RTL Handling | Translation Format |
|----------|------------------|--------------|-------------------|
| **next-intl** | Next.js | ✅ Built-in | JSON files |
| **vue-i18n** | Vue 3 | ✅ Manual | JSON files |
| **react-i18next** | React | ✅ Manual | JSON files |
| **FormatJS** | Framework-agnostic | ✅ Manual | JSON files |

**Research Questions:**
1. Which library handles RTL layout switching automatically?
2. Which has the easiest translation key management for ongoing updates?
3. Which has the best TypeScript support?

**Deliverable:** i18n library recommendation + translation file structure

**Timeline:** Week 1, Day 3

---

### 3.2 Hebrew Font Selection

**Goal:** Choose a Hebrew font that pairs well with the English font (Inter)

**Options to Research:**
| Font | Web Support | Pairing with Inter |
|------|-------------|-------------------|
| **Heebo** | Google Fonts | ✅ Excellent |
| **Assistant** | Google Fonts | ✅ Good |
| **Rubik** | Google Fonts | ✅ Good |
| **Segoe UI** | System (Windows) | ✅ Native |

**Research Questions:**
1. Which Google Font is most legible at small sizes (mobile tables)?
2. Which has the best weight variety (400, 500, 600, 700)?
3. Which loads fastest (font weight/size)?

**Deliverable:** Font recommendation + font-face implementation

**Timeline:** Week 1, Day 4

---

## Priority 4: Data Management (Week 1–2)

### 4.1 JSON Data Sync Strategy

**Goal:** Define how the 3 admins will sync JSON files without conflicts

**Options to Research:**
| Approach | Pros | Cons | Conflict Handling |
|----------|------|------|------------------|
| **Git-based** | Versioned, audit trail | Merge conflicts | Manual resolution |
| **Database + Admin Form** | No file conflicts | Requires backend | Automatic |
| **Cloud Storage** | Real-time sync | Overkill for JSON | Last-write-wins |

**Research Questions:**
1. Can we use GitHub as the "database" for JSON files?
2. How do we prevent two admins from overwriting each other's changes?
3. Can we implement a simple locking mechanism (admin A editing = admin B read-only)?

**Deliverable:** Data sync strategy + conflict resolution workflow

**Timeline:** Week 1, Day 5

---

### 4.2 Backup & Recovery Strategy

**Goal:** Ensure data isn't lost if someone deletes the JSON or deployment fails

**Questions to Answer:**
1. How often should we backup JSON files?
2. Where are backups stored (GitHub releases, cloud storage, etc.)?
3. How do we restore from backup if data is corrupted?

**Deliverable:** Backup automation script + recovery procedure

**Timeline:** Week 2, Day 1

---

## Priority 5: Performance Optimization (Week 2)

### 5.1 Image Optimization

**Goal:** Optimize driver avatars, track images, and other media

**Questions to Answer:**
1. Do we have track images? If not, skip for MVP
2. Do we have driver avatars? If not, use initials
3. What image format/size for optimal loading (WebP, < 50KB)?

**Deliverable:** Image optimization guidelines

**Timeline:** Week 2, Day 2

---

### 5.2 Caching Strategy

**Goal:** Make the dashboard feel fast even with large JSON files

**Questions to Answer:**
1. Should we cache JSON files in the browser?
2. How long should the cache last (5 min, 30 min, 1 hour)?
3. How do we invalidate cache when data is updated?

**Deliverable:** Caching implementation (service worker or headers)

**Timeline:** Week 2, Day 3

---

## Priority 6: Future Features (Post-MVP)

### 6.1 Discord Bot Integration

**Goal:** Automatic results posting to Discord channels

**Research Questions:**
1. Discord bot library for the chosen framework?
2. Webhook vs. bot token authentication?
3. Embed formatting for results (tables, emojis)?

**Deliverable:** Discord bot POC (Proof of Concept)

**Timeline:** Post-MVP (Phase 2)

---

### 6.2 Mobile App Development

**Goal:** iOS/Android companion app

**Research Questions:**
1. React Native vs. Flutter vs. PWA?
2. Push notification provider (OneSignal, Firebase)?
3. App store deployment process?

**Deliverable:** Mobile tech stack recommendation

**Timeline:** Post-MVP (Phase 3)

---

## Research Timeline Summary

| Week | Tasks |
|------|-------|
| **Week 1, Day 1–2** | Framework selection, UI library, hosting |
| **Week 1, Day 3–4** | Authentication strategy, i18n/RTL, Hebrew fonts |
| **Week 1, Day 5** | Data sync strategy, conflict resolution |
| **Week 2, Day 1** | Backup & recovery |
| **Week 2, Day 2–3** | Performance optimization (images, caching) |
| **Post-MVP** | Discord bot, mobile app |

---

## Research Output Format

For each research task, produce:

1. **Recommendation** (1 paragraph, clear choice + 3 reasons)
2. **Pros/Cons Table** (compared to alternatives)
3. **Implementation Notes** (specific library versions, configuration steps)
4. **Risks & Mitigations** (what could go wrong, how to avoid)

---

*Research Plan Version: 1.0*
*Last Updated: February 12, 2026*
