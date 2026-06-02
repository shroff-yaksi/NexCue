# NexCue

> Your universal "what's next?" engine. One inbox for everything you save, one Decide flow that picks the single right item by your available time and mood. *Decide less. Do more.*

You save too much — YouTube Watch Later, Netflix My List, bookmarks, recipes, courses, podcasts, wishlists — and get back to almost none of it. NexCue pulls everything into one inbox and answers a single question: **"What should I do next?"** Tell it how much time you have and (optionally) your mood; it picks one thing from your queue and lets you start in one tap. It tackles two real problems: **content guilt** (the graveyard of saved-but-untouched items) and **decision paralysis** (20 minutes of "what should I watch?" every night).

**Honest about the graveyard:** Pocket, Raindrop, and Matter all built good save-it-later products and all failed to monetize. NexCue's bet is the *Decide* loop and Weekly Active Completions, not yet-another-inbox.

**Stack:** Next.js 16 (App Router + Cache Components) · TypeScript · Supabase (Postgres, Auth, RLS) · Tailwind + shadcn/ui · TanStack Query · Framer Motion · next-pwa · Vercel.

**Wedge:** the Decide loop. Saving is solved and commoditised; *choosing what to actually do* is not. One scored item at a time, never a grid — the antidote to decision paralysis.

**Ground rules:** Never scrape Instagram / Netflix / TikTok / X — share-sheet + URL paste + official APIs only. Plain domain names in code and schema (`saved_item`, `category`, `mood`, `time_budget`, `completion`); "Cue" is a marketing word only, never in code, tables, or columns.

**Docs:** Machine-readable contracts live in [contracts/](./contracts). Full plan & spec: kept in the portfolio `planning/` workspace (not in this public repo).
