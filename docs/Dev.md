# NexCue - Development Plan

> **Document Type:** Technical Development Plan  
> **Version:** 1.2  
> **Last Updated:** January 27, 2026  
> **Timeline:** 16 Weeks (February 1, 2026 - May 22, 2026)  
> **Team:** 4 Members  
> **Market:** Global (English-first)

---

## Project Overview

NexCue is a **universal "What's Next?" decision engine** that aggregates saved content from across platforms (YouTube, Netflix, Instagram, Pocket, podcasts, books, recipes, wishlists) and answers one question: **"What should I do next?"**

## Goals

| Category | Goals |
|----------|-------|
| **Learning** | Next.js 14, Supabase, PWA, Share Extensions |
| **Portfolio** | Published app, Product Hunt launch, real users |
| **Business** | 18K users Year 1, Rs.30L+ revenue, sustainable passive income |

---

# Technology Stack

## Core Stack

| Layer | Technology | Why |
|-------|------------|-----|
| **Frontend** | Next.js 14 + React 18 | SSR, app router, server components |
| **State** | React Query + Zustand | Server state + simple client state |
| **Backend** | Supabase | Postgres + Auth + Realtime + Edge Functions |
| **Hosting** | Vercel | Free tier, instant deploys, edge network |
| **PWA** | next-pwa | Installable on mobile |

### Key Packages

| Package | Purpose |
|---------|---------|
| `next` | React framework |
| `@supabase/supabase-js` | Database & auth client |
| `@tanstack/react-query` | Server state management |
| `zustand` | Simple client state |
| `framer-motion` | Animations |
| `lucide-react` | Icons |
| `date-fns` | Date utilities |
| `recharts` | Charts for insights |
| `next-pwa` | PWA capabilities |
| `cheerio` | URL metadata extraction |
| `open-graph-scraper` | Rich link previews |

### Third-Party Services (Free Tier)

| Service | Provider | Free Limit |
|---------|----------|------------|
| Hosting | Vercel | 100GB bandwidth |
| Database | Supabase | 500MB, 50K MAU |
| Analytics | PostHog | 1M events/mo |
| Errors | Sentry | 5K errors/mo |
| Emails | Resend | 100/day |
| Movie Metadata | TMDB API | Free |
| Link Previews | Open Graph | Free |

---

# Platform Integration Strategy (CRITICAL)

## The Reality of Platform APIs

**User permission ≠ data access. APIs decide, not users.**

### Platform Availability Matrix

| Platform | Saved Items via API? | User Permission? | Safe for Public App? |
|----------|---------------------|------------------|---------------------|
| **YouTube** | ✅ Yes | ✅ Yes | ✅ Yes |
| **Notion** | ✅ Yes | ✅ Yes | ✅ Yes |
| **Pocket** | ✅ Yes | ✅ Yes | ✅ Yes |
| **Instagram** | ❌ No | ❌ No | ❌ No |
| **TikTok** | ❌ No | ❌ No | ❌ No |
| **X (Twitter)** | ❌ No | ❌ No | ❌ No |
| **Netflix/Prime** | ❌ No | ❌ No | ❌ No |
| **Google Keep** | ❌ No | ❌ No | ❌ No |
| **Apple Notes** | ❌ No | ❌ No | ❌ No |

### What This Means

```
+====================================================================================+
|                    THE CORRECT PRODUCT STRATEGY                                    |
+====================================================================================+
|                                                                                    |
|  ❌ WRONG APPROACH:                                                                 |
|  "My app reads your saved content"                                                  |
|  - Scraping = ToS violation                                                         |
|  - Background access = not possible                                                 |
|  - Password-based = security risk                                                   |
|                                                                                    |
|  ✅ CORRECT APPROACH:                                                               |
|  "You choose to send something to my app"                                           |
|  - No scraping                                                                      |
|  - No ToS violations                                                                |
|  - Fully user-controlled                                                            |
|  - Scalable to a business                                                           |
|                                                                                    |
+====================================================================================+
```

## Integration Phases

### Phase 1: MVP (Manual + URL Paste)
- Manual item entry
- URL paste with auto-metadata extraction
- No platform dependencies

### Phase 2: Share-Based Import (The Key Strategy)
- **Native Share Sheet** (iOS/Android)
- User shares from ANY app → NexCue receives
- Extract: URL, platform identifier, Open Graph data
- This is **explicit user intent** = platforms allow this

### Phase 3: Official API Integrations (Only Safe Ones)
- YouTube Watch Later (official API)
- Notion databases (official API)
- Pocket saved articles (official API)
- **Never:** Instagram, TikTok, Netflix, X

## Share-Based Import Flow

```
USER FLOW:
1. User sees post/video on Instagram/YouTube/Netflix
2. Taps Share → Selects "NexCue" 
3. NexCue receives:
   - Post URL (always)
   - Platform identifier
   - Sometimes: title, thumbnail
4. NexCue extracts:
   - Open Graph metadata
   - Duration (if video)
   - TMDB data (if movie/show)
5. Saves as Learning Item

WHAT THIS GETS YOU:
✅ Instagram reels/posts
✅ TikTok videos  
✅ X/Twitter threads
✅ Netflix shows/movies
✅ YouTube videos
✅ Any sharable content
```

## Metadata Resolution Strategy

### For Social Media URLs
1. Extract URL from share
2. Fetch Open Graph tags (title, image, description)
3. Parse platform-specific patterns

### For OTT/Movie Content
1. User shares Netflix/Prime link
2. Extract title from URL
3. Query TMDB/OMDb API for:
   - Poster image
   - Genre
   - Duration
   - Type (movie/series)

**Your system never touches OTT internals.**

---

# System Architecture

## High-Level View

```
USERS (Web + PWA + Share Extension)
      |
      v
NEXT.JS (Vercel Edge)
[Pages] [API Routes] [Server Actions]
      |
      v
SUPABASE (Backend)
[Auth] [PostgreSQL] [Storage] [Realtime]
      |
      v
EXTERNAL APIs
[Open Graph] [TMDB] [YouTube API] [Notion API] [Pocket API]
```

## Database Schema

### Core Tables

**profiles** - User data
- id, email, name, avatar, preferences, stats

**categories** - Content categories
- id, user_id, name, icon, color, is_default

**items** - Saved content
- id, user_id, category_id, title, url, thumbnail
- time_estimate (quick/medium/long)
- priority, mood_tags, status, notes
- source_platform, metadata (JSON)
- created_at, completed_at

**completions** - Daily tracking
- id, user_id, date, items_completed, categories (JSON)

## Project Structure

```
nexcue/
├── app/
│   ├── (auth)/login, signup, forgot-password
│   ├── (main)/
│   │   ├── inbox/page.tsx        # All items view
│   │   ├── decide/page.tsx       # Decision engine
│   │   ├── history/page.tsx      # Completed items
│   │   ├── insights/page.tsx     # Stats & streaks
│   │   └── settings/page.tsx     # Preferences
│   ├── api/
│   │   ├── items/route.ts
│   │   ├── suggest/route.ts      # Smart suggestions
│   │   ├── metadata/route.ts     # URL extraction
│   │   └── share/route.ts        # Share sheet handler
│   └── layout.tsx
├── components/
│   ├── ui/                       # Base components
│   ├── items/                    # Item cards, forms
│   ├── decide/                   # Decision flow UI
│   └── layout/                   # Nav, headers
├── lib/
│   ├── supabase/                 # DB client & hooks
│   ├── metadata/                 # URL parsing, Open Graph
│   ├── utils/                    # Helpers
│   ├── hooks/                    # Custom hooks
│   └── types/                    # TypeScript types
└── public/
    ├── icons/                    # PWA icons
    └── manifest.json
```

---

# 16-Week Development Timeline

## Phase Overview

| Phase | Weeks | Dates | Deliverable |
|-------|-------|-------|-------------|
| **Foundation** | 1-3 | Feb 1-21 | Auth, Design System, Categories |
| **Core MVP** | 4-8 | Feb 22 - Mar 28 | Inbox, Decide Engine |
| **Polish** | 9-11 | Mar 29 - Apr 18 | History, Insights, Settings |
| **Launch** | 12-16 | Apr 19 - May 22 | PWA, Beta, Product Hunt |

---

## PHASE 1: Foundation (Weeks 1-3)

### Week 1: Setup (Feb 1-7)

| Task | Owner |
|------|-------|
| [ ] Next.js 14 project setup | Dev |
| [ ] Supabase project & schema | Backend |
| [ ] Figma design system | Designer |
| [ ] GitHub + CI/CD (Vercel) | Dev |
| [ ] Security review plan | Security |

### Week 2: Base Components (Feb 8-14)

- [ ] Design tokens (colors, spacing, typography)
- [ ] Core UI components (Button, Card, Input, Modal)
- [ ] Layout components (Header, BottomNav)
- [ ] Category icons and colors
- [ ] Dark mode support

### Week 3: Auth & Categories (Feb 15-21)

- [ ] Supabase Auth (Email + Google + Apple)
- [ ] Protected routes middleware
- [ ] User profile creation
- [ ] Default categories setup
- [ ] Custom category creation
- [ ] Onboarding flow

> **DELIVERABLE:** Working auth, design system, category system

---

## PHASE 2: Core MVP (Weeks 4-8)

### Week 4: Data Layer (Feb 22-28)

- [ ] Database schema finalized
- [ ] Row Level Security policies
- [ ] CRUD hooks for items
- [ ] TypeScript types
- [ ] Error handling patterns

### Week 5: Add Items (Mar 1-7)

- [ ] Add item modal/form
- [ ] Category picker
- [ ] Time estimate selector (Quick/Medium/Long)
- [ ] Priority picker
- [ ] Mood tags (optional)
- [ ] **URL paste with metadata extraction**
- [ ] Open Graph fetching
- [ ] Platform detection (YouTube, Netflix, Instagram, etc.)
- [ ] Save to database

### Week 6: Inbox View (Mar 8-14)

- [ ] Items list view (cards)
- [ ] Filter by category
- [ ] Filter by status
- [ ] Sort options (priority, date, time)
- [ ] Item card with actions
- [ ] Edit item
- [ ] Delete/Archive item

> **DELIVERABLE:** Complete Inbox with add/edit/view/delete

### Week 7: Decide Engine Core (Mar 15-21)

- [ ] Time selection UI (15/30/45/60+ min)
- [ ] Category filter (optional)
- [ ] Mood filter (optional)
- [ ] Suggestion algorithm implementation
- [ ] Single suggestion card UI
- [ ] "Start" action (opens URL/marks in-progress)
- [ ] "Skip" action
- [ ] "Show Another" action

### Week 8: Decide Polish (Mar 22-28)

- [ ] "Surprise Me" mode
- [ ] Algorithm tuning
- [ ] Completion animation
- [ ] Mark complete flow
- [ ] Quick notes on completion
- [ ] Edge cases handling

> **DELIVERABLE:** Working Decide Engine - core loop complete

---

## PHASE 3: Polish (Weeks 9-11)

### Week 9: History (Mar 29 - Apr 4)

- [ ] History list view
- [ ] Timeline display
- [ ] Filter by category
- [ ] Filter by date range
- [ ] Search completed items
- [ ] Completion details view

### Week 10: Insights (Apr 5-11)

- [ ] Weekly summary card
- [ ] Completion streak tracker
- [ ] Calendar heatmap
- [ ] Category breakdown chart
- [ ] Queue size over time
- [ ] "Time saved" calculation

### Week 11: Settings & Polish (Apr 12-18)

- [ ] Settings page (theme, notifications, defaults)
- [ ] Profile editing
- [ ] Data export (JSON)
- [ ] Loading states everywhere
- [ ] Empty states
- [ ] Error states
- [ ] Micro-animations
- [ ] Performance audit

> **DELIVERABLE:** All features complete, polished UI

---

## PHASE 4: Launch (Weeks 12-16)

### Week 12: PWA (Apr 19-25)

- [ ] Configure next-pwa
- [ ] manifest.json
- [ ] All icon sizes (iOS + Android)
- [ ] Service worker
- [ ] Offline basic support
- [ ] Install prompt

### Week 13: Testing (Apr 26 - May 2)

- [ ] Full manual QA
- [ ] Cross-browser testing
- [ ] Mobile device testing
- [ ] Performance optimization
- [ ] Lighthouse audit (target 90+)
- [ ] Security audit

### Week 14: Landing Page (May 3-9)

- [ ] Design landing page
- [ ] Build with Next.js
- [ ] SEO optimization
- [ ] Open Graph images
- [ ] Demo video/GIF
- [ ] Testimonials section (beta users)

### Week 15: Beta (May 10-16)

- [ ] Invite 30-50 beta users
- [ ] Feedback collection (Typeform)
- [ ] Bug fixes
- [ ] Quick wins implementation
- [ ] Product Hunt prep
- [ ] Social media assets

### Week 16: Launch (May 17-22)

- [ ] Final QA
- [ ] Product Hunt launch
- [ ] Twitter/X announcement
- [ ] LinkedIn post
- [ ] Indie Hackers post
- [ ] Monitor feedback
- [ ] Celebrate! 🎉

> **MILESTONE:** PUBLIC LAUNCH - May 22, 2026

---

# Post-Launch Roadmap (Complete 3-Year Plan)

## Timeline Overview

| Year | Focus | Key Milestones |
|------|-------|----------------|
| **Year 1** | MVP + Extensions | Launch, Share Extension, Browser Extension |
| **Year 2** | Intelligence + Integrations | Smart suggestions, YouTube/Notion sync, Widgets |
| **Year 3** | AI + Platform Expansion | AI features, Native apps, Enterprise |

---

# Development Bifurcation by App/Component

## 🌐 WEB APP (Next.js PWA)

### Phase 1: MVP (Weeks 1-16) ✓ CURRENT

| Feature | Status | Timeline |
|---------|--------|----------|
| Authentication | 🔲 TODO | Week 3 |
| Categories system | 🔲 TODO | Week 3 |
| Add item (manual) | 🔲 TODO | Week 5 |
| URL paste + metadata | 🔲 TODO | Week 5 |
| Inbox view | 🔲 TODO | Week 6 |
| **Decide Engine** | 🔲 TODO | Week 7-8 |
| History view | 🔲 TODO | Week 9 |
| Basic insights | 🔲 TODO | Week 10 |
| Settings | 🔲 TODO | Week 11 |
| PWA setup | 🔲 TODO | Week 12 |
| Landing page | 🔲 TODO | Week 14 |

### Phase 2: Enhanced Web (Months 5-7)

| Feature | Priority | Details |
|---------|----------|---------|
| Bulk URL import | High | Paste 10+ URLs at once |
| CSV/JSON import | High | Import from other apps |
| Data export | Medium | Backup user data |
| Item expiration | Medium | Auto-archive old items |
| Advanced filters | Medium | Multi-select, date range |

### Phase 3: Intelligence (Months 8-10)

| Feature | Priority | Details |
|---------|----------|---------|
| Calendar heatmap | High | GitHub-style completions |
| Time-of-day patterns | Medium | Morning/evening insights |
| Weekly email digest | Medium | Completion summary |
| Smart suggestions v2 | High | Learn from patterns |

---

## 📱 MOBILE EXTENSIONS

### iOS Share Extension (Month 5-6)

| Task | Complexity | Details |
|------|------------|---------|
| Share Extension target setup | Medium | Xcode project |
| Quick category picker UI | Low | SwiftUI |
| API sync with web app | Medium | Supabase client |
| TMDB lookup for movies | Low | API call |
| Success animation | Low | Haptic + visual |
| Deep link to main app | Low | URL scheme |

**Tech Stack:** Swift, SwiftUI, Supabase Swift SDK

### Android Share Extension (Month 5-6)

| Task | Complexity | Details |
|------|------------|---------|
| Intent Filter setup | Medium | AndroidManifest |
| Share receiver activity | Medium | Kotlin |
| Category picker UI | Low | Jetpack Compose |
| API sync | Medium | Supabase Kotlin |
| Success feedback | Low | Toast + animation |

**Tech Stack:** Kotlin, Jetpack Compose

### iOS Widget (Month 8-9)

| Widget Type | Size | Functionality |
|-------------|------|---------------|
| Quick Suggestion | Small | Shows next suggested item |
| Queue Size | Small | Shows count by category |
| Decide Now | Medium | One-tap to open Decide |
| Today's Progress | Medium | Completions today |

**Tech Stack:** WidgetKit, SwiftUI

### Android Widget (Month 8-9)

| Widget Type | Functionality |
|-------------|---------------|
| Quick Suggestion | Shows next item |
| Decide Button | Opens Decide flow |
| Stats | Completions + streak |

**Tech Stack:** Glance API (Jetpack)

---

## 🔌 BROWSER EXTENSIONS

### Chrome Extension (Month 6-7)

| Feature | Priority | Details |
|---------|----------|---------|
| Popup UI | High | Quick add form |
| One-click save | High | Badge on toolbar |
| Right-click menu | High | "Add to NexCue" |
| Auto-detect page | Medium | Suggest category |
| Keyboard shortcut | Low | Cmd+Shift+N |
| Sync with web app | High | Supabase client |

**Tech Stack:** Manifest V3, React, TypeScript

### Safari Extension (Month 7)

| Feature | Priority | Details |
|---------|----------|---------|
| Safari web extension | High | Based on Chrome ext |
| Mac native feel | Medium | Proper styling |
| iOS Safari support | Low | If time permits |

**Tech Stack:** Safari Web Extension API

### Firefox Extension (Month 8)

| Feature | Priority | Details |
|---------|----------|---------|
| Port from Chrome | Medium | Minor API differences |
| Firefox styling | Low | Match browser |

---

## 🔗 API INTEGRATIONS

### YouTube API (Month 9-10)

| Feature | Complexity | Details |
|---------|------------|---------|
| OAuth2 authentication | Medium | Google Cloud Console |
| Watch Later playlist access | Medium | YouTube Data API v3 |
| Video metadata fetch | Low | Duration, title, thumbnail |
| One-time import | High | Bulk import existing items |
| Periodic sync (optional) | Medium | Daily/weekly refresh |
| Two-way complete | High | Mark watched in YouTube |

**API:** YouTube Data API v3

### Notion API (Month 10-11)

| Feature | Complexity | Details |
|---------|------------|---------|
| OAuth2 integration | Medium | Notion integrations |
| Database selection | Medium | User picks which DB |
| Import database items | Medium | Map to NexCue items |
| Custom field mapping | High | Category, priority, etc. |
| Two-way sync | High | Update Notion on complete |

**API:** Notion API (REST)

### Pocket API (Month 11-12)

| Feature | Complexity | Details |
|---------|------------|---------|
| OAuth integration | Medium | Pocket auth flow |
| Retrieve saved articles | Low | Simple API |
| Import with tags | Medium | Map tags to categories |
| Archive on complete | Medium | Two-way sync |

**API:** Pocket API v3

### TMDB API (Already in MVP)

| Feature | Status | Details |
|---------|--------|---------|
| Movie/show lookup | ✅ Ready | TMDB free API |
| Poster images | ✅ Ready | Image CDN |
| Runtime/duration | ✅ Ready | For time estimate |

---

## 🤖 AI FEATURES (Year 2-3)

### AI Categorization (Month 14-15)

| Feature | Implementation | Cost |
|---------|----------------|------|
| Auto-detect category from URL | OpenAI API | ~$0.01/item |
| Auto-estimate time | Content length analysis | Free |
| Mood tag suggestion | GPT-3.5 | ~$0.001/item |

### Voice Features (Month 16-18)

| Feature | Implementation | Details |
|---------|----------------|---------|
| Siri Shortcuts integration | iOS only | Add via voice |
| Voice note attachments | Web Speech API | Chrome/Safari |
| "What should I watch?" | OpenAI Whisper | Voice command |

### Predictive Intelligence (Month 18-20)

| Feature | Implementation | Details |
|---------|----------------|---------|
| Skip prediction | Local ML model | Based on history |
| Best time to suggest | Pattern analysis | Time-of-day |
| Smart archive | Threshold rules | Items sitting too long |

### AI Summary (Premium) (Month 20-24)

| Feature | Implementation | Cost |
|---------|----------------|------|
| Article summary | GPT-4 | ~$0.05/article |
| YouTube key points | Transcript + GPT | ~$0.03/video |
| "Why you saved this" | Context memory | ~$0.01/query |

---

## 📱 NATIVE APPS (Year 3 - If Needed)

### React Native App (Month 24-30)

| Component | Priority | Reason |
|-----------|----------|--------|
| Core navigation | High | Tab bar UX |
| Decide flow | High | Main interaction |
| Offline support | Medium | Sync queue |
| Push notifications | Medium | Smart reminders |
| Background sync | Low | Keep data fresh |

**Only build if:** PWA performance is insufficient or App Store presence critical

### Desktop App (Month 30-36)

| Platform | Implementation | Priority |
|----------|----------------|----------|
| macOS | Tauri (Rust) or Electron | Low |
| Windows | Tauri | Low |

**Only build if:** Strong user demand

---

## 🏢 ENTERPRISE FEATURES (Year 3)

| Feature | Priority | Details |
|---------|----------|---------|
| Team workspaces | Medium | Shared queues |
| Admin dashboard | Low | User management |
| SSO (SAML) | Low | Enterprise login |
| Audit logs | Low | Compliance |
| Custom branding | Low | White-label |

---

# Technical Feasibility Assessment

## Is This Doable?

| Component | Complexity | Confidence | Notes |
|-----------|------------|------------|-------|
| **Web MVP** | Low-Medium | ✅ 100% | Standard CRUD + algorithm |
| **PWA** | Low | ✅ 100% | next-pwa handles it |
| **Share Extension (iOS)** | Medium | ✅ 95% | Well-documented |
| **Share Extension (Android)** | Medium | ✅ 95% | Standard pattern |
| **Browser Extension** | Low | ✅ 100% | Manifest V3 is stable |
| **YouTube API** | Medium | ✅ 90% | Official, documented |
| **Notion API** | Medium | ✅ 90% | Good documentation |
| **Widgets** | Medium | ✅ 85% | SwiftUI/Glance |
| **AI features** | Medium | ✅ 85% | OpenAI API is easy |
| **Native apps** | High | ✅ 80% | React Native is proven |

**Overall Assessment:** **100% DOABLE**

No technical moonshots required. All components use established technologies and documented APIs.

---

# Never Do (ToS Violations)

| Action | Platform | Reason |
|--------|----------|--------|
| ❌ Scraping | Instagram | No API for saved posts |
| ❌ Scraping | Netflix/Prime | No public APIs |
| ❌ Scraping | TikTok | No API for favorites |
| ❌ Scraping | Twitter bookmarks | API doesn't expose |
| ❌ Password-based access | Any | Security risk |
| ❌ Browser automation | Any | Fragile, ToS violation |
| ❌ Fake "user permission" flows | Any | Deceptive |

---

# Development Rules

## Daily Rules (From MVP Checklist)

- ☐ One small task per session only
- ☐ 30–45 minutes maximum
- ☐ Skipping a day is allowed (no guilt)
- ☐ No feature expansion before February
- ☐ This system must feel lighter than social media

## Core Philosophy

> **"You are not building a productivity tool. You are building a system that helps you START without thinking."**

> **"Finish small. Trust clarity. Earn complexity."**

---

# Milestone Summary

| Milestone | Date | Deliverable |
|-----------|------|-------------|
| **MVP Launch** | May 22, 2026 | Web app + PWA |
| **Share Extension** | July 2026 | iOS + Android |
| **Browser Extension** | August 2026 | Chrome + Safari |
| **Widgets** | October 2026 | iOS + Android |
| **YouTube Integration** | December 2026 | Official API sync |
| **AI Features v1** | March 2027 | Auto-categorization |
| **Native Apps** | December 2027 | If needed |
| **Enterprise** | 2028 | Team features |

---

*End of Development Plan*
