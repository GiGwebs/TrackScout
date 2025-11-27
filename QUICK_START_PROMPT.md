# TrackScout - Quick Start Prompt

## 🎯 What We're Building

**TrackScout** - A blazingly fast web app for DJs to discover trending music from radio stations and public playlists worldwide, match against their local collection, and analyze trends over time.

---

## ✨ Key Differentiators from Current Version

1. **Global, Not Regional:** Support any radio station/playlist worldwide (no language separation)
2. **Single Streaming Platform:** User picks ONE (Spotify/TIDAL/Apple Music) at setup → simpler, faster
3. **Trends Built-In:** Historical data & trend analysis from day one (not an afterthought)
4. **Performance First:** Sub-2-second loads for 1000+ track playlists
5. **Extensible Sources:** Users can add custom radio stations, Billboard charts, public playlists

---

## 🚀 Core Features (MVP)

### 1. Setup Wizard

- Choose streaming platform (Spotify/TIDAL/Apple Music)
- Authenticate via OAuth
- Point to DJ collection folder (optional)
- Done!

### 2. Playlist Discovery

- Radio stations worldwide (user-addable)
- Billboard charts (Hot 100, Global 200, etc.)
- Spotify/Apple Music charts
- User-submitted public playlists

### 3. Smart Matching

- Match against local DJ collection
- Fuzzy + AI matching (cached for speed)
- Visual indicators: ✓ Owned / ✗ Missing
- Filter by ownership

### 4. Trend Analysis

- "Hot This Week" vs. "Hot Last Week"
- Track popularity over time (charts)
- Rising stars (gaining momentum)
- Station comparison
- Historical data preserved automatically

### 5. One-Click Export

- M3U, VirtualDJ, Rekordbox, Serato, Traktor
- Export: Full / Owned / Missing / High-confidence matches

---

## 🎯 Technical Requirements

### Performance Targets

- Initial load: <1s
- Playlist load: <2s (1000 tracks)
- Search/filter: <100ms
- Export: <5s

### Tech Stack (Your Choice!)

**Choose the best tools for:**

- Fastest development
- Best performance
- Simplest deployment
- Lowest complexity

**Suggestions:**

- Frontend: React/Vue/Svelte + Vite + Tailwind + TanStack Query
- Backend: Node/Bun + Fastify/Hono + PostgreSQL/Supabase
- Deploy: Vercel + Railway/Fly.io

### Data Strategy

- Time-series database for historical snapshots
- Aggressive caching (Redis or in-memory)
- Offline support (Service Workers + IndexedDB)
- Background sync

---

## 🎨 UI/UX Principles

**Inspiration:** Spotify (music-focused) + Linear (fast, minimal) + Vercel (modern, delightful)

**Key Screens:**

1. Dashboard (trending, discoveries, stats)
2. Playlists (grid/list, filter by source)
3. Playlist Detail (tracks, ownership, export)
4. Trends (charts, comparisons)
5. Sources (manage radio stations, playlists)
6. Settings (minimal, smart defaults)

**Interactions:**

- Instant search (as-you-type)
- Keyboard shortcuts (/, e, r, Esc)
- Infinite scroll (virtualized)
- Toast notifications
- Dark mode default

---

## 📊 Success Criteria

### Must-Haves

- ✅ Fast (<2s playlist loads)
- ✅ Reliable (graceful errors, no crashes)
- ✅ Simple (minimal config, max automation)
- ✅ Beautiful (professional, premium feel)
- ✅ Accurate (90%+ match rate)

### Metrics

- Lighthouse: 90+ (all categories)
- Bundle: <200KB initial JS
- API: <500ms p95
- Match accuracy: >90%
- Error rate: <0.1%

---

## 🚀 Development Phases

**Week 1-2:** Foundation

- Setup wizard + streaming auth
- Basic playlist fetching (1-2 sources)
- Track matching (fuzzy + API)
- Simple UI (dashboard + detail)

**Week 3-4:** Core Features

- Multiple sources (radio, charts)
- Export (M3U, VDJ)
- Ownership tracking
- Search & filtering

**Week 5-6:** Trends & Polish

- Historical data collection
- Trend analysis dashboard
- Performance optimization
- UI polish

**Week 7-8:** Extensibility

- Custom source management
- Additional export formats
- Documentation & deployment

---

## 💡 Key Decisions

### What's Different from Current Version?

| Current                            | Next Gen                     |
| ---------------------------------- | ---------------------------- |
| Danish/English separation          | Global (all languages)       |
| Support all 3 streaming platforms  | User picks ONE at setup      |
| Trends as afterthought             | Trends built-in from day one |
| Slow loading (226s for 648 tracks) | <2s for 1000+ tracks         |
| Complex setup                      | 3-step wizard                |
| Fixed sources                      | User-addable sources         |

### What We're Keeping?

✅ Fuzzy matching algorithm  
✅ AI matching with cache  
✅ Export system (VDJ, M3U, etc.)  
✅ Ownership tracking  
✅ Beautiful dark UI

---

## 🎬 Your Mission

**Build the best DJ playlist discovery tool in the world.**

**You have full creative freedom on:**

- Tech stack (choose what's best)
- Architecture (design for performance)
- Implementation details (use best practices)

**Non-negotiables:**

- Performance (<2s loads)
- Simplicity (minimal config)
- Global reach (any station/playlist)
- Trends (built-in from day one)
- Single streaming platform per user

**Resources:**

- Full spec: `NEXT_GEN_PROJECT_PROMPT.md`
- Current codebase: Reference for what worked/didn't
- Your expertise: Choose the right tools for the job

---

## 🚀 Let's Build!

This is a **greenfield project** with lessons learned from the current version.

**Goal:** Production-ready MVP in 8 weeks.

**Approach:**

1. Start simple (one source, basic UI)
2. Iterate fast (ship weekly)
3. Measure everything (analytics from day one)
4. Test with real DJs (early feedback)

**Success = A DJ's best friend for discovering trending music worldwide.**

Let's make it happen! 🎵
