# Skynet Site System — 60-Site Master Playbook

> **Distilled from 60 shipped client websites.** A complete website-design system for landing pages, agency demos, and freelance Upwork/Fiverr builds — niche-tuned design tokens, conversion-locked funnel, speculative-build pitch flow, and 3-variant client-pick lock with a sticky variant switcher.

## Status

Last reviewed: October 2026 · release v2026.10

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Built by SkynetLabs](https://img.shields.io/badge/Built%20by-SkynetLabs-0F0E0D.svg)](https://www.skynetjoe.com)
[![Sites Mined](https://img.shields.io/badge/Sites%20Mined-60-8B3A3A.svg)](#case-studies)
[![Niches](https://img.shields.io/badge/Niches-17-C8A579.svg)](#design-tokens)

A reusable website-design playbook for freelancers, agencies, and AI coding agents (Claude Code, Cursor, v0, Lovable). Mined from 60 actually-shipped client sites — not curated theory.

---

## What this is

This isn't another awesome-list. It's an **extracted system** — every rule, palette, font pair, and anti-pattern came from a real client revision cycle on Vercel + GitHub.

- **8-phase build flow** — from input to ship + pitch in one session
- **17 niche design tokens** — real hex codes + font pairs that closed real clients (wedding, medical, wellness, law, HVAC, finance, dental, real estate, photography, restaurant, beauty, trades, indie events, e-commerce, B2B SaaS, agency, portfolio)
- **60 case studies** — Tier 1 flagships (Vow Sanctuary, Wellness DNA, Pretty Potty, FundRock Capital, AXIS RX, Helix Wellness, SkynetLabs Clinic) + Tier 2 production (24 builds) + Tier 3 generator (20 niche demos)
- **3-variant lock** — every client demo ships V1 Editorial / V2 Cinematic / V3 Bold with a sticky top-right switcher (URL-hash routed, mobile-collapsed, share-friendly)
- **Pitch template + 7 scope-question sets** — 5–8 questions per niche, validated ~70% reply rate
- **Competitor research agent prompts** — 3 parallel research agents (competitor teardown / niche taste signals / keyword + EEAT + schema)
- **Anti-pattern catalogue** — what NOT to do, learned the hard way

---

## Quick start

### As a Claude Code skill

```bash
git clone https://github.com/waseemnasir2k26/skynet-site-system.git ~/.claude/skills/skynet-site
```

Trigger from any Claude Code session:

```
/skynet-site

Or paste any client brief / Upwork JD / Fiverr buyer note.
```

### As a manual playbook

Open [`SKILL.md`](./SKILL.md). 8 phases, 13 hard rules. Follow top-to-bottom.

---

## Repo structure

```
skynet-site-system/
├── SKILL.md                          # 8-phase build flow + 13 hard rules + master prompt
├── case-studies.md                   # 60-site comparison + Tier 1/2/3/4 + patterns
├── design-tokens.md                  # 17-niche palette + font pair lookup
├── scope-questions.md                # 5–8 scope Qs per niche (universal + 7 overrides)
├── pitch-template.md                 # verbatim pitch message + 3 worked examples
├── competitor-research-template.md   # 3 parallel research agent prompts
├── recipes/
│   └── variant-switcher.md           # Sticky top-right 3-variant switcher (React + vanilla JS)
└── README.md                         # this file
```

---

## The 8-phase build flow

| Phase | What | Time |
|---|---|---|
| 1 — Inputs | Brief · niche · client name · budget · timeline | 5 min |
| 2 — Research | 3 parallel agents (competitor / taste / SEO) | 10 min |
| 3 — Design Token Lock | Pick from 17-niche table — never default | 5 min |
| 3.5 — 3-Variant Lock | Editorial / Cinematic / Bold | locked |
| 3.6 — Sticky Switcher | Top-right `position:fixed; top:20px; right:20px` | locked |
| 4 — Stack Pick | Static / pure HTML / Next.js+R3F / WP demo-first | 5 min |
| 5 — Build | 8-section funnel (hero → trust → services → about → process → testimonials → gallery → FAQ → lead-magnet → footer) | 2–5 hr |
| 6 — Premium Signatures | 4–6 niche-fit picks | woven |
| 7 — Conversion Guardrails | Lighthouse ≥90 · LCP ≤2.5s · ≤6 form fields | check |
| 8 — Ship + Pitch | gh repo + Vercel + 5–8 scope Qs | 30 min |

---

## Design tokens — 17 niches

| Niche | Palette | Display Font | Body Font |
|---|---|---|---|
| Wedding / vow / luxury event | Warm beige `#F2EBE0` + Claret `#8B3A3A` + Champagne | Instrument Serif | Inter |
| Wellness / DNA / premium health | Bone `#F4F1EB` + Sage `#7A8B6F` | Apothecary serif | Inter |
| Medical / clinic / surgical | Forest `#2D4A3E` + Mint `#7EC8A0` | Cormorant Garamond | Inter |
| UK healthcare / nursing | Navy `#0A2540` + Teal-glow `#2DD4BF` | Fraunces | Inter |
| Medical pharmacy / GLP-1 | Navy `#11112e` + Royal-blue `#2c51a3` | Satoshi | Inter |
| Luxury rental / event service | Rose-gold `#D4A574` + Cream | Playfair Display | Lato |
| Indie event / wrestling / sport | Black + Electric red `#E63946` + yellow | Anton / Bebas | Inter |
| Wellness coach + book funnel | Cream-warm + multi-accent | Fraunces | Inter |
| HVAC / plumbing / trades | Steel blue + Safety orange | Manrope | Inter |
| Dental | Off-white + Mint `#10B981` | Playfair Display | DM Sans |
| Law firm | Oxblood `#7B1F2C` + Brass `#B8924B` | Lora | Inter |
| Real estate luxury | Sand + Bronze | Cormorant SC | Inter |
| Restaurant fine-dine | Burgundy + Gold leaf | Italiana | Inter |
| Beauty / spa | Blush + Rose-gold | Cormorant Garamond | Lato |
| Photography portfolio | Pure black + single accent | Helvetica Neue | Inter |
| Finance / VC pitch | Obsidian + Champagne gold `#D4AF37` | Playfair Display | DM Sans |
| Tech / SaaS / agency | Off-white + cobalt/lime/coral | Space Grotesk | Inter |

Full list with don'ts in [`design-tokens.md`](./design-tokens.md).

---

## 13 hard rules

1. **Build first, pitch second.** ~10× higher close rate vs cold proposal.
2. **3-variant lock + sticky switcher.** Editorial / Cinematic / Bold + top-right pills.
3. **Niche-tune everything.** Wedding luxury ≠ corporate luxury.
4. **Real photos, not Picsum.** Unsplash CDN per niche minimum.
5. **Unique testimonials per niche.** No reuse across builds.
6. **Footer credit always.** "Built by SkynetLabs ↗" — free portfolio surface.
7. **noindex spec demos 90 days.** SpamBrain Feb 2026.
8. **No batch SEO publish.** Drip 3–5/week × months.
9. **Phase 2 upsell ALWAYS in pitch.** Phase 1 = audition.
10. **5–8 scope Qs not 16.** GutReno over-fired — reduce.
11. **First-person if solo, "we" if team.** Don't fake size.
12. **No invented metrics.** Real builds, real wins, real photos only.
13. **Image rotation log.** Never pick photos by eye.

Full reasoning in [`SKILL.md`](./SKILL.md).

---

## 3-variant lock + sticky switcher

Every client demo ships **3 variants on different axes** (not 3 versions of the same look):

| Variant | Axis | Example |
|---|---|---|
| **V1 Editorial** | Magazine grid · serif display · whitespace-heavy | Vow Sanctuary modern v3 |
| **V2 Cinematic** | R3F 3D hero or MP4 loop · dark · animation-forward | Wellness DNA Helix |
| **V3 Bold / Minimal** | Glassmorphic or brutalist · single accent · type-driven | Wellness DNA Magazine / Aesop |

**Sticky switcher spec:**
- Position: `fixed; top:20px; right:20px; z-index:99`
- 3 pills (V1 / V2 / V3) — active filled with accent color
- URL hash routing (`#v1` `#v2` `#v3`) — shareable
- Mobile: collapse to floating bottom-right circle → modal sheet
- KILL component on production after client picks

Full code in [`recipes/variant-switcher.md`](./recipes/variant-switcher.md) — React + Tailwind, vanilla JS, header-integrated alt.

---

## Stack decision tree

```
Budget < $300 / fast
  → Static HTML + Tailwind CDN + vanilla JS

Budget $300–1K / premium-feel
  → React + Vite + Framer Motion + Tailwind

Budget $1K+ / hero cinematic
  → Next.js 15+ + R3F v9 + Drei v10 + Framer + Lenis + Zod

WordPress brief
  → Build Vercel demo FIRST → Phase 2 Divi/Kadence/Woo port

Multi-region / SEO at scale
  → WordPress custom theme + companion plugin
```

---

## Speculative-build pitch flow

```
[TRIGGER WORD if Upwork-required]

Hey [Name] —

[1 SENTENCE HOOK tying to competitor gap]

Built a working concept so you can see exactly what I mean:

→ Live: [demo URL]
→ Repo: [github URL]

What's built:
• [bullet using THEIR vocabulary]
• ... 4 more

Brand + copy is placeholder. To finish + ship to your domain, I'd need:

1. [Scope Q 1]
... 5 more

Bonus: [pricing-lever Q] — changes fee.

Reply with what you have — live on your domain inside the week.
```

Full template + 3 worked examples in [`pitch-template.md`](./pitch-template.md).

---

## Patterns observed across 60 sites

- **Stack split:** React + Vite (14) · Next.js 14+ (8) · Static HTML (5) · WordPress (3) · Generated monorepo (20)
- **Most-used colors:** Navy 60% · Gold/champagne 45% · Sage 20% · Cream background 70%
- **Hero patterns:** Image overlay 50% · MP4 loop 20% · R3F 3D 15% · Editorial grid 10% · Glassmorphic 5%
- **Top techniques:** Framer Motion scroll reveals 65% · Marquee 30% · Blob morph 25% · R3F + Lenis 25% · Glassmorphism 25% · Pulse-glow 20% · Count-up 20% · Ken Burns 15% · Film grain 10%

Full breakdown in [`case-studies.md`](./case-studies.md).

---

## Anti-patterns (caught + fixed across builds)

- ❌ Same testimonial across 20 niches → 60 unique testimonials
- ❌ Picsum photos → Unsplash CDN per niche
- ❌ Gradient-shader R3F blob → 5 mesh specs per niche
- ❌ Navy + bright gold for wedding → warm beige + claret
- ❌ Cormorant for modern wedding → Instrument Serif
- ❌ 16 scope Qs → reduce to 5–8
- ❌ Batch SEO publish → drip 3–5/week
- ❌ Photo "by eye" → always rotation log

---

## Who this is for

- **Freelancers** on Upwork / Fiverr who pitch landing pages and want a higher close rate
- **Agencies** running speculative-build outreach
- **AI coding agents** (Claude Code, Cursor, v0, Lovable) — feed `SKILL.md` to ground design decisions
- **Designers** who want a real-world niche → token lookup
- **Founders** building MVPs who want a battle-tested funnel order

---

## Built by

[**SkynetLabs**](https://www.skynetjoe.com) — AI automation + n8n + Shopify + WordPress + AEO/SEO. Personal: [waseemnasir.com](https://www.waseemnasir.com).

GitHub: [@waseemnasir2k26](https://github.com/waseemnasir2k26)

---

## License

[MIT](./LICENSE) — fork it, ship it, sell with it. Credit appreciated, not required.

---

## Keywords

`website-design` `landing-page` `freelance-playbook` `design-system` `nextjs-template` `react-template` `tailwindcss` `framer-motion` `react-three-fiber` `r3f` `vercel` `upwork` `fiverr` `agency-toolkit` `claude-code` `claude-code-skill` `cursor` `v0` `ai-coding-agent` `design-tokens` `speculative-build` `conversion-optimization` `wedding-website` `wellness-website` `medical-website` `law-firm-website` `hvac-website` `dental-website` `restaurant-website`


## Work with SkynetLabs

Built by [Waseem Nasir](https://www.skynetjoe.com/?utm_source=github&utm_medium=readme&utm_campaign=skynet-site-system) at SkynetLabs — n8n + AI automation for small businesses.

- Hire on Fiverr: https://www.fiverr.com/agencies/skynetjoellc
- Hire on Upwork: https://www.upwork.com/freelancers/muhammadwaseemnasir
- Book a free call: https://calendly.com/skynetlabs/schedule-a-free-consultation
