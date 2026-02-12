# GTIL Data Schema

## Directory Structure

```
data/
├── drivers.json       # Driver registry with tier/split assignments
├── standings.json     # Current championship standings by tier
├── results.json       # Race results for all completed rounds
├── calendar.json      # Full season schedule
├── tracks.json        # Track information (18 circuits)
└── README.md         # This file
```

---

## Schema Definitions

### drivers.json

Driver registry with metadata and current points.

```json
{
  "season": "2026",
  "totalDrivers": 41,
  "drivers": [
    {
      "id": "driver-slug",
      "name": "Full Driver Name",
      "tier": 1,
      "split": "A",
      "discordId": null,
      "nationality": null,
      "points": 34  // Current season points
    }
  ]
}
```

**Notes:**
- `id` should be kebab-case of the driver name for URL routing
- `tier`: 1 = Split A, 2 = Split B, 3 = Split C
- `split`: Letter designation (A/B/C)
- `discordId`: Optional: Discord user ID for linking
- `nationality`: Optional: Country code (IL, US, etc.)
- `points`: Current season points total (synced from standings.json)

---

### standings.json

Current championship standings with position tracking.

```json
{
  "season": "2026",
  "lastUpdated": "2026-02-07",
  "tier1": {
    "name": "Split A",
    "standings": [
      {
        "position": 1,
        "driver": "Driver Name",
        "points": 34,
        "change": 0
      }
    ],
    "promotionZone": [],
    "relegationZone": [13, 14]
  },
  "tier2": {
    "name": "Split B",
    "standings": [...],
    "promotionZone": [1, 2, 3],
    "relegationZone": []
  },
  "tier3": {
    "name": "Split C",
    "standings": [...],
    "promotionZone": [1, 2, 3],
    "relegationZone": []
  }
}
```

**Notes:**
- `change`: 0 = no change, positive = moved down, negative = moved up
- `promotionZone`: Top 3 positions (empty for Tier 1)
- `relegationZone`: Bottom 3 positions (empty for Tier 3)

---

### results.json

Complete race results history with track linkage.

```json
{
  "season": "2026",
  "races": [
    {
      "round": 1,
      "name": "Goodwood",
      "date": "2026-02-05",
      "trackId": 1,  // Links to tracks.json
      "track": "Goodwood",
      "car": "Mazda Roadster Touring Car",
      "format": "Sprint",
      "pointsMultiplier": 1,
      "splits": [
        {
          "split": "A",
          "tier": 1,
          "results": [
            {
              "position": 1,
              "driver": "Driver Name",
              "points": 34
            }
          ]
        }
      ]
    }
  ]
}
```

**Notes:**
- `format`: "Sprint", "Race 100", "Double Points"
- `pointsMultiplier`: 1 = standard, 2 = double, 3 = triple
- `trackId`: Links to `tracks.json` (circuit metadata)
- Results include all finishers for each split

---

### calendar.json

Full season schedule with race details and track linkage.

```json
{
  "season": "2026",
  "totalRounds": 18,
  "races": [
    {
      "round": 1,
      "name": "Goodwood",
      "date": "2026-02-05",
      "trackId": 1,  // Links to tracks.json
      "track": "Goodwood",
      "car": "Mazda Roadster Touring Car",
      "format": "Sprint",
      "pointsMultiplier": 1,
      "status": "completed",  // "completed" | "upcoming" | "cancelled"
      "results": "R1 (Goodwood)"  // Reference to results section
    }
  ],
  "seasonClosingEvent": {
    "name": "Grand Final",
    "date": "2026-07-16",
    "description": "Season closing event"
  }
}
```

**Notes:**
- `status`: "completed" | "upcoming" | "cancelled"
- `trackId`: Links to `tracks.json` (circuit metadata)
- Points multipliers track special rounds (R6 = triple, many double)

---

### tracks.json

Track information for all circuits.

```json
{
  "season": "2026",
  "totalTracks": 18,
  "tracks": [
    {
      "id": 1,
      "name": "Goodwood",
      "location": "United Kingdom",
      "type": "Historic Circuit"
    }
  ]
}
```

**Notes:**
- `type`: Circuit category (Historic, Street, Racing, Endurance, Speedway, etc.)
- `location`: Real-world location for context
- Track `id` maps to `calendar.json` round `trackId` field and `results.json` round `trackId` field

---

## Admin Workflow

### After Each Race

1. **Update `calendar.json`:** Set race status to `"completed"`
2. **Add to `results.json`:** Append new race results (with `trackId` linkage)
3. **Recalculate `standings.json`:** Update positions, points, zones
4. **Update `drivers.json`:** Sync `points` field with current totals
5. **Update `lastUpdated`** in `standings.json`

### Before Season

1. **Initialize `drivers.json`:** Add all drivers with tier/split assignments (all `points` = 0)
2. **Initialize `calendar.json`:** Populate full schedule with status "upcoming" and `trackId` for all rounds
3. **Create empty `results.json`:** `{ "season": "2026", "races": [] }`
4. **Create empty `standings.json`:** All drivers at 0 points

---

## Data Integrity Checks

- Total drivers in `drivers.json` should match sum of all split drivers
- `standings.json` driver names should match `drivers.json`
- `standings.json` `points` totals should match sum of results points
- All rounds in `results.json` should exist in `calendar.json`
- Status should match reality (completed races should have results)
- `trackId` in `results.json`/`calendar.json` should match `id` in `tracks.json`

---

*Last Updated: February 12, 2026*
