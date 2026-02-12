# GTIL Dashboard — Planning Summary

## What We've Built

### Data Structure (`/data/`)
- ✅ `drivers.json` — 41 drivers with tier/split assignments
- ✅ `standings.json` — Round 1 standings by tier
- ✅ `results.json` — R1 results (Goodwood)
- ✅ `calendar.json` — Full 18-round schedule
- ✅ `README.md` — Schema documentation

### Documentation (`/dashboard/`)
- ✅ `prd.md` — Product Requirements Document
- ✅ `ui-ux-design.md` — Detailed UI/UX mockups for all pages
- ✅ `admin-form-spec.md` — Admin form specification
- ✅ `research-plan.md` — Research tasks (framework, hosting, i18n)
- ✅ `tech-stack-decision.md` — Tech stack comparison (custom dev only)
- ✅ `mvp-implementation-checklist.md` — 2-week sprint checklist
- ✅ `lovable-analysis.md` — Detailed Lovable platform analysis
- ✅ `replit-analysis.md` — Detailed Replit platform analysis
- ✅ `infrastructure-options-final.md` — Complete comparison (Replit, Lovable, Base44, Softr, Glide, Airtable, custom dev)
- ✅ `INFRASTRUCTURE_SUMMARY.md` — Quick decision matrix with all options
- ✅ `SUMMARY.md` — This file (planning overview)

---

## Quick Decisions Needed

### 1. Platform Choice (Pick One)

**Testing Strategy:**
1. **Test Lovable first** (Day 1) — Top priority
2. **Test Replit second** (Day 2) — Strong alternative
3. **Test Base44 third** (Day 3, if both fail)
4. **Softr + Airtable** (Backup if all 3 fail)
5. **Custom Dev** (Fallback, 10–14 days)

**Decision needed:** Which platform to test first? Lovable or Replit?

---

## Next Steps

### Immediate (Before Testing)

1. **Choose testing order:** Lovable first, then Replit
2. **Sign up for chosen platform** (start with Lovable)
3. **Describe GTIL app** in natural language
4. **Test critical features:** RTL/Hebrew, data structure, multi-admin, GitHub sync
5. **Make decision:** If works → build (3–5 days), if fails → test next

---

## Data Catch-Up Needed

**R2 (St. Croix B) is tonight (Feb 12).** After the race:

1. Send me the results (Split A/B/C)
2. I'll add to `results.json`
3. I'll recalculate `standings.json`
4. I'll update `calendar.json` (R2 → completed)

**R3 (Dragon Trail) is Feb 19.** We'll need results after that too.

---

## Git Commit Ready

When you approve git operations, the repo will include:

**Files Added:**
- `data/` — All JSON data files + README
- `dashboard/` — PRD, specs, UI/UX design, research, tech stack, MVP checklist, Lovable/Replit analyses
- `league-rules.md` — Renamed from RULES.md
- `README.md` — Updated with schedule and driver rankings

**Next:** Once platform is chosen, create frontend repo and start coding.

---

## Open Questions / Gaps

- [ ] Domain name? (GTIL.il or gtil.jarvischer.com or subdomain)
- [ ] Discord bot integration needed now or later? (Post-MVP)
- [ ] Mobile app needed now or later? (Post-MVP)
- [ ] Historical seasons? (2026 only for MVP)
- [ ] Driver avatars? (Names only for MVP)
- [ ] Track images? (Text only for MVP)

---

## Testing Timeline

| Days | Task |
|-------|-------|
| **Day 1** | Test Lovable (RTL, data structure, multi-admin, GitHub) |
| **Day 2** | Test Replit (RTL, data structure, multi-admin, GitHub, SSH, public) |
| **Day 3** | Decision: Lovable ✅ OR Replit ✅ OR Test Base44 |
| **Day 3–5** | If one works → Build on chosen platform |
| **Day 3–7** | If all fail → Test Softr + Airtable |
| **Day 7** | Decision: Softr ✅ OR ❓ OR ❓ |
| **Day 8–14** | If no-code fails → Custom dev (fallback) |

**Hard Deadline:** February 26, 2026 (R4 — Sardegna A)

---

*Planning Summary Version: 2.0*
*Last Updated: February 12, 2026*
*Deadline: February 26, 2026 (MVP)*
