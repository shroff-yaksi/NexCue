# NexCue - Product Specification

> **App Name:** NexCue  
> **Tagline:** Your Universal "What's Next?" Engine  
> **Version:** 1.0  
> **Last Updated:** January 27, 2026  
> **Team:** 4 Members  
> **Market:** Global (English-first, India priority)

---

## Executive Summary

NexCue is a **universal content queue and decision engine** that solves the modern problem of content hoarding across platforms. Whether it's saved Instagram posts, YouTube Watch Later, bookmarked articles, wishlisted products, saved recipes, or podcast queues - NexCue brings everything into one place and answers the simple question: **"What should I do next?"**

The core philosophy: **Decide less. Do more.**

---

## The Problem We Solve

### The Content Hoarding Epidemic

| Platform | What Users Save | Typical Count | % Ever Revisited |
|----------|-----------------|---------------|------------------|
| Instagram | Posts, Reels, Recipes | 200-500 | 5% |
| YouTube | Watch Later videos | 100-300 | 10% |
| Netflix | My List shows/movies | 50-150 | 20% |
| Browser | Bookmarks | 500-2000 | 2% |
| Spotify | Saved songs, playlists | 1000+ | 30% |
| Amazon | Wishlist items | 50-200 | 15% |
| Notes App | Random screenshots, ideas | 50-200 | 15% |
| Pocket/Instapaper | Articles to read | 100-500 | 20% |
| Pinterest | Pins (recipes, ideas) | 200-1000 | 10% |
| Twitter/X | Bookmarks | 100-500 | 5% |

**Result:** Thousands of "saved for later" items that create guilt and decision paralysis.

---

## Product Vision

```
+====================================================================================+
|                        NexCue - Your "What's Next?" Engine                         |
+====================================================================================+
|                                                                                    |
|  "I have 30 minutes... what should I do?"                                          |
|                                                                                    |
|  +--------------+  +--------------+  +--------------+  +--------------+            |
|  |    WATCH     |  |    READ      |  |    LISTEN    |  |    LEARN     |            |
|  +--------------+  +--------------+  +--------------+  +--------------+            |
|  | YouTube      |  | Articles     |  | Podcasts     |  | Courses      |            |
|  | Netflix      |  | Books        |  | Audiobooks   |  | Tutorials    |            |
|  | Movies       |  | Newsletters  |  | Music        |  | Workshops    |            |
|  | Saved Reels  |  | Threads      |  | Playlists    |  | Guides       |            |
|  +--------------+  +--------------+  +--------------+  +--------------+            |
|                                                                                    |
|  +--------------+  +--------------+  +--------------+  +--------------+            |
|  |    COOK      |  |     DO       |  |     BUY      |  |    OTHER     |            |
|  +--------------+  +--------------+  +--------------+  +--------------+            |
|  | Recipes      |  | Side Projects|  | Wishlist     |  | Custom       |            |
|  | Meal Ideas   |  | DIY Projects |  | Shopping     |  | Categories   |            |
|  | Restaurants  |  | Home Tasks   |  | Gift Ideas   |  | Anything     |            |
|  +--------------+  +--------------+  +--------------+  +--------------+            |
|                                                                                    |
|                               |                                                    |
|                               v                                                    |
|                  +-------------------------+                                       |
|                  |    SMART DECISION       |                                       |
|                  |    ENGINE               |                                       |
|                  |  Time + Mood + Context  |                                       |
|                  |  = Perfect Suggestion   |                                       |
|                  +-------------------------+                                       |
|                                                                                    |
+====================================================================================+
```

---

## Target Audience

| Segment | Description | Primary Pain |
|---------|-------------|--------------|
| Content Hoarders | 500+ saved items across apps | "So much saved, never opened" |
| Netflix Scrollers | Spend 20 mins deciding what to watch | Decision paralysis |
| Podcast Collectors | 50+ episodes in queue | "Where do I even start?" |
| Recipe Savers | Hundreds of saved recipes | Never cook any of them |
| Wishlist Sitters | Items saved for months | Can't prioritize purchases |
| Tab Collectors | 30+ browser tabs open "to read later" | Information overload |
| Course Hoarders | Multiple unfinished courses | Learning guilt |

---

# Core Features

## Section 1: Universal Inbox

### 1.1 Content Categories (Built-in)

| Category | Icon | Examples |
|----------|------|----------|
| **Watch** | 📺 | YouTube, Netflix, movies, TV shows, documentaries, reels |
| **Read** | 📚 | Articles, books, newsletters, blog posts, threads |
| **Listen** | 🎧 | Podcasts, audiobooks, albums, playlists |
| **Learn** | 🎓 | Courses, tutorials, workshops, skill content |
| **Cook** | 🍳 | Recipes, meal ideas, restaurants to try |
| **Do** | ⚡ | Projects, DIY, tasks, side hustles |
| **Buy** | 🛒 | Wishlist items, shopping ideas, gifts |
| **Visit** | 📍 | Places, travel, local spots |
| **Custom** | ✨ | User-created categories |

### 1.2 Adding Items

| Method | Description |
|--------|-------------|
| **Manual Add** | Title + Category + Time Estimate |
| **URL Paste** | Auto-detect title, thumbnail, duration |
| **Share Extension** | Add from ANY app via share sheet |
| **Browser Extension** | One-click save from Chrome/Safari |
| **Voice Add** | "Add this recipe, 30 minutes to make" |
| **Screenshot** | Photo of content to save |
| **Bulk Import** | CSV, JSON, or app-specific imports |

### 1.3 Item Properties

| Property | Description |
|----------|-------------|
| **Title** | What is this item? |
| **Category** | Watch / Read / Listen / Learn / Cook / Do / Buy / Custom |
| **Time Estimate** | Quick (≤15 min) / Medium (20-45 min) / Long (1+ hr) |
| **Priority** | Low / Normal / High / Urgent |
| **Mood Tags** | Relaxing / Energizing / Focused / Fun / Productive |
| **Source** | Original URL or app |
| **Notes** | Why you saved it, context |
| **Thumbnail** | Visual preview |
| **Status** | New / In Progress / Completed / Skipped / Archived |

### 1.4 Smart Metadata Extraction

When you paste a URL, NexCue auto-extracts:

| Source | Extracted Data |
|--------|----------------|
| YouTube | Title, thumbnail, duration, channel |
| Netflix | Show/movie name, genre, runtime |
| Spotify | Podcast episode, duration, show name |
| Articles | Title, reading time, site name |
| Amazon | Product name, price, image |
| Recipes | Dish name, cook time, image |

---

## Section 2: The Decide Engine (Core Feature)

The heart of NexCue - eliminates decision fatigue.

### 2.1 Decision Flow

```
+====================================================================================+
|                           THE DECIDE FLOW                                          |
+====================================================================================+
|                                                                                    |
|  STEP 1: "How much time do you have?"                                              |
|  ---------------------------------------------------------------------------       |
|  [15 min] [30 min] [45 min] [1 hr] [1.5 hr] [2+ hr] [Surprise me]                  |
|                                                                                    |
|  STEP 2: "What are you in the mood for?" (Optional)                                |
|  ---------------------------------------------------------------------------       |
|  [📺 Watch] [📚 Read] [🎧 Listen] [🎓 Learn] [🍳 Cook] [⚡ Do] [Any]               |
|                                                                                    |
|  STEP 3: "How are you feeling?" (Optional)                                         |
|  ---------------------------------------------------------------------------       |
|  [😌 Relaxed] [⚡ Energized] [🎯 Focused] [🎉 Fun/Light] [Skip]                    |
|                                                                                    |
|  RESULT: Perfect Suggestion                                                        |
|  ---------------------------------------------------------------------------       |
|                                                                                    |
|  ╔══════════════════════════════════════════════════════════════╗                 |
|  ║  📺 WATCH THIS                                                ║                 |
|  ║                                                               ║                 |
|  ║  "How to Build a Second Brain"                                ║                 |
|  ║  YouTube • 45 min • Productivity                              ║                 |
|  ║                                                               ║                 |
|  ║  Saved 3 weeks ago • Matches your focused mood                ║                 |
|  ╚══════════════════════════════════════════════════════════════╝                 |
|                                                                                    |
|  [▶ Start Now]  [Skip Today]  [Show Another]  [Not Interested]                    |
|                                                                                    |
+====================================================================================+
```

### 2.2 Smart Selection Algorithm

| Factor | Weight | Description |
|--------|--------|-------------|
| **Time Match** | 35% | Fits available time |
| **Category Match** | 20% | Matches mood/preference |
| **Priority** | 15% | Higher priority items first |
| **Age** | 15% | Older items get slight boost (prevent rot) |
| **Mood Match** | 10% | Relaxing vs focused content |
| **Completion History** | 5% | What you typically finish |

### 2.3 "Surprise Me" Mode

When you don't want to decide anything:
- Random selection from queue
- Weighted by priority and age
- One-tap start
- Skip freely, no guilt

### 2.4 Contextual Suggestions

| Context | Suggestion Type |
|---------|-----------------|
| Morning commute | Listen (podcasts, audiobooks) |
| Lunch break | Watch (short videos), Read (articles) |
| Evening wind-down | Watch (relaxing), Cook (dinner recipe) |
| Weekend afternoon | Learn (courses), Do (projects) |

---

## Section 3: Platform Integration Strategy

### 3.1 The Reality of Platform APIs

**User permission ≠ data access. APIs decide, not users.**

| Platform | Can Access Saved Items? | Integration Method |
|----------|------------------------|--------------------|
| **YouTube** | ✅ Yes (official API) | Direct sync (Phase 2+) |
| **Notion** | ✅ Yes (official API) | Direct sync (Phase 2+) |
| **Pocket** | ✅ Yes (official API) | Direct sync (Phase 2+) |
| **Instagram** | ❌ No API | Share-based import |
| **TikTok** | ❌ No API | Share-based import |
| **Netflix/Prime** | ❌ No API | Share-based import |
| **X/Twitter** | ❌ Bookmarks blocked | Share-based import |
| **Pinterest** | ❌ Limited | Share-based import |
| **Spotify** | ❌ Podcast queue blocked | Share-based import |

### 3.2 Share-Based Import (The Correct Approach)

**How it works:**
1. User sees a reel/post/show on any platform
2. Taps Share → Selects "NexCue"
3. NexCue receives the URL
4. Auto-extracts metadata (Open Graph, TMDB for movies)
5. Saves as item in queue

**This enables:**
- ✅ Instagram reels/posts (via share)
- ✅ TikTok videos (via share)
- ✅ Netflix shows (via share + TMDB lookup)
- ✅ Twitter threads (via share)
- ✅ Any platform with a Share button

**Honest limitation:**
- Cannot auto-import OLD saved collections
- Only works for NEW items going forward
- This is acceptable and actually better (intentional items only)

### 3.3 Import Methods by Phase

| Method | Availability |
|--------|--------------|
| **Manual Entry** | Phase 1 (MVP) |
| **URL Paste + Auto-Metadata** | Phase 1 |
| **Share Extension (iOS/Android)** | Phase 2 |
| **Browser Extension** | Phase 2 |
| **YouTube API Sync** | Phase 3 (official only) |
| **Notion API Sync** | Phase 3 (official only) |
| **Pocket API Sync** | Phase 3 (official only) |

---

## Section 4: History & Progress

### 4.1 Completion Tracking

| View | Description |
|------|-------------|
| **Timeline** | Chronological list of completed items |
| **Calendar** | Heat map (like GitHub contributions) |
| **By Category** | Watch / Read / Listen breakdown |
| **By Source** | Which platforms you consume most |

### 4.2 Stats Dashboard

| Stat | Description |
|------|-------------|
| Items Completed | Total all-time |
| Current Streak | Days in a row with completions |
| Queue Size | Items waiting |
| Completion Rate | Done vs Added |
| Average per Week | Consumption pace |
| Time Saved (Decision) | Estimated decision time saved |

---

## Section 5: Queue Management

### 5.1 Views

| View | Description |
|------|-------------|
| **All Items** | Everything in queue |
| **By Category** | Filter by Watch/Read/etc. |
| **By Priority** | Urgent → Low |
| **By Time** | Quick → Long |
| **By Age** | Oldest → Newest |
| **Smart Groups** | Auto-groupings |

### 5.2 Bulk Actions

- Select multiple items
- Batch change category/priority
- Batch archive or delete
- Move to different category
- Add shared tags

### 5.3 Archive

- Completed items auto-archive
- Manual archive for "not now"
- Searchable history
- Restore to queue anytime

---

## Section 6: Personalization

### 6.1 Preferences

| Setting | Options |
|---------|---------|
| Default category | Any or specific |
| Typical free time | 15/30/45/60+ min |
| Preferred content times | Morning=Listen, Evening=Watch |
| Skip behavior | Show less often / Remove after X skips |
| Notifications | Off / Daily / Smart |

### 6.2 Smart Defaults

NexCue learns your patterns:
- What time you consume content
- What categories you complete most
- How long you typically have
- Your completion patterns

---

# Design Philosophy

## Core Principles

| Principle | Implementation |
|-----------|----------------|
| **One Decision** | You just pick time, we pick content |
| **No Guilt** | Skipping is valid, archives are clean |
| **Instant Value** | Add → Decide → Done in seconds |
| **Quiet by Default** | Minimal notifications |
| **Progress Visible** | See queue shrink, feel accomplishment |
| **Platform Agnostic** | Works with any content, any source |

## Visual Identity

- **Clean & Minimal** - Focus on content, not chrome
- **Category Colors** - Quick visual identification
- **Smooth Animations** - Satisfying completions
- **Dark Mode First** - Easy on eyes during content consumption
- **Mobile-First** - Decide on the go

## Core Philosophy (From the Manifesto)

> **"You are not building a productivity tool. You are building a system that helps you START without thinking."**

> **"Finish small. Trust clarity. Earn complexity."**

The goal is to feel **lighter than social media**, not heavier.

---

# Use Cases

## Use Case 1: Evening TV Decision

**Before NexCue:**
- Open Netflix → Scroll 15 min → Nothing appeals → Switch to YouTube → Same thing → Watch random short videos → Feel unsatisfied

**With NexCue:**
- Open NexCue → "1 hour, Watch, Relaxed" → Get suggestion: "The Bear Season 2" (Netflix) → Start immediately

## Use Case 2: Podcast Overload

**Before:**
- 50+ podcast episodes in queue
- No idea what to listen to on commute
- End up listening to same comfort podcasts

**With NexCue:**
- "30 min, Listen" → Get suggestion from your actual queue → Actually discover saved content

## Use Case 3: Recipe Decision

**Before:**
- 200 saved recipes on Instagram
- End up ordering food because "nothing feels right"

**With NexCue:**
- "45 min, Cook" → Get dinner recipe from your saved posts → Actually cook something

## Use Case 4: Learning Goals

**Before:**
- 5 courses started, none finished
- New courses keep getting added
- Feel guilty about unfinished learning

**With NexCue:**
- "1 hour, Learn, Focused" → Continue your in-progress course → Make actual progress

---

# Success Metrics

## North Star Metric

**Weekly Active Completions (WAC)** - Items marked complete per week

## Supporting Metrics

| Metric | Month 6 Target | Month 12 Target |
|--------|----------------|-----------------|
| Weekly Active Users | 5,000 | 15,000 |
| Completions per User/Week | 7 | 10 |
| Day 7 Retention | 35% | 45% |
| Day 30 Retention | 20% | 30% |
| Queue Size (avg) | 50 items | 75 items |
| Decision Time Saved | 10 min/week | 15 min/week |

---

# Complete Product Roadmap

## Phase Overview (All Phases)

| Phase | Timeline | Focus | Key Deliverables |
|-------|----------|-------|------------------|
| **Phase 1: MVP** | Weeks 1-16 | Core loop | Inbox, Decide, History, Web App |
| **Phase 2: Extensions** | Months 5-7 | Frictionless Add | Share Extension, Browser Extension |
| **Phase 3: Intelligence** | Months 8-10 | Smart Features | Insights, Smart Suggestions, Widgets |
| **Phase 4: Integrations** | Months 11-14 | Official APIs | YouTube, Notion, Pocket sync |
| **Phase 5: Social** | Year 2 | Community | Shared lists, accountability partners |
| **Phase 6: AI** | Year 2-3 | Automation | AI categorization, voice, predictive |

---

## Phase 1: MVP (Weeks 1-16) ✓ CURRENT

### Core Features
- [x] User authentication (Email, Google, Apple)
- [x] Default categories (Watch, Read, Listen, Learn, Cook, Do, Buy)
- [x] Custom categories
- [x] Add items (manual + URL paste)
- [x] URL metadata extraction (Open Graph)
- [x] Inbox view with filters
- [x] **Decide Engine** (time + category + mood selection)
- [x] Suggestion algorithm
- [x] Mark complete / Skip / Archive
- [x] History view
- [x] Basic insights (streak, weekly count)
- [x] Settings & preferences
- [x] PWA (installable)
- [x] Dark mode

### Onboarding Strategy (Cold Start Solution)
- First-time users see "Add your first 5 items" prompt
- Sample items option: "Try with example queue"
- Quick import: Paste 5 URLs at once
- Immediate value: First Decide suggestion after 3 items

---

## Phase 2: Extensions (Months 5-7)

### Share Extension (iOS + Android)
- [ ] iOS Share Extension development
- [ ] Android Intent Filter setup
- [ ] Quick category picker in share sheet
- [ ] Auto-detect platform (Instagram, YouTube, Netflix, etc.)
- [ ] TMDB lookup for movie/show links
- [ ] Success confirmation animation

### Browser Extension (Chrome, Safari, Firefox)
- [ ] One-click save button on all pages
- [ ] Right-click context menu "Add to NexCue"
- [ ] Popup: quick category + time estimate
- [ ] Sync with web app
- [ ] Keyboard shortcut (Cmd+Shift+N)

### Additional Features
- [ ] Bulk URL import (paste 10+ links at once)
- [ ] CSV/JSON import from other apps
- [ ] Export queue data
- [ ] Item expiration settings ("Archive if not touched in 60 days")

---

## Phase 3: Intelligence (Months 8-10)

### Advanced Insights Dashboard
- [ ] Calendar heatmap (GitHub-style completions)
- [ ] Category breakdown charts
- [ ] Time-of-day patterns
- [ ] "Content aging" report (items sitting too long)
- [ ] Weekly email digest
- [ ] Completion velocity trends

### Smart Suggestions V2
- [ ] Learn from completion patterns
- [ ] Time-of-day awareness (morning = Listen, evening = Watch)
- [ ] "You usually skip this type" detection
- [ ] Seasonal/mood playlists ("Rainy day reads")
- [ ] "Continue where you left off" for in-progress items

### Mobile Widgets
- [ ] iOS Widget: "Your next suggestion" (one-tap)
- [ ] iOS Widget: "Queue size" minimal
- [ ] Android Widget: Same as iOS
- [ ] Apple Watch complication (optional)

### Notifications
- [ ] Daily nudge (configurable time)
- [ ] "You haven't opened NexCue in 7 days" win-back
- [ ] Weekly summary notification
- [ ] Smart notifications (only when queue growing)

---

## Phase 4: Integrations (Months 11-14)

### Official API Integrations (Only Safe Ones)

| Platform | Integration Type | Priority |
|----------|-----------------|----------|
| **YouTube** | Watch Later sync | High |
| **Notion** | Database import | High |
| **Pocket** | Saved articles sync | High |
| **Spotify** | Podcast episodes (if API allows) | Medium |
| **Kindle/Goodreads** | Want to Read | Medium |
| **Todoist** | Import as "Do" items | Low |

### How Integrations Work
- One-time authorization (OAuth)
- Initial import of existing saved items
- Optional: Periodic sync (daily/weekly)
- Two-way: Mark complete in NexCue → complete in source app

### Third-Party Metadata APIs
- [ ] TMDB for movies/shows (already in MVP)
- [ ] Open Library for books
- [ ] Podcast Index for episodes
- [ ] Product Hunt API for tech products

---

## Phase 5: Social Features (Year 2)

### Shared Lists
- [ ] Create collaborative queues
- [ ] Share via link (read-only or editable)
- [ ] "Recommend to friend" action
- [ ] Family queue (watch together list)

### Accountability Partner
- [ ] Connect with a friend
- [ ] See each other's completion streaks
- [ ] Gentle nudges ("Alex completed 5 items today!")
- [ ] Weekly comparison (optional, non-competitive)

### Community Features (Optional)
- [ ] Public queues (curated lists)
- [ ] "Popular this week" from community
- [ ] Follow other users' queues
- [ ] Comments on items

---

## Phase 6: AI Features (Year 2-3)

### AI Categorization
- [ ] Auto-detect category from URL
- [ ] Auto-estimate time from content
- [ ] Auto-tag mood (relaxing, focused, fun)
- [ ] Smart title extraction

### Voice Integration
- [ ] "Hey Siri, add this to NexCue"
- [ ] Voice command: "What should I watch?"
- [ ] Voice notes attached to items

### Predictive Intelligence
- [ ] "You'll probably skip this" warning
- [ ] "Best time to suggest this" scheduling
- [ ] "You haven't touched Learn in 2 weeks" nudge
- [ ] Smart archive suggestions

### AI Summary (Premium)
- [ ] Summarize long articles before deciding
- [ ] Show key takeaways of YouTube videos
- [ ] "Why you saved this" reminder AI

---

## Phase 7: Platform Expansion (Year 3)

### Native Apps (If PWA Insufficient)
- [ ] React Native iOS app
- [ ] React Native Android app
- [ ] Desktop app (Electron or Tauri)

### Enterprise/Team Features
- [ ] Team workspaces
- [ ] Admin dashboard
- [ ] Shared organizational queues
- [ ] SSO integration

### API & Zapier
- [ ] Public API for developers
- [ ] Zapier integration
- [ ] IFTTT recipes
- [ ] Webhooks

---

# Feature Prioritization Matrix

## Must Have (MVP)
| Feature | Reason |
|---------|--------|
| Decide Engine | Core differentiator |
| URL metadata extraction | Reduces friction |
| Categories + filters | Organization |
| History tracking | Sense of progress |

## Should Have (Year 1)
| Feature | Reason |
|---------|--------|
| Share Extension | Biggest UX improvement |
| Browser Extension | Capture from desktop |
| Insights dashboard | Retention driver |
| Widgets | Daily engagement |

## Nice to Have (Year 2+)
| Feature | Reason |
|---------|--------|
| Social features | Growth lever |
| AI features | Premium differentiation |
| Native apps | Performance (if needed) |
| Enterprise | Revenue expansion |

---

# Anti-Patterns (What NOT to Build)

| Feature | Why NOT |
|---------|---------|
| Aggressive notifications | Creates anxiety, defeats purpose |
| Strict streaks with "broken" language | Guilt-inducing |
| Social comparison leaderboards | Toxic competition |
| "You have 247 items waiting!" prominent display | Anxiety-inducing |
| Gamification badges overdone | Becomes a chore |
| Auto-import everything | Defeats intentionality |

**Core principle:** This should feel LIGHTER than the problem, not heavier.

---

# Technical Feasibility Assessment

## Is This Doable?

| Factor | Assessment | Confidence |
|--------|------------|------------|
| **Core MVP** | Standard CRUD + simple algorithm | ✅ 100% |
| **URL metadata extraction** | Open Graph, existing libraries | ✅ 100% |
| **Share Extension** | Well-documented iOS/Android patterns | ✅ 95% |
| **Browser Extension** | Standard Chrome/Safari APIs | ✅ 95% |
| **YouTube API** | Official, documented, free tier | ✅ 90% |
| **AI features** | OpenAI API, clear integration | ✅ 85% |
| **Native apps** | React Native, proven stack | ✅ 90% |

**Overall: This is absolutely doable.** No technical moonshots required.

---

*End of Product Specification*
