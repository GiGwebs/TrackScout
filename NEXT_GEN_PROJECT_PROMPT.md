# TrackScout - State-of-the-Art Project Brief

## 🎯 Vision Statement

**TrackScout** is a modern, performant web application that helps DJs and music enthusiasts discover trending tracks from radio stations and public playlists worldwide, match them against their local music collection, and analyze music trends over time. The app should be blazingly fast, beautifully designed, and dead simple to use.

---

## 🎨 Core Philosophy

**Principles:**

- **Performance First:** Sub-2-second load times for any playlist size (1000+ tracks)
- **Simplicity:** Minimal configuration, maximum automation
- **Global Reach:** Support any radio station/playlist worldwide, not just one region
- **Single Source of Truth:** User picks ONE streaming platform, app optimizes around it
- **Progressive Enhancement:** Works offline, gets better with connectivity
- **Data-Driven:** Historical trend analysis built-in from day one
- **No Reinventing Wheels:** Use proven libraries, frameworks, and patterns

---

## 🎪 User Journey

### First Launch (Setup Wizard)

1. Welcome screen with beautiful onboarding
2. **Choose Your Streaming Platform:** Spotify OR TIDAL OR Apple Music (pick one)
3. Authenticate with chosen platform (OAuth)
4. Point to local DJ collection folder (optional - for ownership matching)
5. Done! → Dashboard

### Daily Workflow

1. Browse trending tracks from:
   - Radio stations worldwide (user can add custom stations)
   - Billboard charts (Hot 100, Global 200, etc.)
   - Spotify Viral charts
   - Other public playlists (user-submitted)
2. See which tracks you own vs. need to acquire
3. One-click export to DJ software (VirtualDJ, Rekordbox, Serato, Traktor)
4. Analyze trends: "What's hot this month vs. last month?"

---

## 🚀 Key Features (MVP)

### 1. **Unified Playlist Discovery**

- Fetch from multiple sources:
  - Radio station playlists (via web scraping or APIs)
  - Billboard charts (official API or scraping)
  - Spotify charts & playlists (Spotify API)
  - User-submitted public playlists
- Single unified interface to browse all sources
- Real-time updates (daily refresh)

### 2. **Smart Track Matching**

- Match playlist tracks against local DJ collection
- Use chosen streaming platform's API for metadata enrichment
- Fuzzy matching for artist/title variations
- AI-powered matching for edge cases (optional, rate-limited)
- Cache all matches for instant subsequent loads

### 3. **Ownership Tracking**

- Visual indicators: ✓ Owned / ✗ Missing
- Filter by ownership status
- Export missing tracks list for acquisition

### 4. **Trend Analysis Dashboard**

- "Hot This Week" vs. "Hot Last Week"
- Track popularity over time (line charts)
- Rising stars (tracks gaining momentum)
- Seasonal patterns (summer hits vs. winter)
- Station comparison (which stations play what)
- Historical data preserved automatically

### 5. **One-Click Export**

- Export to DJ software formats:
  - M3U/M3U8 (universal)
  - VirtualDJ XML
  - Rekordbox XML
  - Serato crates
  - Traktor NML
- Export options:
  - Full playlist
  - Owned tracks only
  - Missing tracks only
  - Tracks above X% match confidence

### 6. **Custom Source Management**

- User can add new radio stations (provide URL)
- User can add public playlists (Spotify/Apple Music links)
- Community-driven: Share discovered sources
- Auto-detect playlist format and scrape

---

## 🎛️ Technical Requirements

### Performance Targets

- **Initial Load:** <1 second (skeleton UI)
- **Playlist Load:** <2 seconds for 1000 tracks
- **Search/Filter:** <100ms response time
- **Export:** <5 seconds for any playlist size
- **Trend Analysis:** <3 seconds to render charts

### Data Management

- **Historical Data:** Keep all playlist snapshots (time-series database)
- **Caching Strategy:** Aggressive caching with smart invalidation
- **Offline Support:** Service workers, IndexedDB for local storage
- **Sync:** Background sync when online

### Scalability

- Support 10,000+ tracks in collection
- Handle 100+ playlists simultaneously
- Trend analysis over 2+ years of data
- Efficient database queries (indexed, optimized)

### User Experience

- **Mobile-First:** Responsive design, works on phones
- **Dark Mode:** Default dark theme (DJ-friendly)
- **Accessibility:** WCAG 2.1 AA compliant
- **Keyboard Shortcuts:** Power-user friendly
- **Loading States:** Skeleton screens, progress indicators
- **Error Handling:** Graceful degradation, helpful error messages

---

## 🛠️ Technical Constraints & Preferences

### What You MUST Consider

1. **Single Streaming Platform:** User picks one (Spotify/TIDAL/Apple Music) at setup

   - Optimize all metadata fetching for chosen platform
   - No need to support all three simultaneously per user
   - Reduces API complexity and rate limit issues

2. **No Language Separation:** Global market, all languages mixed

   - Remove Danish/English filtering
   - Support Unicode properly (Japanese, Arabic, etc.)
   - Auto-detect language if needed for display purposes only

3. **Historical Data from Day One:**

   - Design database schema for time-series data
   - Automatic daily snapshots of all playlists
   - Efficient storage (don't duplicate unchanged data)

4. **Extensible Architecture:**
   - Easy to add new playlist sources (plugins?)
   - Easy to add new export formats
   - Easy to add new streaming platforms

### What You SHOULD Choose (Tech Stack)

**You decide the best stack, but consider:**

**Frontend Options:**

- Modern framework: React, Vue, Svelte, or SolidJS
- State management: Zustand, Jotai, or built-in (Context/Signals)
- Styling: Tailwind CSS, UnoCSS, or CSS-in-JS
- Data fetching: TanStack Query, SWR, or framework-native
- Charts: Recharts, Chart.js, or D3.js
- Build tool: Vite, Turbopack, or Bun

**Backend Options:**

- Runtime: Node.js, Bun, or Deno
- Framework: Express, Fastify, Hono, or tRPC
- Database: PostgreSQL, SQLite, or Supabase
- ORM: Drizzle, Prisma, or Kysely
- Caching: Redis, or in-memory (if lightweight)
- Job Queue: BullMQ, or simple cron jobs

**Deployment:**

- Frontend: Vercel, Netlify, or Cloudflare Pages
- Backend: Railway, Fly.io, or Render
- Database: Supabase, Neon, or PlanetScale

**Choose based on:**

- Fastest development velocity
- Best performance characteristics
- Simplest deployment story
- Lowest operational complexity

---

## 📊 Data Sources & APIs

### Required Integrations

1. **Streaming Platforms (pick one per user):**

   - Spotify Web API (metadata, charts, playlists)
   - TIDAL API (metadata, playlists)
   - Apple Music API (metadata, charts)

2. **Chart Sources:**

   - Billboard API (official or unofficial)
   - Spotify Charts (web scraping or API)
   - Apple Music Charts (API)

3. **Radio Stations:**

   - Generic web scraper (Puppeteer/Playwright)
   - RSS feeds (if available)
   - Station-specific APIs (if available)

4. **Local Collection:**
   - File system scanning (music files)
   - Metadata extraction (ID3 tags, etc.)
   - Rekordbox XML parsing (if user has it)

### Data Schema Considerations

- **Tracks:** artist, title, album, year, BPM, key, genre, ISRC
- **Playlists:** name, source, date, tracks[], metadata
- **Snapshots:** playlist_id, snapshot_date, tracks[]
- **User Collection:** file_path, metadata, streaming_ids
- **Match Cache:** track_key → collection_match (persistent)

---

## 🎨 UI/UX Requirements

### Design Inspiration

- **Spotify:** Clean, dark, music-focused
- **Linear:** Fast, keyboard-driven, minimal
- **Vercel Dashboard:** Modern, performant, delightful

### Key Screens

1. **Dashboard:**

   - "Hot This Week" carousel
   - "Trending Up" section
   - "New Discoveries" section
   - Quick stats (total tracks, owned %, etc.)

2. **Playlists:**

   - Grid/List view toggle
   - Filter by source (Radio, Billboard, Spotify, etc.)
   - Sort by date, popularity, ownership
   - Search across all playlists

3. **Playlist Detail:**

   - Track list with ownership indicators
   - Filter: All / Owned / Missing
   - Search within playlist
   - Export button (prominent)
   - Stats cards (owned, missing, match types)

4. **Trends:**

   - Time-series charts (track popularity over time)
   - Comparison view (this month vs. last month)
   - Station comparison (which stations play what)
   - Genre trends (if metadata available)

5. **Sources:**

   - List of all configured sources
   - Add new source (URL input + auto-detect)
   - Enable/disable sources
   - Community-shared sources (optional)

6. **Settings:**
   - Streaming platform (locked after setup)
   - Collection path
   - Export preferences
   - Refresh schedule
   - Theme (dark/light)

### Interaction Patterns

- **Instant Search:** As-you-type filtering (debounced)
- **Infinite Scroll:** For long lists (virtualized)
- **Keyboard Shortcuts:**
  - `/` → Search
  - `e` → Export
  - `r` → Refresh
  - `Esc` → Close modals
- **Drag & Drop:** Reorder playlists, tracks
- **Right-Click Menus:** Context actions
- **Toast Notifications:** Success/error feedback

---

## 🚨 Critical Success Factors

### Must-Haves (Non-Negotiable)

1. **Fast:** No loading spinners >2 seconds
2. **Reliable:** Graceful error handling, no crashes
3. **Simple:** Grandma could use it
4. **Beautiful:** Looks professional, feels premium
5. **Accurate:** Matching works 90%+ of the time

### Nice-to-Haves (Future)

1. AI-powered recommendations
2. Collaborative playlists (share with friends)
3. Mobile app (React Native/Flutter)
4. Browser extension (quick add playlists)
5. Email reports (weekly digest)
6. Integration with DJ software (direct import)

---

## 📝 Development Approach

### Phase 1: Foundation (Week 1-2)

- Setup wizard (streaming platform selection)
- Basic playlist fetching (1-2 sources)
- Track matching (fuzzy + streaming API)
- Simple UI (dashboard + playlist detail)

### Phase 2: Core Features (Week 3-4)

- Multiple playlist sources (radio, charts)
- Export functionality (M3U, VDJ)
- Ownership tracking
- Search & filtering

### Phase 3: Trends & Polish (Week 5-6)

- Historical data collection
- Trend analysis dashboard
- Performance optimization
- UI polish & animations

### Phase 4: Extensibility (Week 7-8)

- Custom source management
- Additional export formats
- Community features (optional)
- Documentation & deployment

---

## 🎓 Best Practices to Follow

### Code Quality

- **TypeScript:** Strict mode, no `any`
- **Testing:** Unit tests for critical paths, E2E for user flows
- **Linting:** ESLint, Prettier, consistent style
- **Documentation:** JSDoc for complex functions, README for setup
- **Git:** Conventional commits, feature branches, PR reviews

### Performance

- **Code Splitting:** Lazy load routes, components
- **Image Optimization:** WebP, lazy loading, responsive
- **Bundle Size:** Keep <200KB initial JS
- **Caching:** Aggressive caching with smart invalidation
- **Database:** Indexed queries, connection pooling

### Security

- **Auth:** OAuth 2.0, secure token storage
- **API Keys:** Environment variables, never committed
- **Input Validation:** Sanitize all user inputs
- **CORS:** Proper configuration
- **Rate Limiting:** Prevent abuse

### Deployment

- **CI/CD:** Automated testing, deployment
- **Monitoring:** Error tracking (Sentry), analytics
- **Logging:** Structured logs, searchable
- **Backups:** Automated database backups
- **Rollback:** Easy rollback mechanism

---

## 🎯 Success Metrics

### Technical

- Lighthouse score: 90+ (Performance, Accessibility, Best Practices)
- Bundle size: <200KB initial, <1MB total
- API response time: <500ms p95
- Database query time: <100ms p95
- Error rate: <0.1%

### User Experience

- Time to first playlist: <5 seconds
- Match accuracy: >90%
- Export success rate: >99%
- User retention: >60% (week 2)

---

## 🚀 Deliverables

1. **Working Application:**

   - Deployed and accessible via URL
   - Setup wizard functional
   - At least 3 playlist sources working
   - Export to 2+ formats working
   - Trend analysis dashboard functional

2. **Documentation:**

   - README with setup instructions
   - Architecture overview
   - API documentation
   - User guide (screenshots)

3. **Code Quality:**

   - Clean, readable, well-structured
   - TypeScript with proper types
   - Tests for critical functionality
   - No console errors or warnings

4. **Deployment:**
   - Production-ready deployment
   - Environment variables documented
   - Monitoring & error tracking setup
   - Backup strategy documented

---

## 💡 Implementation Guidance

### Start Simple, Scale Smart

1. **MVP First:** Get one playlist source working end-to-end
2. **Iterate Fast:** Ship small, working features frequently
3. **Measure Everything:** Add analytics from day one
4. **User Feedback:** Test with real DJs early and often

### Avoid Common Pitfalls

- **Don't over-engineer:** YAGNI (You Aren't Gonna Need It)
- **Don't premature optimize:** Profile before optimizing
- **Don't ignore errors:** Handle them gracefully
- **Don't skip testing:** Write tests for critical paths
- **Don't hardcode:** Use config files, environment variables

### Recommended Resources

- **UI Components:** shadcn/ui, Radix UI, Headless UI
- **Icons:** Lucide, Heroicons, Phosphor
- **Animations:** Framer Motion, Auto-Animate
- **Charts:** Recharts, Tremor, Visx
- **Forms:** React Hook Form, Zod validation
- **Tables:** TanStack Table, AG Grid
- **Date/Time:** date-fns, Luxon
- **File Handling:** Papaparse (CSV), xml2js (XML)

---

## 🎬 Final Notes

**This is not just a rebuild—it's a reimagining.**

Take everything we learned from the current Radio Explorer:

- ✅ What worked (fuzzy matching, AI cache, export system)
- ❌ What didn't (language separation, slow loading, complex setup)

Build something **10x better** by:

1. Choosing the RIGHT tech stack for the job
2. Designing for PERFORMANCE from day one
3. Making it GLOBAL, not regional
4. Building TRENDS into the core, not as an afterthought
5. Keeping it SIMPLE for users, sophisticated under the hood

**You have full creative freedom on the tech stack.**  
Choose what will get us to a production-ready app fastest, with the best performance and maintainability.

**The goal:** A DJ's best friend for discovering trending music worldwide, beautifully designed, blazingly fast, and dead simple to use.

Let's build something amazing. 🚀
