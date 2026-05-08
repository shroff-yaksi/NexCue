# 📋 NexCue — Remaining Tasks
> Last updated: February 24, 2026
> Timeline: Feb 1, 2026 → May 22, 2026 (MVP launch)
> Stack: Next.js 14 + Supabase + Vercel

---

## ⚠️ Status: NOT STARTED
> The project exists as documentation only. No Next.js codebase has been initialized yet.

---

## 🔴 Phase 1 — Foundation (Week 1–3, Feb 1–21)

### Week 1 — Setup
- [ ] Initialize Next.js 14 project (`npx create-next-app@latest`)
- [ ] Setup Supabase project + define and run database schema
- [ ] Create GitHub repo + Vercel deployment pipeline
- [ ] Start Figma design system

### Week 2 — Base Components
- [ ] Design tokens (colors, spacing, typography)
- [ ] Core UI components (Button, Card, Input, Modal)
- [ ] Layout components (Header, BottomNav)
- [ ] Dark mode support
- [ ] Category icons and color mapping

### Week 3 — Auth & Categories
- [ ] Supabase Auth (Email + Google + Apple)
- [ ] Protected routes middleware
- [ ] User profile creation on first login
- [ ] Default categories setup (seeded)
- [ ] Custom category creation UI
- [ ] Onboarding flow for new users

---

## 🔴 Phase 2 — Core MVP (Week 4–8, Feb 22 – Mar 28)

### Data Layer
- [ ] Finalize Supabase schema (`profiles`, `categories`, `items`, `completions`)
- [ ] Row Level Security (RLS) policies
- [ ] CRUD React Query hooks for items
- [ ] TypeScript types file

### Add Items
- [ ] Add item form/modal (title, category, time estimate, priority, mood tags)
- [ ] URL paste with Open Graph metadata extraction
- [ ] Platform detection (YouTube → video, Netflix → show, etc.)
- [ ] TMDB API lookup for movie/show content
- [ ] Save to Supabase

### Inbox View
- [ ] Items list with card UI
- [ ] Filter by category / status
- [ ] Sort by priority / date / time estimate
- [ ] Edit item
- [ ] Delete / archive item

### Decide Engine
- [ ] Time selection UI (15 / 30 / 45 / 60+ min)
- [ ] Category + mood filter
- [ ] Suggestion algorithm (priority + mood + time matching)
- [ ] Single suggestion card UI
- [ ] Actions: Start / Skip / Show Another
- [ ] "Surprise Me" mode
- [ ] Completion animation + mark complete flow
- [ ] Quick notes on completion

---

## 🔴 Phase 3 — Polish (Week 9–11, Mar 29 – Apr 18)

- [ ] History view (timeline, filter by category/date, search)
- [ ] Insights page (weekly summary, streak tracker, calendar heatmap, category chart)
- [ ] Settings page (theme, notifications, default preferences)
- [ ] Profile editing + data export (JSON)
- [ ] Loading states, empty states, error states across all pages
- [ ] Micro-animations (Framer Motion)
- [ ] Lighthouse audit (target 90+ score)

---

## 🔴 Phase 4 — Launch (Week 12–16, Apr 19 – May 22)

- [ ] Configure `next-pwa` (manifest, service worker, all icon sizes)
- [ ] Offline basic support + install prompt
- [ ] Full manual QA + cross-browser + mobile device testing
- [ ] Performance optimization
- [ ] Build landing page with Next.js (SEO, OG images, demo GIF)
- [ ] Invite 30–50 beta users + Typeform feedback
- [ ] Bug fixes from beta
- [ ] Product Hunt launch assets (social images, tagline, screenshots)
- [ ] Product Hunt launch + Twitter/LinkedIn/Indie Hackers announcement

---

## 🟡 Post-MVP (Month 5–7)
- [ ] Bulk URL import (paste 10+ URLs at once)
- [ ] CSV/JSON import from other apps
- [ ] Item expiration (auto-archive old items)
- [ ] Advanced filters (multi-select, date range)
- [ ] iOS Share Extension (Swift/SwiftUI)
- [ ] Android Share Extension (Kotlin/Jetpack Compose)
- [ ] Chrome browser extension (Manifest V3)
- [ ] Safari extension

---

## 🟢 Future (Year 2–3)
- [ ] YouTube Watch Later sync (official API)
- [ ] Notion database integration
- [ ] Pocket saved articles sync
- [ ] iOS & Android home screen widgets
- [ ] AI auto-categorization (OpenAI API)
- [ ] Voice features (Siri Shortcuts, Web Speech API)
- [ ] Predictive suggestions (skip prediction, best-time patterns)
- [ ] Native React Native app (if PWA insufficient)
- [ ] Enterprise: team workspaces, SSO, admin dashboard

---

## 📌 Notes
- **Never** scrape Instagram, Netflix, TikTok, or Twitter — use share sheet or official APIs only
- TMDB API is free and already planned for movie/show metadata
- Target: Product Hunt launch May 22, 2026
