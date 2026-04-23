# STATUS — Phillip La Loans

*Last updated: 2026-04-23*

## What this is
Personal brand site + GMB cleanup + planned realtor outreach system for Phillip La, Mortgage Loan Officer at Loan Factory (California). Bilingual English/Vietnamese.

## What's live
- Main site — https://philliplaloans.com (v1.5)
- 18 URLs in sitemap (10 city pages, 7 service pages, homepage)
- Service pages: CA Dream For All, FHA, Vietnamese, VA, First Time Home Buyer, Refinance, Conventional
- City pages: Irvine, Anaheim, Huntington Beach, Garden Grove, Fullerton, Orange, Newport Beach, Costa Mesa, Yorba Linda, Santa Ana
- Discovery form deployed separately (Formspree)
- GMB mostly cleaned up April 19 — name, phone, description, website, Asian-owned flag all set

## What's broken / blocked
- **GMB verification pending** — Phil records the verification video live in the Google Business Profile app on his phone. Cal can't do this. Phil doing it himself.
- **GMB cover photo** — waiting on verification to swap family group shot → `pics/HeadShot.png`
- **Step 3 (realtor outreach)** — planned, not started. Elevasis workflow: Apify scrape → AnyMailFinder → LLM personalize → Instantly send.

## What's next
1. Follow up with Phil on GMB verification video recording
2. Swap GMB cover photo to HeadShot once verified
3. Monitor GSC for SEO page indexing (expect 2-8 weeks)
4. Start Step 3 — build Elevasis realtor outreach workflow

## Key files
- `index.html` — main landing page (single-file, all CSS/JS inline)
- `<city>/index.html` — 10 city pages
- `<service>/index.html` — 7 service explainer pages
- `sitemap.xml` + `robots.txt` + `llm.txt` — SEO files
- `.impeccable.md` — design context for future Impeccable skill runs
- `CLAUDE.md` — full doc, decisions, version history, Phil's info

## Deploy notes
- GitHub: `Cal-Zentara/phillip-laloans`
- Domain: philliplaloans.com (CNAME in repo)
- Hosting: GitHub Pages
- **Grep for section comments** (e.g. `<!-- DREAM`, `<!-- LOANS -->`) — don't trust line numbers, structure shifts between versions
- All apply CTAs → `loanfactory.com/phillipla/apply` (Phil's brokerage backend)
- Phone: **714-726-6333** (direct). Do NOT use 714-989-6421 (Google Voice, Phil hates it).
