# GTIL Dashboard — Product Requirements Document

## Project Overview

**Product:** GTIL Dashboard  
**Purpose:** Real-time tracking and visualization of the Grand Turismo Israel League championship  
**Target Users:** League participants, spectators, race organizers  
**Launch Target:** 2026 Season (Phase 1 by March 2026)

---

## Vision

Create a centralized dashboard for GTIL that provides:

1. **Real-time standings** — Always-current championship points and driver positions
2. **Race calendar** — Visual schedule with upcoming events and results
3. **Driver profiles** — Individual stats, performance history, tier standings
4. **Live race updates** — Race day leaderboard and position changes
5. **Historical data** — Archive of past seasons, race results, and statistics

---

## Core Features (MVP)

### 1. Championship Standings

- Current season standings by tier (Tier 1, Tier 2, Tier 3)
- Points totals with breakdown per race
- Position changes (up/down arrows)
- Promotion/relegation zones highlighted
- Last updated timestamp

### 2. Race Calendar

- Visual calendar of all 18 rounds
- Past races with results links
- Upcoming races with countdown
- Track information (name, car restrictions, format)
- Points multiplier indicators (Sprint/Double/Triple)

### 3. Driver Profiles

- Driver name, tier, current position
- Season statistics: races, podiums, wins, DNFs
- Points breakdown per race
- Average finishing position
- Historical performance (season-by-season)

### 4. Race Results

- Results page for each completed race
- Full finishing order with times
- Points awarded
- Penalty notes
- Fastest lap

---

## Future Features (Phase 2)

### Live Race Updates
- Real-time leaderboard during races
- Position change indicators
- Lap counter
- Current leader gap

### Statistics & Analytics
- Driver vs. driver head-to-head
- Track performance averages
- Car performance by tier
- DNF rates by track/car

### Social Features
- Share results to Discord/Twitter
- Driver comments/notes
- Community polls (Driver of the Race)

### Mobile App
- iOS/Android companion app
- Push notifications for race results
- Calendar sync with personal calendars

---

## Technical Requirements

### Tech Stack

**Frontend:**
- [ ] Framework: Next.js / React / Vue (TBD)
- [ ] UI Library: Tailwind CSS / shadcn/ui (TBD)
- [ ] Charts: Chart.js / Recharts (TBD)
- [ ] Icons: Lucide / Heroicons (TBD)

**Backend:**
- [ ] API: Custom REST API or GraphQL
- [ ] Database: PostgreSQL / MongoDB (TBD)
- [ ] Hosting: Vercel / Netlify / Railway (TBD)

**Data Source:**
- [ ] Manual data entry (admin dashboard)
- [ ] API integration with Discord bot (race results)
- [ ] Webhook for real-time updates

### Performance
- Page load < 2 seconds
- Mobile responsive (320px–1920px)
- Real-time updates < 500ms

### Accessibility
- WCAG 2.1 AA compliant
- Keyboard navigation
- Screen reader support

---

## User Stories

### As a Driver
- I want to see my current standing and points in real time
- I want to know when the next race is and what car to use
- I want to view my race history and identify improvement areas
- I want to see if I'm in promotion/relegation zone

### As a Spectator
- I want to follow the championship standings across all tiers
- I want to see upcoming races with track and car info
- I want to check results after each race
- I want to view individual driver profiles and stats

### As a Race Organizer
- I want to manually enter race results
- I want to update points standings after each race
- I want to promote/relegate drivers between tiers
- I want to manage driver registrations

---

## Non-Functional Requirements

### Security
- Admin-only access for data modification
- Rate limiting on public endpoints
- No sensitive driver data exposed publicly

### Reliability
- 99.5% uptime during race days
- Automatic backups of championship data
- Rollback capability for data errors

### Scalability
- Support up to 100 concurrent users (Phase 1)
- Support up to 1,000 concurrent users (Phase 2)
- Historical data retention for 5+ seasons

---

## Success Metrics

### Engagement
- 50+ unique daily users (drivers + spectators)
- 80% of drivers visiting dashboard weekly
- Average session time > 5 minutes

### Performance
- Page load time < 2s (p95)
- Zero data errors in championship standings
- Race results posted within 1 hour of race end

### Adoption
- 90% of registered drivers claim their profiles
- 100% race results uploaded on schedule

---

## Roadmap

### Phase 1: MVP (March 2026)
- [ ] Frontend framework setup
- [ ] Database schema design
- [ ] Championship standings page
- [ ] Race calendar page
- [ ] Driver profile pages
- [ ] Admin dashboard for data entry
- [ ] Basic deployment

### Phase 2: Live Updates (May 2026)
- [ ] Real-time race leaderboard
- [ ] WebSocket integration
- [ ] Push notifications
- [ ] Statistics and analytics

### Phase 3: Mobile & Social (July 2026)
- [ ] Mobile app (iOS/Android)
- [ ] Social sharing features
- [ ] Community features
- [ ] Multi-language support (Hebrew, English)

---

## Open Questions

- **Data entry:** Manual or automated via Discord bot?
- **Hosting:** Vercel for frontend, where for backend?
- **Authentication:** Driver verification method (Discord ID, email)?
- **Language:** English-only or bilingual (English/Hebrew)?
- **Budget:** Hosting and third-party service limits?

---

## Dependencies

- **Design:** Figma mockups for UI/UX
- **Data:** 2026 season schedule, driver list, race results format
- **Discord:** Bot integration for automated results (optional Phase 2)
- **Hosting:** Domain name (GTIL.il or subdomain)

---

*PRD Version: 1.0*  
*Last Updated: February 12, 2026*  
*Owner: GTIL League*
