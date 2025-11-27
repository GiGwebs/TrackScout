# TrackScout - AI Assistant Kickoff Prompt

## 🎯 Project Overview

I want to build **TrackScout** - a modern, high-performance web application for DJs to discover trending tracks from radio stations and public playlists worldwide, match them against their local music collection, and analyze music trends over time.

---

## 📋 Complete Documentation

Please review these two comprehensive specification documents:

### 1. Full Technical Specification

**File:** `NEXT_GEN_PROJECT_PROMPT.md`  
**GitHub:** https://github.com/GiGwebs/TrackScout/blob/main/NEXT_GEN_PROJECT_PROMPT.md

This document contains:

- Complete vision and philosophy
- Detailed feature specifications
- Technical requirements and constraints
- UI/UX requirements
- Data sources and APIs
- Development phases
- Best practices and success metrics

### 2. Quick Start Guide

**File:** `QUICK_START_PROMPT.md`  
**GitHub:** https://github.com/GiGwebs/TrackScout/blob/main/QUICK_START_PROMPT.md

This document contains:

- Executive summary
- Key differentiators from previous version
- MVP feature list
- 8-week development roadmap
- Quick technical targets

---

## 🎯 Your Mission

Build TrackScout as a **greenfield project** with full creative freedom on tech stack and architecture.

### Non-Negotiable Requirements

1. **Performance:** <2 second load times for 1000+ track playlists
2. **Simplicity:** Minimal configuration, maximum automation
3. **Global Reach:** Support any radio station/playlist worldwide (no language restrictions)
4. **Single Streaming Platform:** User picks ONE (Spotify/TIDAL/Apple Music) at setup
5. **Trends Built-In:** Historical data and trend analysis from day one

### Tech Stack Freedom

**You decide the optimal stack!** Choose based on:

- Fastest development velocity
- Best performance characteristics
- Simplest deployment story
- Lowest operational complexity

Suggestions are provided in the specs, but feel free to propose better alternatives with justification.

---

## 🚀 Phase 1: Foundation (Weeks 1-2)

Let's start with the MVP foundation:

1. **Setup Wizard**

   - Welcome screen with onboarding
   - Streaming platform selection (Spotify/TIDAL/Apple Music)
   - OAuth authentication
   - DJ collection path configuration (optional)

2. **Basic Playlist Fetching**

   - Implement 1-2 playlist sources (e.g., one radio station + Spotify charts)
   - Parse and normalize track data

3. **Track Matching**

   - Fuzzy matching against local collection
   - Streaming API metadata enrichment
   - Match result caching

4. **Simple UI**
   - Dashboard with playlist overview
   - Playlist detail page with track list
   - Ownership indicators (owned/missing)
   - Basic search and filtering

---

## 💡 Context & Background

### What We're Building On

This is a complete rebuild of "Danish Radio Explorer" with lessons learned:

**✅ What Worked:**

- Fuzzy matching algorithm (keep this approach)
- AI-powered matching with caching (implement better)
- Export system to DJ software formats (port this)
- Dark UI aesthetic (maintain this)

**❌ What Didn't Work:**

- Slow loading (226 seconds for 648 tracks - unacceptable!)
- Language separation (Danish/English - too limiting)
- Complex setup (too many configuration steps)
- Performance bottlenecks (synchronous processing)
- Playback error loops (don't implement playback in MVP)

### Repository Information

- **GitHub:** https://github.com/GiGwebs/TrackScout
- **Local Path:** `/Users/gigwebs/Documents/GitHub/TrackScout`
- **Status:** Empty repo, ready for initial implementation

---

## 🎨 Design Principles

### Inspiration

- **Spotify:** Clean, dark, music-focused
- **Linear:** Fast, keyboard-driven, minimal
- **Vercel Dashboard:** Modern, performant, delightful

### Key Interactions

- Instant search (as-you-type, debounced)
- Keyboard shortcuts (/, e, r, Esc)
- Infinite scroll (virtualized for performance)
- Toast notifications for feedback
- Dark mode by default (DJ-friendly)

---

## 📊 Success Metrics

### Technical Targets

- Lighthouse score: 90+ (all categories)
- Bundle size: <200KB initial JS
- API response: <500ms p95
- Database query: <100ms p95
- Error rate: <0.1%

### User Experience Targets

- Time to first playlist: <5 seconds
- Match accuracy: >90%
- Export success rate: >99%

---

## 🤝 Let's Start!

### First Discussion Points

Before we start coding, I'd like your input on:

1. **Tech Stack Recommendation**

   - What frontend framework do you recommend and why?
   - What backend framework/runtime?
   - What database solution?
   - What deployment strategy?

2. **Architecture Approach**

   - How would you structure the application?
   - How would you handle the time-series data for trends?
   - How would you optimize for the <2s load time requirement?

3. **Phase 1 Implementation Plan**
   - What should we build first?
   - What's the critical path to a working MVP?
   - Any potential blockers or challenges you foresee?

### Development Approach

- **Start Simple:** One playlist source, basic UI, core matching
- **Iterate Fast:** Ship small, working features frequently
- **Measure Everything:** Add analytics and monitoring from day one
- **Test Early:** Get feedback from real DJs as soon as possible

---

## 📝 Important Notes

### What NOT to Include in MVP

- ❌ Playback functionality (caused issues in previous version)
- ❌ Complex AI matching (start with fuzzy, add AI later)
- ❌ Multiple streaming platforms (user picks ONE)
- ❌ Advanced trend analysis (basic trends in Phase 1, advanced in Phase 3)

### What to Prioritize

- ✅ Fast loading and responsiveness
- ✅ Simple, intuitive UX
- ✅ Reliable matching
- ✅ Clean, maintainable code
- ✅ Proper error handling

---

## 🎯 Ready to Build!

I'm excited to work with you on TrackScout. Let's create something amazing that DJs around the world will love to use.

**Next Step:** Please review the specification documents and share your recommended tech stack and architectural approach. Once we align on the foundation, we'll start building Phase 1!

---

## 📚 Quick Reference Links

- **Full Spec:** https://github.com/GiGwebs/TrackScout/blob/main/NEXT_GEN_PROJECT_PROMPT.md
- **Quick Start:** https://github.com/GiGwebs/TrackScout/blob/main/QUICK_START_PROMPT.md
- **Repository:** https://github.com/GiGwebs/TrackScout
- **This Prompt:** https://github.com/GiGwebs/TrackScout/blob/main/AI_KICKOFF_PROMPT.md
