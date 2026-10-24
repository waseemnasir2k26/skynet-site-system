# skynet-site-system

A website playbook for freelancers, agencies and AI coding agents: niche design tokens, a conversion funnel, a 3-variant demo pattern and a pitch template, written down from the sites SkynetLabs has built. Use it as a Claude Code skill or read it as a checklist.

- **8-phase build flow** from brief to shipped demo and pitch (`SKILL.md`).
- **17 niche design-token sets**: palette hexes and font pairs for wedding, medical, wellness, law, HVAC, dental, real estate, restaurant, beauty, photography, finance, SaaS and more (`design-tokens.md`).
- **Case studies** of the builds the rules came from, with stack and tokens per site (`case-studies.md`).
- **3-variant lock**: each demo ships Editorial, Cinematic and Bold versions behind a sticky switcher (`recipes/variant-switcher.md`, React and vanilla JS).
- **Pitch template and scope questions**: 5-8 questions per niche (`pitch-template.md`, `scope-questions.md`).
- **Research prompts**: three parallel agent prompts for competitor teardown, niche taste and SEO (`competitor-research-template.md`).

## Quickstart

As a Claude Code skill:

```bash
git clone https://github.com/waseemnasir2k26/skynet-site-system.git ~/.claude/skills/skynet-site
```

Then in Claude Code run `/skynet-site` and paste a client brief. Without Claude Code, open `SKILL.md` and follow the 8 phases top to bottom.

## The 8 phases

| Phase              | What                                                                                   |
| ------------------ | -------------------------------------------------------------------------------------- |
| 1 Inputs           | Brief, niche, client name, budget, timeline                                            |
| 2 Research         | Three parallel research agents                                                         |
| 3 Token lock       | Pick palette and fonts from the niche table, never defaults                            |
| 3.5 / 3.6 Variants | Editorial, Cinematic, Bold plus sticky top-right switcher                              |
| 4 Stack            | Static HTML, React + Vite, Next.js + R3F, or a WordPress demo first                    |
| 5 Build            | Hero, trust, services, about, process, testimonials, gallery, FAQ, lead magnet, footer |
| 6 Signatures       | 4-6 niche-fit premium touches                                                          |
| 7 Guardrails       | Lighthouse 90+, LCP 2.5s or less, 6 form fields or fewer                               |
| 8 Ship and pitch   | Repo, Vercel deploy, 5-8 scope questions                                               |

## Design tokens (first rows)

| Niche                    | Palette                                      | Display font       | Body    |
| ------------------------ | -------------------------------------------- | ------------------ | ------- |
| Wedding / luxury event   | Beige `#F2EBE0`, claret `#8B3A3A`, champagne | Instrument Serif   | Inter   |
| Medical / clinic         | Forest `#2D4A3E`, mint `#7EC8A0`             | Cormorant Garamond | Inter   |
| HVAC / plumbing / trades | Steel blue, safety orange                    | Manrope            | Inter   |
| Law firm                 | Oxblood `#7B1F2C`, brass `#B8924B`           | Lora               | Inter   |
| Finance / VC             | Obsidian, champagne gold `#D4AF37`           | Playfair Display   | DM Sans |

All 17 sets, with what to avoid for each, are in `design-tokens.md`.

## Hard rules (short list)

1. Build first, pitch second.
2. Three variants with a sticky switcher; remove the switcher once the client picks.
3. Tune everything to the niche.
4. Real photos, not placeholders.
5. Unique testimonials per niche, no invented metrics.
6. noindex speculative demos.
7. 5-8 scope questions, not 16.
8. Log which photos you have used so you do not repeat them.

The full list with reasoning is in `SKILL.md`.

## For you if

You build client sites on a deadline and want defaults that are already niche-appropriate, or you want your coding agent to stop picking the same generic palette every time.

## Status and limits

- It is a playbook, not a template or generator. There is no code to install beyond the switcher recipe.
- Rules and tokens come from SkynetLabs' own builds. They are opinions that worked for us, not benchmarks, and the figures quoted in the older docs (close rate, reply rate) have not been independently checked.
- Some case-study entries are speculative demos rather than paid client sites. `case-studies.md` lists which tier each belongs to.
- `case-studies.md` names a local folder as its data source. Ignore it.

## License

MIT, see [LICENSE](LICENSE).

---

Built by SkynetLabs. Contact: info@skynetjoe.com

Need this wired into your business? SkynetLabs builds voice agents, n8n back offices and sites that convert → https://skynetjoe.com
