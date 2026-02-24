# NexCue — Your Universal "What's Next?" Engine

> **Platform:** Web PWA (Next.js 14) · **Stage:** Pre-development (docs only) · **Target Launch:** May 22, 2026  
> **Market:** Global (English-first, India priority) · **Team:** 4 members

NexCue is a **universal content queue and decision engine**. You save too much — YouTube, recipes, articles, Netflix shows, courses — and never get back to any of it. NexCue brings everything into one inbox and answers one question: **"What should I do next?"**

> *Decide less. Do more.*

---

## The Problem

| Platform | What You Save | % Ever Revisited |
|----------|--------------|-----------------|
| Instagram | Posts, Reels | 5% |
| YouTube | Watch Later | 10% |
| Browser | Bookmarks | 2% |
| Podcast Apps | Episodes | 15% |
| Notes App | Screenshots | 15% |

Thousands of items saved. Decision paralysis. Nothing ever watched.

---

## How It Works

```
1. Add anything  →  Paste a URL, share from any app, or type it manually
2. Tap "Decide"  →  Pick how much time you have (15 / 30 / 60 min)
3. Get a match   →  NexCue picks the best item for your time + mood
4. Start it      →  One tap. No more scrolling.
```

---

## Content Categories (Built-in)

| Category | Examples |
|----------|---------|
| 📺 Watch | YouTube, Netflix, saved reels |
| 📚 Read | Articles, books, newsletters |
| 🎧 Listen | Podcasts, audiobooks, albums |
| 🎓 Learn | Courses, tutorials, workshops |
| 🍳 Cook | Recipes, meal ideas |
| ⚡ Do | Side projects, tasks |
| 🛒 Buy | Wishlist, shopping |
| ✨ Custom | Anything you define |

---

## Tech Stack

| Layer | Technology |
|-------|-----------|
| Framework | Next.js 14 (App Router) |
| Language | TypeScript |
| Database | Supabase (PostgreSQL + RLS) |
| Auth | Supabase Auth (Email, Google, Apple) |
| Hosting | Vercel |
| State | React Query (TanStack Query) |
| Styling | Tailwind CSS |
| Animations | Framer Motion |
| Metadata API | TMDB (movies/shows), Open Graph (URLs) |

---

## Project Status

> ⚠️ **Pre-development** — Documentation and planning complete. No code written yet.

See [`REMAINING_TASKS.md`](./REMAINING_TASKS.md) for the full phased build plan.

---

## Roadmap

| Phase | Timeline | Focus |
|-------|----------|-------|
| Phase 1 | Feb – Mar 2026 | Setup, Auth, Base UI |
| Phase 2 | Feb 22 – Mar 28 | Core MVP: Inbox + Decide Engine |
| Phase 3 | Mar 29 – Apr 18 | History, Insights, Polish |
| Phase 4 | Apr 19 – May 22 | PWA, QA, Product Hunt Launch |
| Post-MVP | Month 5–7 | Share Extensions, Browser Extension |
| Future | Year 2–3 | AI, Native Apps, Enterprise |

---

## Key Constraint

> Never scrape Instagram, Netflix, TikTok, or Twitter. Use share-sheet or official APIs only.

---

*Target: Product Hunt launch May 22, 2026*