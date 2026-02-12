# Admin Form Specification

## Overview

Simple admin interface for managing race results and standings. Built for 3 admins with minimal training required.

---

## Admin Dashboard Pages

### 1. Dashboard Home

**URL:** `/admin`  
**Access:** Admin only (auth TBD)

**Shows:**
- Quick summary: Current round, next race, last updated
- Quick actions: "Add Race Results", "Update Standings", "Manage Drivers"
- Recent activity log (last 10 actions)

---

### 2. Add Race Results

**URL:** `/admin/results/add`  
**Purpose:** Enter results for a completed race

#### Form Fields

**Race Selection:**
- **Round (dropdown):** R1–R18 (from calendar.json)
- **Auto-fill:** Track, car, format, points multiplier

**Results Entry (per split):**

For each split (A/B/C), enter results in order of finish:

| Field | Type | Required |
|-------|------|----------|
| Position | Auto (1, 2, 3...) | Yes |
| Driver | Dropdown (from drivers.json) | Yes |
| Points | Auto-calculate | No |
| DNF | Checkbox | No |
| Penalty Points | Number | No |
| Penalty Seconds | Number | No |

**Bulk Entry Options:**
- "Paste results" — paste from Discord/Excel, auto-parse format
- "Quick fill" — driver dropdown with auto-search

**Validation:**
- Each driver can appear only once per race
- Positions must be sequential (1, 2, 3...)
- Total drivers per split should match split size

**Submit Action:**
1. Add entry to `results.json`
2. Recalculate `standings.json`
3. Update `calendar.json` race status to "completed"
4. Log action
5. Return to dashboard with success message

---

### 3. Manage Calendar

**URL:** `/admin/calendar`  
**Purpose:** View and edit race schedule

**Table View:**
| Round | Track | Date | Car | Format | Status | Actions |
|-------|-------|------|-----|--------|--------|---------|
| R1 | Goodwood | 2026-02-05 | Mazda RT | Sprint | ✅ | Edit |
| R2 | St. Croix | 2026-02-12 | Honda NSX | Sprint | ✅ | Edit |
| R3 | Dragon Trail | 2026-02-19 | Any Gr.3 | Sprint | ⏳ | Edit |

**Actions:**
- "Edit" — Opens modal to update race details
- "Mark as Completed" — Button if results exist
- "Mark as Cancelled" — Button for weather/postponement

---

### 4. Manage Drivers

**URL:** `/admin/drivers`  
**Purpose:** Add, edit, remove drivers

**Table View:**
| Name | Tier | Split | Discord ID | Actions |
|------|------|-------|------------|---------|
| Itay Sela | 1 | A | — | Edit |
| Moti Kimchi | 1 | A | — | Edit |

**Actions:**
- "Add Driver" — Opens form: Name, Tier, Split, Discord ID (optional)
- "Edit Driver" — Opens form with current data
- "Delete Driver" — Confirmation modal
- "Promote/Relegate" — Move driver between tiers (season end only)

---

### 5. Standings Editor

**URL:** `/admin/standings`  
**Purpose:** Manual override of standings (rare use)

**View:**
- Current standings for all tiers
- "Recalculate" button (rebuilds from results.json)
- "Manual Edit" mode for overrides

**Warning:**
- Manual edits should be logged with reason
- Prefer using "Add Race Results" for normal updates

---

## Form UX Principles

### 1. Progressive Disclosure
- Start with required fields only
- Show optional fields on "Advanced" toggle
- Pre-fill data from existing JSON files

### 2. Auto-Save (Draft Mode)
- Save form data to local storage every 30 seconds
- "Restore Draft" on page load if available
- Clear draft after successful submit

### 3. Error Handling
- Inline validation (red borders, error messages)
- Prevent submit on errors
- Show specific error: "Driver 'Itay Sela' already in position 3"

### 4. Confirmation
- "Submit" → Modal: "Confirm results for R1 Goodwood?"
- Show summary: "Split A: 14 drivers, Split B: 12 drivers, Split C: 12 drivers"
- Cancel / Confirm buttons

---

## Admin Actions Log

**Stored in:** `data/admin-log.json`

```json
{
  "actions": [
    {
      "timestamp": "2026-02-12T14:30:00Z",
      "admin": "cherninio",
      "action": "add_race_results",
      "details": "Added results for R1 (Goodwood)",
      "changes": {
        "updated": ["standings.json", "results.json", "calendar.json"]
      }
    }
  ]
}
```

**Display:** Last 10 actions on dashboard home. Full log accessible via `/admin/log`

---

## Access Control

### Phase 1: Simple Password
- Single admin password shared among 3 admins
- Store in environment variable: `ADMIN_PASSWORD`

### Phase 2: Individual Accounts
- Each admin has username + password
- Store in JSON: `data/admins.json`

### Phase 3: Discord Integration
- Admin accounts linked to Discord IDs
- OAuth login via Discord

---

## Mobile Support

**Admin form should work on:**
- Desktop (full features)
- Tablet (slightly compressed layout)
- Mobile (simplified form, results entry only)

---

## Tech Notes

### JSON Operations

**Add Race Results:**
```javascript
// 1. Read existing results.json
const results = JSON.parse(readFileSync('data/results.json'));

// 2. Append new race
results.races.push(newRace);

// 3. Write back
writeFileSync('data/results.json', JSON.stringify(results, null, 2));
```

**Recalculate Standings:**
```javascript
// 1. Start with 0 points for all drivers
// 2. Loop through results.json
// 3. Add points per race
// 4. Sort by points desc
// 5. Update standings.json
```

---

*Last Updated: February 12, 2026*
*Phase: MVP Design*
