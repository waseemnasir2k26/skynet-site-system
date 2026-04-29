# Competitor Research Template

Phase 1 of build flow. Run 3 agents IN PARALLEL (single message, 3 Agent calls).

## Agent A — Competitor Teardown

```
You are researching the [NICHE] industry's top 8-12 websites to identify the
"sameness gap" we can exploit in design.

Niche: [NICHE]
Geo: [GEO if relevant — UK / US / NYC / Hamptons / etc.]
Specific brief: [PASTE BRIEF SUMMARY]

For each of 8-12 competitors, capture:

1. URL + brand name
2. Hero pattern (image / video / 3D / illustration / type-only)
3. Primary palette (3 hex codes)
4. Display font + body font (inspect or guess)
5. CTA pattern (form / phone / book / quote / chat)
6. Pricing visibility (visible / gated / hidden)
7. Trust signals shown (years / press / reviews / certifications / photos)
8. Conversion friction (form length / steps to checkout)
9. Whitespace level (dense / balanced / sparse)
10. Voice (corporate / personal / playful / clinical)

After all 8-12, identify:

- **Sameness gap** — the trait 7+ of them share (this is OUR opening)
- **Best in class** — top 2 sites doing it right (study these)
- **Opportunity wedge** — 1 sentence on what we'd do that none of them do

Output as `docs/RESEARCH-COMPETITORS.md`. Tight markdown table + bullets.
```

## Agent B — Niche Taste Signals

```
You are researching what BUYERS in the [NICHE] niche perceive as "premium."

Wedding-luxury ≠ corporate-luxury. Healthcare ≠ SaaS. We need niche-tuned taste.

Niche: [NICHE]
Buyer type: [B2C couple / B2B trade / patient / event planner / etc.]

Sources to scrape (use WebFetch + WebSearch):
- Awwwards.com — search "[niche]"
- Behance.net — search "[niche] website"
- Dribbble.com — search "[niche] landing"
- Pinterest — "[niche] website inspiration"
- 1-2 high-end real brands in niche (Aesop / Vogue Weddings / Mayo Clinic / etc.)

Capture:

1. Top 5 design refs that resonated w/ niche buyers (URLs)
2. Common typography pattern (serif display + sans body? all-sans? all-serif?)
3. Common color story (warm / cool / muted / bold)
4. Hero pattern that wins (cinematic / editorial / portrait / product / data)
5. Photography style (lifestyle / studio / candid / portrait / abstract)
6. Animation level (none / subtle / cinematic)
7. 3 specific signature techniques worth stealing

Output: `docs/RESEARCH-TASTE.md`. Recommend 1 design direction w/ palette + font pair from `design-tokens.md` table.
```

## Agent C — Keyword + EEAT + Schema

```
You are researching SEO + trust requirements for [NICHE] in [GEO].

Niche: [NICHE]
Geo: [GEO]

Capture:

1. **Keyword cluster** — primary (1) + secondary (5) + long-tail (10) per page
2. **Search intent** per cluster (informational / commercial / transactional)
3. **Schema markup needed:**
   - LocalBusiness (always for service area)
   - FAQPage (always)
   - Service / MedicalBusiness / LegalService (niche-specific)
   - Product (if applicable)
   - Review (if real testimonials)
4. **Trust signals niche expects:**
   - Licenses / certifications / reg #s
   - Years in business
   - Photos (real work / staff / facility)
   - Insurance
   - Press / awards / accreditations
5. **EEAT signals to weave in:**
   - Author byline + bio
   - Date published / updated
   - First-person voice OR named team
6. **2026 SEO threats per niche:**
   - SpamBrain (Mar 2026)
   - Scaled-Content-Abuse (Feb 2026)
   - Site-Reputation-Abuse (Mar 2024 → expanded 2026)

Output: `docs/RESEARCH-SEO.md`. Include 1 "must add" + 3 "skip these" rules.
```

## Synthesis

After all 3 return, write `docs/RESEARCH.md` synthesizing into 1 page:

```
# Research Synthesis — [Client] [Niche]

## Sameness Gap (from competitors)
[1 paragraph]

## Design Direction (from taste signals)
[Palette + font pair from design-tokens.md, 1 paragraph why]

## Conversion Wedge
[1 sentence: what no competitor does, that we will]

## SEO Stack
[Schema list + keyword cluster + trust signals to wire]

## Photo Strategy
[Real client / Unsplash niche-tagged / hybrid]

## Voice
[First-person / "we" / clinical / warm]
```

This synthesis = the brief for Phase 2 (design lock) + Phase 4 (build).
