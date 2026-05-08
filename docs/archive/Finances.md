# NexCue - Financial Plan

> **Document Type:** Financial Planning  
> **Version:** 1.1  
> **Last Updated:** January 27, 2026  
> **Team:** 4 Members  
> **Market:** Global (English-first, India priority)

---

## Project Context

NexCue is a **universal "What's Next?" decision engine** for all saved content across platforms - YouTube Watch Later, Netflix My List, Instagram Saved, podcasts, articles, recipes, wishlists, and more.

**Team:** 4 members (Dev Lead, Designer, Backend, Tester/Security)

---

# Revenue Model

## Revenue Streams

| Stream | % Revenue | Details |
|--------|-----------|---------|
| **Subscriptions** | 80% | Freemium → Pro → Team |
| **Lifetime Deals** | 15% | Launch strategy (limited time) |
| **Future B2B/API** | 5% | Team plans, white-label |

---

# Pricing Strategy

## User Subscription Tiers

| Tier | Monthly | Yearly | Yearly Savings |
|------|---------|--------|----------------|
| **Free** | Rs.0 | Rs.0 | - |
| **Pro** | Rs.149 | Rs.999 | 44% |
| **Team** | Rs.299/user | Rs.2,499/user | 30% |

*Pricing comparable to Netflix Mobile (Rs.149), Spotify (Rs.119), Notion (Rs.96)*

## Feature Comparison

| Feature | Free | Pro (Rs.149) | Team |
|---------|------|--------------|------|
| Total items | 25 | Unlimited | Unlimited |
| Categories | 3 | Unlimited | Unlimited |
| Decide engine | Basic | Smart + Mood | Smart |
| History | 7 days | Full | Full |
| Insights/Stats | Basic | Full analytics | + Team stats |
| Export data | - | ✓ | ✓ |
| Browser extension | - | ✓ | ✓ |
| Share extension | ✓ | ✓ | ✓ |
| Priority support | - | ✓ | ✓ |
| Shared lists | - | - | ✓ |

---

## Special Offers

### Launch Offers

| Offer | Details |
|-------|---------|
| **Lifetime Early Bird** | Rs.1,499 (first 250 users) |
| **Lifetime Standard** | Rs.2,499 (next 500 users) |
| **Product Hunt Deal** | 40% off first year (Rs.599) |
| **Student Discount** | 50% off with .edu email |
| **Referral Bonus** | 1 month free for both parties |

### Lifetime Deal Strategy

| Phase | Price | Quantity | Revenue |
|-------|-------|----------|---------|
| Super Early | Rs.1,499 | 250 | Rs.3,74,750 |
| Early | Rs.2,499 | 500 | Rs.12,49,500 |
| **Total LTD** | - | **750** | **Rs.16,24,250** |

*Lifetime deals fund Year 1, then discontinued*

---

# Development & Operating Costs

## Free Tier Services

| Service | Provider | Free Limit | Enough For |
|---------|----------|------------|------------|
| Hosting | Vercel | 100GB bandwidth | 50K users |
| Database | Supabase | 500MB, 50K MAU | 30K users |
| Auth | Supabase | Included | All users |
| Analytics | PostHog | 1M events/mo | All traffic |
| Errors | Sentry | 5K errors/mo | MVP |
| Emails | Resend | 100/day | Transactional |
| Movie Metadata | TMDB API | Free unlimited | All lookups |
| Open Graph | Self-hosted | Free | Link previews |

**You can run FREE until 20,000-30,000 active users!**

## Year 1 Costs (Minimal)

| Category | Monthly | Yearly | Notes |
|----------|---------|--------|-------|
| **Supabase** | Rs.0-1,000 | Rs.0-12,000 | Free tier mostly |
| **Vercel** | Rs.0 | Rs.0 | Free tier |
| **Domain** | - | Rs.1,500 | nexcue.com |
| **Email (Resend)** | Rs.0-500 | Rs.0-6,000 | Free tier initially |
| **Analytics** | Rs.0 | Rs.0 | PostHog free |
| **Marketing** | Rs.2,000 | Rs.25,000 | Paid promotion |
| **Misc** | Rs.500 | Rs.6,000 | Buffer |
| **TOTAL** | **~Rs.3,000** | **~Rs.50,000** | |

### One-Time Costs

| Item | Cost |
|------|------|
| Domain purchase | Rs.1,500 |
| Premium assets (icons, fonts) | Rs.3,000 |
| Legal templates (Privacy, ToS) | Rs.5,000 |
| Video/GIF creation | Rs.5,000 |
| Product Hunt hunter outreach | Rs.0 (organic) |
| **TOTAL** | **Rs.14,500** |

---

## Phase 2+ Development Costs (Post-Launch)

### Extension Development (Months 5-8)

| Component | One-Time Cost | Notes |
|-----------|---------------|-------|
| Apple Developer Account | Rs.8,500/yr | Required for iOS Share Extension |
| Google Play Developer | Rs.2,100 (once) | Required for Android |
| Chrome Web Store | Rs.500 (once) | One-time registration |
| **TOTAL** | **~Rs.11,000** | First year |

### Year 2+ Additional Costs

| Item | Monthly | Annual | Notes |
|------|---------|--------|-------|
| OpenAI API (AI features) | Rs.5,000-15,000 | Rs.60,000-1.8L | Based on usage |
| Supabase Pro (if needed) | Rs.2,100 | Rs.25,000 | At 50K+ users |
| Vercel Pro (if needed) | Rs.1,700 | Rs.20,000 | At scale |
| YouTube API (if limits hit) | Rs.0 | Rs.0 | Generous free tier |
| Apple Developer renewal | - | Rs.8,500 | Annual |
| **TOTAL (Year 2)** | - | **Rs.1.5-3L** | Scales with users |

---

## Cost Scaling

| Active Users | Monthly Cost | Notes |
|--------------|--------------|-------|
| 0-5,000 | Rs.0-2,000 | Free tiers cover |
| 5,000-15,000 | Rs.2,000-5,000 | Minor overages |
| 15,000-30,000 | Rs.5,000-10,000 | Upgrade some services |
| 30,000-50,000 | Rs.10,000-20,000 | Pro tiers needed |
| 50,000+ | Rs.25,000+ | Scale infrastructure |

---

# Revenue Projections

## User Growth (Conservative)

| Month | Total Users | Paid Users | Conversion |
|-------|-------------|------------|------------|
| Month 1 (Launch) | 1,000 | 75 | 7.5% |
| Month 3 | 3,000 | 300 | 10% |
| Month 6 | 8,000 | 1,040 | 13% |
| Month 9 | 12,000 | 1,920 | 16% |
| Month 12 | 18,000 | 3,240 | 18% |

## Monthly Recurring Revenue (MRR)

| Month | Paid Users | ARPU | MRR |
|-------|------------|------|-----|
| Month 1 | 75 | Rs.120 | Rs.9,000 |
| Month 3 | 300 | Rs.125 | Rs.37,500 |
| Month 6 | 1,040 | Rs.125 | Rs.1,30,000 |
| Month 9 | 1,920 | Rs.130 | Rs.2,49,600 |
| Month 12 | 3,240 | Rs.130 | Rs.4,21,200 |

*ARPU = Average Revenue Per User (blend of monthly/yearly)*

## Year 1 Financial Summary

### Revenue

| Source | Amount |
|--------|--------|
| Subscriptions (cumulative MRR) | Rs.15,00,000 |
| Lifetime Deals | Rs.16,24,250 |
| **TOTAL REVENUE** | **Rs.31,24,250** |

### Costs

| Category | Amount |
|----------|--------|
| Infrastructure (yearly) | Rs.50,000 |
| One-time costs | Rs.14,500 |
| Contingency (10%) | Rs.6,500 |
| **TOTAL COSTS** | **Rs.71,000** |

### Profit

| Metric | Amount |
|--------|--------|
| **Gross Revenue** | Rs.31,24,250 |
| **Total Costs** | Rs.71,000 |
| **NET PROFIT (Year 1)** | **Rs.30,53,250** |
| **Profit Margin** | 97.7% |

*Note: Team time is unpaid/equity in Year 1*

---

## Break-Even Analysis

| Metric | Value |
|--------|-------|
| Monthly Fixed Costs | Rs.3,000 |
| ARPU (blended) | Rs.125 |
| Break-even Paid Users | 24 users |
| At 10% conversion | 240 total users |

**BREAK-EVEN: ~250 users (Week 2-3 post-launch)**

---

## 3-Year Projection

| Year | Users | Paid Users | Revenue | Costs | Profit |
|------|-------|------------|---------|-------|--------|
| Year 1 | 18K | 3,240 | Rs.31L | Rs.0.8L | Rs.30L |
| Year 2 | 60K | 12,000 | Rs.80L | Rs.8L | Rs.72L |
| Year 3 | 150K | 30,000 | Rs.2.5Cr | Rs.25L | Rs.2.25Cr |

### Year-by-Year Cost Breakdown

**Year 1 (MVP + Launch): Rs.0.8L**
- Infrastructure: Rs.50K
- One-time costs: Rs.15K
- Extensions (Apple/Google/Chrome): Rs.11K
- Buffer: Rs.4K

**Year 2 (Extensions + Integrations): Rs.8L**
- Infrastructure (scaled): Rs.2L
- Apple Developer renewal: Rs.8.5K
- OpenAI API (AI features): Rs.1.2L
- Marketing: Rs.2L
- Team expenses (part-time): Rs.2.5L

**Year 3 (AI + Scale): Rs.25L**
- Infrastructure (pro tiers): Rs.5L
- OpenAI API (heavy usage): Rs.4L
- Team salaries (full-time): Rs.12L
- Marketing: Rs.3L
- Miscellaneous: Rs.1L

---

# Funding Strategy

## Bootstrap Approach

### Phase 1: Development (Rs.0)
- All free tier services
- Team works for equity

### Phase 2: Launch (Rs.30,000)

| Item | Cost |
|------|------|
| Domain + Legal | Rs.6,500 |
| Assets + Video | Rs.8,000 |
| Marketing | Rs.10,000 |
| Buffer | Rs.5,500 |

### Phase 3: Growth (Self-funded)
- Lifetime deals fund operations
- Reinvest 30% of monthly revenue
- No external funding needed until Year 2

> **TOTAL INITIAL INVESTMENT: Rs.30,000**

---

## Optional: Accelerated Growth

If we want to grow faster, funding options at milestones:

| Stage | When | Amount | Use |
|-------|------|--------|-----|
| Friends & Family | 5K users | Rs.5L | Marketing |
| Angels | 25K users | Rs.20-50L | Team expansion |
| Seed | 100K users | Rs.2-5Cr | Scale |

---

# Key Metrics to Track

## Monthly Dashboard

| Metric | Month 6 Target | Month 12 Target |
|--------|----------------|-----------------|
| Total Users | 8,000 | 18,000 |
| Paid Subscribers | 1,040 | 3,240 |
| MRR | Rs.1,30,000 | Rs.4,21,200 |
| Conversion Rate | 13% | 18% |
| Monthly Churn | <6% | <5% |
| NPS | 45+ | 55+ |

## Unit Economics Targets

| Metric | Target |
|--------|--------|
| CAC (organic) | Rs.0-25 |
| CAC (paid) | Rs.150-250 |
| LTV (12 months) | Rs.1,200-1,800 |
| LTV:CAC Ratio | 6x+ |
| ARPU | Rs.125-150 |
| Gross Margin | 95%+ |

---

# Financial Risks & Mitigation

| Risk | Probability | Impact | Mitigation |
|------|-------------|--------|------------|
| Low conversion | Medium | High | Clear Pro value, good onboarding |
| High churn | High | High | Focus on habit formation |
| Lifetime deals oversold | Low | Medium | Strict limits (750 total) |
| Infrastructure costs spike | Low | Medium | Billing alerts, optimize |
| No Product Hunt feature | Medium | Medium | Multiple launch strategies |

## Cost Control Rules

1. **Never exceed Rs.10,000/mo** until MRR covers it
2. **Set billing alerts** at Rs.2K, Rs.5K, Rs.10K
3. **Free tier first** - upgrade only when necessary
4. **LTD funds ops** - don't spend MRR until Month 6
5. **Reinvest 30%** of profit, save 70%

---

# Summary

## Financial Overview

| Metric | Value |
|--------|-------|
| **Initial Investment** | Rs.30,000 |
| **Year 1 Operating Costs** | Rs.80,000 |
| **Break-even Point** | 250 users (Week 2-3) |
| **Year 1 Revenue** | Rs.31,24,250 |
| **Year 1 Profit** | Rs.30,44,250 |
| **Year 1 ROI** | 10,000%+ |
| **Year 3 Revenue** | Rs.2.5Cr |
| **Year 3 Profit** | Rs.2.25Cr |

## Pricing Summary

| Tier | Price | Value |
|------|-------|-------|
| **Free** | Rs.0 | 25 items, 3 categories |
| **Pro Monthly** | Rs.149 | Unlimited everything |
| **Pro Yearly** | Rs.999 | 44% savings |
| **Lifetime (Launch)** | Rs.1,499-2,499 | Forever access |

---

*End of Financial Plan*
