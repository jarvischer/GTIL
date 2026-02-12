# GTIL Dashboard — Tech Stack Decision Matrix

## Decision Criteria

For each tech choice, we'll score on 5 factors (1–5 scale):

| Factor | Weight |
|--------|--------|
| **Speed to MVP** (2-week deadline) | 30% |
| **RTL/Hebrew Support** | 25% |
| **Long-term Maintainability** | 20% |
| **Admin Experience** (3 admins) | 15% |
| **Cost** | 10% |

**Scoring:** 1 = Poor, 5 = Excellent

---

## 1. Frontend Framework

### Next.js 14/15 (App Router)

| Factor | Score | Notes |
|--------|-------|-------|
| Speed to MVP | 4 | Fast, but SSR might be overkill for static JSON |
| RTL/Hebrew Support | 5 | next-intl excellent, built-in middleware |
| Long-term Maintainability | 5 | Industry standard, huge ecosystem |
| Admin Experience | 5 | Server actions for form handling |
| Cost | 5 | Free Vercel tier, unlimited deployments |

**Total Weighted Score:** 4.75/5

**Pros:**
- Built-in routing, no config needed
- Server actions = secure admin forms without API routes
- next-intl = best i18n for Next.js
- Vercel deployment = git push → live
- Image optimization built-in
- App Router = modern, future-proof

**Cons:**
- SSR/ISR complexity not needed for static JSON
- Learning curve if you're new to React/Next.js

**Verdict:** ⭐ **RECOMMENDED** — Best balance of speed, features, and future-proofing

---

### Vue 3 + Nuxt 4

| Factor | Score | Notes |
|--------|-------|-------|
| Speed to MVP | 5 | Simpler mental model than React |
| RTL/Hebrew Support | 4 | vue-i18n works, but RTL manual |
| Long-term Maintainability | 4 | Strong ecosystem, but smaller than React |
| Admin Experience | 4 | Great reactivity, forms are easy |
| Cost | 5 | Free Netlify/Vercel deployment |

**Total Weighted Score:** 4.55/5

**Pros:**
- Simpler syntax than React (good for 2-week sprint)
- Vue DevTools excellent for debugging
- vue-i18n mature library
- Lightweight bundle size

**Cons:**
- Fewer component libraries than React
- RTL support requires manual dir="rtl" management
- Nuxt SSR adds complexity like Next.js

**Verdict:** 🟡 **ALTERNATIVE** — Great if you prefer Vue syntax over React

---

### React + Vite

| Factor | Score | Notes |
|--------|-------|-------|
| Speed to MVP | 4 | Fast dev, but manual routing (React Router) |
| RTL/Hebrew Support | 4 | react-i18next, but RTL manual |
| Long-term Maintainability | 5 | React ecosystem is massive |
| Admin Experience | 4 | Client-side forms, need API for backend |
| Cost | 5 | Free Vercel deployment |

**Total Weighted Score:** 4.45/5

**Pros:**
- Fastest dev server (Vite is instant)
- Simple mental model (just React + router)
- Full flexibility (no framework opinion)
- Great for static builds

**Cons:**
- Need to choose/learn React Router
- Client-side forms need API routes (or use Supabase/Firebase)
- No built-in image optimization

**Verdict:** 🟡 **ALTERNATIVE** — Fast, but more manual setup than Next.js

---

### SvelteKit

| Factor | Score | Notes |
|--------|-------|-------|
| Speed to MVP | 4 | Simple, but smaller ecosystem |
| RTL/Hebrew Support | 3 | svelte-i18n exists, but less mature |
| Long-term Maintainability | 3 | Growing ecosystem, but smaller |
| Admin Experience | 3 | Great, but fewer admin libraries |
| Cost | 5 | Free Vercel/Netlify deployment |

**Total Weighted Score:** 3.75/5

**Pros:**
- Smallest bundle size
- Simplest syntax (no JSX)
- Fastest runtime

**Cons:**
- Fewer component libraries (especially for tables/admin)
- Less i18n/RTL support
- Harder to find developers if you need help

**Verdict:** 🔴 **NOT RECOMMENDED** — Too experimental for a 2-week deadline

---

## 2. UI Component Library

### shadcn/ui + Tailwind CSS

| Factor | Score | Notes |
|--------|-------|-------|
| Speed to MVP | 4 | Copy-paste components, but need to build tables |
| RTL/Hebrew Support | 4 | Tailwind supports RTL, need to configure |
| Long-term Maintainability | 5 | You own the code, full control |
| Admin Experience | 5 | Beautiful, accessible, fully customizable |
| Cost | 5 | Free, open source |

**Total Weighted Score:** 4.6/5

**Pros:**
- Copy-paste components into your project (no npm install bloat)
- Beautiful by default, accessible (Radix UI primitives)
- Full customization (it's your code)
- Best table components (TanStack Table integration)
- Tailwind RTL = just add `dir="rtl"` and utilities flip

**Cons:**
- Need to build some components from scratch (customization required)
- No pre-built admin dashboard (unlike Mantine/Shadcn-like libs)

**Verdict:** ⭐ **RECOMMENDED** — Best balance of beauty, control, and long-term flexibility

---

### Mantine

| Factor | Score | Notes |
|--------|-------|-------|
| Speed to MVP | 5 | Pre-built admin dashboard, tables ready |
| RTL/Hebrew Support | 5 | Built-in RTL support, just add dir="rtl" |
| Long-term Maintainability | 4 | Opinionated, but mature |
| Admin Experience | 5 | @mantine/dashboards library |
| Cost | 5 | Free, MIT license |

**Total Weighted Score:** 4.85/5

**Pros:**
- Fastest to MVP (pre-built tables, forms, layouts)
- Best RTL support (automatic RTL mirroring)
- @mantine/dashboards = admin UI out of the box
- TypeScript first, great DX
- Hooks for everything (use-form, use-list, etc.)

**Cons:**
- Opinionated design system (harder to customize completely)
- Larger bundle size than shadcn/ui (but still manageable)
- Locked into Mantine ecosystem (harder to switch later)

**Verdict:** ⭐ **RECOMMENDED** — Fastest for MVP, especially with admin forms

---

### Chakra UI

| Factor | Score | Notes |
|--------|-------|-------|
| Speed to MVP | 4 | Good components, but tables are basic |
| RTL/Hebrew Support | 5 | Built-in RTL, just add dir="rtl" |
| Long-term Maintainability | 4 | Solid, but less active than Mantine |
| Admin Experience | 4 | Good forms, but no admin dashboard |
| Cost | 5 | Free, MIT license |

**Total Weighted Score:** 4.4/5

**Pros:**
- Easy to use (simple API)
- Great RTL support
- Good accessibility

**Cons:**
- Basic table components (need TanStack Table for complex standings)
- No pre-built admin dashboard
- Less active development than Mantine/shadcn

**Verdict:** 🟡 **ALTERNATIVE** — Good, but Mantine is better for admin-heavy apps

---

## 3. Internationalization (i18n)

### next-intl (for Next.js)

| Factor | Score | Notes |
|--------|-------|-------|
| Speed to MVP | 5 | Simple setup, just add middleware |
| RTL/Hebrew Support | 5 | Automatic RTL switching |
| Long-term Maintainability | 5 | Mature, well-maintained |
| Admin Experience | 5 | Admin can edit translations via JSON |
| Cost | 5 | Free, MIT license |

**Total Weighted Score:** 5/5

**Pros:**
- Automatic RTL based on locale (en = LTR, he = RTL)
- Simple translation files (JSON)
- Server-side + client-side support
- Best Next.js integration

**Cons:**
- Next.js only (won't work with Vue/React + Vite)

**Verdict:** ⭐ **RECOMMENDED** — If using Next.js, this is the best choice

---

### vue-i18n (for Vue 3)

| Factor | Score | Notes |
|--------|-------|-------|
| Speed to MVP | 4 | Good, but need manual RTL switching |
| RTL/Hebrew Support | 3 | Manual dir="rtl" management |
| Long-term Maintainability | 5 | Mature library |
| Admin Experience | 4 | JSON translations, easy to edit |
| Cost | 5 | Free, MIT license |

**Total Weighted Score:** 4.1/5

**Pros:**
- Standard Vue i18n library
- Good documentation
- JSON translations

**Cons:**
- RTL not automatic (need to wrap app in dir="rtl" based on locale)

**Verdict:** 🟡 **ALTERNATIVE** — Good for Vue, but requires extra RTL work

---

### react-i18next (for React + Vite)

| Factor | Score | Notes |
|--------|-------|-------|
| Speed to MVP | 3 | Complex setup for 2-week deadline |
| RTL/Hebrew Support | 2 | Manual dir="rtl" management |
| Long-term Maintainability | 5 | Industry standard |
| Admin Experience | 4 | JSON translations |
| Cost | 5 | Free, MIT license |

**Total Weighted Score:** 3.45/5

**Pros:**
- Most popular React i18n library
- Flexible, powerful

**Cons:**
- Complex setup (namespaces, plugins)
- RTL not automatic
- Overkill for simple bilingual dashboard

**Verdict:** 🔴 **NOT RECOMMENDED** — Too complex for 2-week deadline

---

## 4. Hosting Platform

### Vercel

| Factor | Score | Notes |
|--------|-------|-------|
| Speed to MVP | 5 | Git push → live in seconds |
| RTL/Hebrew Support | 5 | N/A (handled by app) |
| Long-term Maintainability | 5 | Preview deployments, rollbacks |
| Admin Experience | 5 | All admins can deploy via git |
| Cost | 5 | Free tier generous (100GB bandwidth) |

**Total Weighted Score:** 5/5

**Pros:**
- Best developer experience (zero config)
- Preview deployments for testing (admin-pr-1.vercel.app)
- Automatic SSL, CDN, edge network
- Team support (multiple collaborators)
- Best Next.js integration

**Cons:**
- Free tier: 100GB bandwidth (should be enough for static dashboard)
- Limited serverless function time (not needed for JSON-based app)

**Verdict:** ⭐ **RECOMMENDED** — Best for Next.js, great DX for teams

---

### Netlify

| Factor | Score | Notes |
|--------|-------|-------|
| Speed to MVP | 5 | Git push → live |
| RTL/Hebrew Support | 5 | N/A (handled by app) |
| Long-term Maintainability | 5 | Good, but fewer features than Vercel |
| Admin Experience | 4 | Good, but preview URLs clunky |
| Cost | 5 | Free tier generous |

**Total Weighted Score:** 4.8/5

**Pros:**
- Great for static sites
- Netlify Forms (could use for admin contact)
- Build hooks, scheduled builds

**Cons:**
- Preview deployments URLs are less intuitive
- Slightly slower builds than Vercel

**Verdict:** 🟡 **ALTERNATIVE** — Great for Vue/React + Vite, but Vercel wins for Next.js

---

### Railway

| Factor | Score | Notes |
|--------|-------|-------|
| Speed to MVP | 3 | Need to set up Docker/service |
| RTL/Hebrew Support | 5 | N/A (handled by app) |
| Long-term Maintainability | 4 | Good for full-stack apps |
| Admin Experience | 3 | Need backend API for admin forms |
| Cost | 3 | $5/mo starting (not free) |

**Total Weighted Score:** 3.7/5

**Pros:**
- Full-stack hosting (frontend + backend + database)
- Good for future Discord bot integration

**Cons:**
- Not needed for MVP (static JSON only)
- Cost not zero ($5/mo minimum)
- More complexity than Vercel/Netlify

**Verdict:** 🔴 **NOT RECOMMENDED** — Overkill for static JSON dashboard

---

## Final Recommendations

### Stack Option A: Next.js + Mantine + Vercel ⭐ BEST FOR SPEED

```
Framework:    Next.js 15 (App Router)
UI Library:   Mantine (@mantine/core, @mantine/dashboards)
i18n:         next-intl
Hosting:      Vercel
Styling:      Mantine (Tailwind optional)
Auth:         Simple password (Phase 1) → Discord OAuth (Phase 2)
Data:         JSON files (Git-based)
```

**Why:**
- Fastest to MVP (Mantine pre-built tables/admin forms)
- Best RTL support (Mantine automatic, next-intl automatic)
- Great admin experience (pre-built dashboard components)
- Long-term maintainable (Next.js is industry standard)

**Estimated MVP Time:** 10–12 days

---

### Stack Option B: Vue 3 + Nuxt 4 + shadcn/ui + Netlify 🟡 BALANCED

```
Framework:    Nuxt 4
UI Library:   shadcn/ui + Tailwind CSS
i18n:         @nuxtjs/i18n
Hosting:      Netlify
Styling:      Tailwind CSS
Auth:         Simple password
Data:         JSON files (Git-based)
```

**Why:**
- If you prefer Vue over React (simpler mental model)
- shadcn/ui = beautiful, customizable components
- Nuxt = fast, built-in routing

**Estimated MVP Time:** 12–14 days

---

### Stack Option C: Next.js + shadcn/ui + Vercel 🟡 FUTURE-PROOF

```
Framework:    Next.js 15 (App Router)
UI Library:    shadcn/ui + Tailwind CSS
i18n:          next-intl
Hosting:       Vercel
Styling:       Tailwind CSS
Auth:          Simple password
Data:          JSON files (Git-based)
```

**Why:**
- Most flexible (you own all the code)
- Tailwind = fastest styling, full RTL support
- Best long-term (no locked-in library)
- Slightly slower to build custom tables

**Estimated MVP Time:** 12–14 days

---

## Decision Checklist

Before finalizing, confirm:

- [ ] Team is comfortable with chosen framework (React/Next.js or Vue/Nuxt)?
- [ ] RTL support is automatic or well-documented?
- [ ] Admin forms will be easy for 3 admins to use?
- [ ] Hosting is free or low-cost for MVP?
- [ ] Deployment workflow is simple (git push)?

---

*Tech Stack Decision Matrix Version: 1.0*
*Last Updated: February 12, 2026*
