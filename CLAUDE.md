# PhillipLoans — CLAUDE.md

**Client:** Phillip La — Mortgage Loan Officer, Loan Factory, California  
**Site:** philliplaloans.com (GitHub Pages, repo: Cal-Zentara/phillip-laloans)  
**Version:** 1.4  
**Status:** Step 1 done (SEO expansion complete). Step 2 in progress. Step 3 planned.

---

## Table of Contents

1. [Project Overview](#project-overview)
2. [File Structure](#file-structure)
3. [Site Sections — What, Where, Why](#site-sections)
4. [Color & Typography](#color--typography)
5. [Key Decisions](#key-decisions)
6. [Phil's Info](#phils-info)
7. [Pending Steps](#pending-steps)
8. [Version History](#version-history)

---

## Project Overview

Three-step system for Phil:
1. **Landing page** — personal brand site at philliplaloans.com. DONE.
2. **GMB cleanup** — fix his Google My Business listing. IN PROGRESS.
3. **Realtor outreach system** — Elevasis workflow to cold email California realtors. PLANNED.

Phil's Loan Factory page: `loanfactory.com/phillipla` — this is his brokerage page. The custom site is his personal brand on top of that. All CTAs go to `loanfactory.com/phillipla/apply`.

---

## File Structure

```
PhillipLoans/
├── index.html                      — Main landing page (single file, all CSS/JS inline)
├── CNAME                           — Contains: philliplaloans.com
├── CLAUDE.md                       — This file
├── .impeccable.md                  — Design context — read by Impeccable skills
├── robots.txt                      — Tells Google what to crawl + sitemap location
├── sitemap.xml                     — All 16 URLs listed for Google indexing
├── llm.txt                         — Business description for AI crawlers (ChatGPT, Perplexity)
├── ca-dream-for-all/
│   └── index.html                  — CA Dream For All program explainer page
├── fha-loans/
│   └── index.html                  — FHA loan explainer for CA first-time buyers
├── vietnamese-loan-officer/
│   └── index.html                  — Bilingual service page (English + Vietnamese)
├── irvine/index.html               — City page: Irvine
├── anaheim/index.html              — City page: Anaheim
├── huntington-beach/index.html     — City page: Huntington Beach
├── garden-grove/index.html         — City page: Garden Grove (bilingual focus)
├── fullerton/index.html            — City page: Fullerton
├── orange/index.html               — City page: Orange
├── newport-beach/index.html        — City page: Newport Beach (jumbo focus)
├── costa-mesa/index.html           — City page: Costa Mesa
├── yorba-linda/index.html          — City page: Yorba Linda (jumbo/move-up focus)
├── santa-ana/index.html            — City page: Santa Ana
├── discovery-form/
│   └── index.html                  — Discovery form (deployed separately, Formspree)
└── pics/
    ├── HeadShot.png                — Phil's headshot (blue blazer), used in hero
    ├── download.png                — Loan Factory asset (NOT used)
    ├── buy_vs_rent_lf_non_shadow.png — Loan Factory infographic (NOT used)
    ├── landscape.png               — Loan Factory asset (NOT used)
    └── Screenshot 2024-08-19 130045.png — Loan Factory asset (NOT used)
```

---

## Site Sections

> Section order on the page (top to bottom): Nav → Hero → NMLS Strip → LF Network → **Dream (CA Dream For All)** → Loans → Why Phil → Testimonials → Calculator → CTA → Footer.
> Stats Grid was removed in v1.3 (redundant with NMLS Strip + LF Network).

| Section | What It Is | Why |
|---|---|---|
| CSS Variables | Color + font tokens (charcoal `#141414` + orange `#E8622A`) | Charcoal/orange theme to match Loan Factory |
| Nav | Fixed nav — PL monogram + links + Apply Now button | Always-visible CTA |
| Hero | Split layout — text left, headshot right + diagonal panel + 2 geo squares | First impression, personal brand. Tagline: "I help California homebuyers pick the right loan, not the easiest one to close." |
| NMLS Strip | Compliance bar — NMLS numbers, CA license, languages | Legal requirement + trust signal |
| LF Network | "Backed by Loan Factory" — 226 partners / 2,397 LOs / 48 states / 18,308+ Google reviews | Bridge between Phil's personal brand + brokerage. Shows he's not a solo guy in a closet |
| Dream (CA Dream For All) | Featured editorial block — eyebrow + big headline + body + "Up to 20%" stat aside | Phil's actual edge — most loan officers don't even know this CA program exists. Pulled out of loans grid in v1.3 to lead the conversation |
| Loans Grid | 7 loan cards + 1 "Not sure which one?" CTA card in 4-col grid | Shows range. CTA card fills 8th slot so first-timers (Maria persona) have an entry point if overwhelmed |
| Why Phil | 4 reasons with numbered boxes (01–04) | Differentiates Phil from generic lenders |
| Testimonials | 4 real reviews from Phil's Google/Yelp | Social proof — real names, real quotes |
| Calculator | Mortgage calculator with rate estimation | High-value tool — keeps people on page |
| CTA Section | Final push — Apply, phone, email, Instagram | Captures anyone who scrolled this far |
| Footer | Phil's name + compliance text + Loan Factory co-brand | Legal + brand affiliation |

> **Line numbers** shift every time a section is added/removed. Grep for the section comment (e.g. `<!-- DREAM`, `<!-- LOANS -->`) instead of trusting numbers in this doc.

---

## Color & Typography

```css
--navy:       #141414   /* near-black charcoal background (true charcoal — restored v1.3) */
--navy-mid:   #1c1c1c   /* slightly lighter for card backgrounds */
--navy-light: #282828   /* hover states, gradients */
--gold:       #E8622A   /* Loan Factory orange — primary accent */
--gold-light: #f07845   /* hover state for orange */
--text:       #f0ede6   /* warm cream text */
--text-muted: rgba(240,237,230,0.55)
--border:     rgba(232,98,42,0.15)
```

**Fonts:** Cormorant Garamond (headings, italic accents) + Outfit (body, buttons)

**Why charcoal + orange:** Original theme was navy + gold. Phil asked to tie in with Loan Factory colors. Orange on navy looked sporty. Switched navy → charcoal so orange reads premium, not athletic.

---

## Key Decisions

| Decision | What We Did | Why |
|---|---|---|
| No form on landing page | Single CTA button → loanfactory.com/phillipla/apply | Phil said collecting info twice (on site + Loan Factory) was bad UX |
| No live rate chart | Built calculator with estimated rate ranges instead | Loan Factory rates use proprietary backend — can't replicate |
| No emojis | Numbered gold boxes (01–04) for icons | Cal's rule. Icons without emojis |
| Charcoal instead of navy | Background changed from #08111e to #141414 | Navy + orange reads sporty. Charcoal keeps it premium |
| Loan Factory co-brand in footer | Text badge: "Licensed with LOAN FACTORY® NMLS #320841" | Phil's Loan Factory assets were too cheesy to use as images |
| Phone: 714-726-6333 | Used direct line throughout site | Phil said 714-989-6421 is a Google Voice number he "kinda hates" |
| Hero geo squares + diagonal panel kept | Kept the rotated orange-bordered squares and clip-path slab behind Phil's photo | v1.3 critique flagged them as AI slop, but Cal explicitly liked the layered hero composition. Don't remove again |
| No cave/rock textures on background | Kept original faint noise overlay only (`opacity: 0.04`) | v1.3 tested heavy grain + mottled "stone" patches + low-frequency turbulence "rock" textures. Cal rejected all of them — too busy. Plain charcoal + faint noise wins |
| Stats Grid permanently removed | Deleted "8+ / CA / 24/7 / 5★" block | Redundant with NMLS Strip + LF Network. "24/7 available" also sets an expectation Phil can't meet — breaks the honest brand promise |
| Float animation off | Removed the gentle up/down loop on Phil's headshot | Private-bank reference tone calls for stillness. Confidence doesn't wiggle |
| Design context lives in `.impeccable.md` | Project root file, written by `/impeccable teach` in v1.3 | Future Impeccable skills (`/critique`, `/polish`, `/audit`, etc.) read this file to design to Phil's actual brand instead of generic AI defaults |

---

## Phil's Info

| Field | Value |
|---|---|
| Full name | Phillip La |
| Title | Mortgage Loan Officer |
| Brokerage | Loan Factory |
| MLO NMLS | #2493651 |
| Loan Factory NMLS | #320841 |
| Phone (direct) | 714-726-6333 |
| Phone (Google Voice — avoid) | 714-989-6421 |
| Email | phillip.la@loanfactory.com |
| Instagram | @phillip.laloans |
| Apply link | https://www.loanfactory.com/phillipla/apply |
| Languages | English, Vietnamese |
| License | California |

---

## Pending Steps

### Step 2 — GMB Cleanup (IN PROGRESS)
Cal logging into Phil's Google account to update:
- Business name: `Phillip La — Mortgage Loan Officer`
- Phone: `714-726-6333`
- Description: *"I help California homebuyers and homeowners navigate the mortgage process with clarity and honesty. Whether you're buying your first home, investing in property, or looking to refinance, I'll find the right loan for your situation — not just the easiest one to close. Licensed in California, NMLS #2014566."*
- Website: `https://philliplaloans.com`
- Photo: upload `pics/HeadShot.png`

Go to: business.google.com

### Step 3 — Realtor Outreach System (PLANNED)
Elevasis workflow:
- **Apify** — scrape Google Maps for California realtors by city
- **AnyMailFinder** — enrich names + domains → get personal emails
- **LLM** — personalize each email (name, city, brokerage)
- **Instantly** — send cold email campaign
- Phil starting from scratch — no existing tools

---

## Version History

| Version | Date | What Changed |
|---|---|---|
| 1.0 | 2026-04-14 | Initial build — full landing page, navy/gold theme |
| 1.1 | 2026-04-14 | Fixed 4-column loan grid (was 3-col with empty cell), added real testimonials |
| 1.2 | 2026-04-14 | Rethemed to charcoal + Loan Factory orange, added LF co-brand footer |
| 1.3 | 2026-04-15 | Ran Impeccable critique. Fixed dark-green palette drift back to true charcoal. Replaced "Friendly Neighborhood" tagline with "I help California homebuyers pick the right loan, not the easiest one to close." Deleted Stats Grid (8+/CA/24/7/5★). Pulled CA Dream For All out as featured editorial block between LF Network and Loans. Removed float animation on hero photo. Added "Not sure which one?" CTA card to fill 8th loans-grid slot. |
| 1.4 | 2026-04-19 | Full SEO expansion. Added robots.txt, sitemap.xml (14 URLs), llm.txt. Built 10 city pages (Irvine, Anaheim, Huntington Beach, Garden Grove, Fullerton, Orange, Newport Beach, Costa Mesa, Yorba Linda, Santa Ana) — each with unique market copy, loan grid, CA Dream For All callout, and JSON-LD schema. Built 3 service pages (CA Dream For All, FHA Loans, Vietnamese Loan Officer). All pages interlinked via city chips. Strategy: rank for "[loan officer] in [city]" searches across Orange County. |
