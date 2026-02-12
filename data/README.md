# GTIL Data Schema

## Directory Structure

```
data/
├── drivers.json       # Driver registry with tier/split assignments
├── standings.json     # Current standings (time trials + season)
├── time-trials.json  # Time trial qualifying results
├── results.json       # Race results for all completed rounds
├── calendar.json      # Full season schedule
├── tracks.json        # Track information (18 circuits)
└── README.md         # This file
```

---

## Overview

GTIL 2026 has two separate systems:

1. **Time Trials (TT1, TT2, TT3)** — Qualifying rounds held Jan 26, 2026 to determine tier placement
2. **Championship Season (R1–R18)** — Regular racing season starting Feb 5, 2026

The 41 drivers were assigned to tiers (Split A/B/C) based on their time trial performance.

---

## Schema Definitions

### drivers.json

Driver registry with time trial results and championship tier.

```json
{
  "season": "2026",
  "totalDrivers": 41,
  "timeTrials": {
    "tt1": {
      "date": "2026-01-26",
      "name": "Time Trial 1",
      "description": "Qualifying round for tier placement"
    },
    "tt2": {
      "date": "2026-01-26",
      "name": "Time Trial 2",
      "description": "Qualifying round for tier placement"
    },
    "tt3": {
      "date": "2026-01-26",
      "name": "Time Trial 3",
      "description": "Final qualifying round for tier placement"
    }
  },
  "drivers": [
    {
      "id": "driver-slug",
      "name": "Full Driver Name",
      "tier": 1,
      "split": "A",
      "discordId": null,
      "nationality": null,
      "username": null,
      "ttPosition": 4,
      "ttFastestLap": null,
      "ttPoints": 0
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
- `username`: Optional: Discord username for time trials (from image data)
- `ttPosition`: Final position from time trial qualifying (1–41)
- `ttFastestLap`: Fastest lap time for each track (optional)
- `ttPoints`: Points from time trial system (optional)

---

### standings.json

Contains both time trial qualifying standings and championship season standings.

```json
{
  "season": "2026",
  "lastUpdated": "2026-02-07",
  "timeTrials": {
    "tt1": { "date": "2026-01-26", "name": "Time Trial 1", "description": "Qualifying round" },
    "tt2": { "date": "2026-01-26", "name": "Time Trial 2", "description": "Qualifying round" },
    "tt3": { "date": "2026-01-26", "name": "Time Trial 3", "description": "Final qualifying round" }
  },
  "standings": {
    "timeTrials": {
      "tt1": {
        "date": "2026-01-26",
        "overallLeader": "Itay Sela",
        "overallTime": "3:39.556",
        "tier1": [
          {"position": 1, "driver": "Itay Sela", "time": "3:39.556"},
          {"position": 2, "driver": "Moti Kimchi", "time": "3:40.xxx"},
          ...
        ]
      },
      "tier2": [...],
      "tier3": [...]
    }
  }
}
```

**Notes:**
- Time trial section shows qualifying results from TT1, TT2, TT3
- Each tier has its own standings (top 14, middle 14, bottom 13)
- Overall fastest times displayed
- Season section can be added later for championship rounds (R1–R18)

---

### time-trials.json

Complete time trial results (TT1, TT2, TT3) with full driver data.

```json
{
  "season": "2026",
  "timeTrials": {
    "tt1": {
      "date": "2026-01-26",
      "name": "Time Trial 1",
      "description": "Qualifying round for tier placement"
    },
    "tt2": { "date": "2026-01-26", "name": "Time Trial 2", "description": "Qualifying round" },
    "tt3": { "date": "2026-01-26", "name": "Time Trial 3", "description": "Final qualifying round" }
  },
  "standings": {
    "timeTrials": {
      "tt1": {
        "date": "2026-01-26",
        "overallLeader": "Itay Sela",
        "overallTime": "3:39.556",
        "tier1": [...]
      },
      "tier2": [...],
      "tier3": [...]
    }
  }
}
```

**Notes:**
- TT1 = Initial qualifying round
- TT2 = Second qualifying round
- TT3 = Final qualifying round
- Overall leader is fastest time across all drivers
- Each tier shows individual standings

---

### results.json

Complete race results history for championship season (R1–R18).

```json
{
  "season": "2026",
  "races": [
    {
      "round": 1,
      "name": "Goodwood",
      "date": "2026-02-05",
      "trackId": 1,
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
- `trackId`: Links to `tracks.json`
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
      "trackId": 1,
      "track": "Goodwood",
      "car": "Mazda Roadster Touring Car",
      "format": "Sprint",
      "pointsMultiplier": 1,
      "status": "completed",
      "results": "R1 (Goodwood)"
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
- Time trials (TT1, TT2, TT3) are separate from championship rounds (R1–R18)
- `status`: "completed" | "upcoming" | "cancelled"
- `trackId`: Links to `tracks.json`
- Points multipliers track special rounds

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
- Track `id` maps to `calendar.json` round `trackId` field

---

## Admin Workflow

### After Each Race

1. **Update `calendar.json`:** Set race status to `"completed"`
2. **Add to `results.json`:** Append new race results
3. **Recalculate `standings.json`:** Update season standings by tier
4. **Update `lastUpdated`** in `standings.json`

### For Time Trials

1. **Update `drivers.json`:** Add `ttPosition`, `ttFastestLap`, `ttPoints`, `username` fields
2. **Create/Update `time-trials.json`:** Record qualifying results
3. **Update `standings.json`:** Update time trial standings

---

## Data Integrity Checks

- Total drivers in `drivers.json` should match sum of all split drivers
- `standings.json` driver names should match `drivers.json`
- All rounds in `results.json` should exist in `calendar.json`
- Status should match reality (completed races should have results)
- `trackId` in `results.json`/`calendar.json` should match `id` in `tracks.json`
- Time trial dates should match `timeTrials` section

---

*Last Updated: February 12, 2026*
