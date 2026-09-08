# PROMPT — the brief this folder answers

This file exists so the build is reproducible. Part 1 is Oliver's brief exactly as it
was given, brackets and all. Part 2 is the same brief with every bracket filled in for
Ads Went Nuts, so it can be re-run without going back to anyone for the variables.

---

## Part 1 — Oliver's brief, verbatim

```
Build me a one-page VSL funnel for a [niche] AI and marketing agency. The page should have:
- A bold headline that highlights this offer: [your offer, example: get 10 new roofing leads in 30 days or you dont pay]
- A subheadline that speaks to the biggest pain point of [niche] and hints that this offer solves it
- A video placeholder in the center of the page
- 3 to 5 bullet points below the video showing what they will learn or get
- A single call-to-action button that says [book your call] linking to [your link or calendar]
- A short line of text below the button that removes risk, like a guarantee or a no pressure statement
Keep the design clean and minimal. Dark background, white text, one accent colour which is [your colour]. No navigation menu. No footer links. One goal only which is to get them to click the button.
```

---

## Part 2 — the same brief, filled in for Ads Went Nuts

```
Build me a one-page VSL funnel for a landscaping / lawn care AI and marketing agency.
The page should have:
- A bold headline that highlights this offer: 30 citas confirmadas en 30 dias para tu
  empresa de landscaping, garantizadas. (EN: 30 confirmed appointments in 30 days for
  your landscaping company, guaranteed.)
- A subheadline that speaks to the biggest pain point of landscaping / lawn care
  company owners -- being treated as a price quote by callers who vanish, and losing
  the job to whoever is cheapest -- and hints that this offer solves it
- A video placeholder in the center of the page
- 3 to 5 bullet points below the video showing what they will learn or get
- A single call-to-action button that says "Agenda tu llamada" / "Book your call"
  linking to https://calendly.com/connor-adswentnuts/30-citas-en-30-dias
- A short line of text below the button that removes risk, like a guarantee or a
  no pressure statement
Keep the design clean and minimal. Dark background, white text, one accent colour which
is #21C48C. No navigation menu. No footer links. One goal only which is to get them to
click the button.
```

### Variables

| Variable | Value |
| --- | --- |
| Niche | Landscaping / lawn care companies in the US |
| Offer | 30 citas confirmadas en 30 dias, garantizadas |
| Accent colour | `#21C48C` (the only accent — no gold, no amber, no yellow) |
| Calendar link | `https://calendly.com/connor-adswentnuts/30-citas-en-30-dias` |
| Brand | Ads Went Nuts |
| Legal entity | Ads Went Nuts es un nombre comercial de Connor Fleming (propietario unico). |
| Contact | (404) 276-6462 · connor@adswentnuts.com |
| Languages | Spanish (`/index.html`, primary) and English (`/en/index.html`) |

---

## Part 3 — the second guide: six conversion principles

Applied alongside Oliver's brief, not instead of it. Where they collide, the
resolutions are in `README.md` ("The two collisions").

```
1. Lead with the reader's problem, not the product. The first screen should make the
   reader feel understood before it sells anything.
2. Mirror the audience's actual language -- the raw words they use describing their own
   frustration, not corporate-speak. ("I'm tired of starting over every Monday" beats
   "Achieve your fitness goals with our proven system.")
3. One page, one goal, one CTA. Pages doing multiple things converted 40-60% worse.
4. Social proof placement beats the proof itself -- put it immediately after the biggest
   objection, not in a block at the bottom.
5. Headline formula: [End result the reader wants] + [Time frame] + [Without the thing
   they fear]. Showed up in 60%+ of top converters. E.g. "Get your first 100 customers
   in 30 days without spending a dollar on ads."
6. Nobody reads, they scan. Headings read in sequence (H1 -> H2 -> H2) must tell the
   whole story without a single paragraph being read.
```

**Principle 4 carries a hard constraint here.** Ads Went Nuts has no testimonials, no
case studies, no named clients, no results numbers and no client screenshots. None
exist. None may be invented, implied or paraphrased. The principle is applied as
*placement* of the proof that does exist — the guarantee, the niche exclusivity, and
the willingness to disqualify. See `README.md`, principle 4.

---

### Constraints layered on top of the brief

These are Connor's, not Oliver's. They are the reason the pages are not a bare reading
of the brief. Each one is justified in `README.md`.

1. Two pages: Spanish primary, English at `/en/`. The English page is written for a US
   landscaping owner, not translated from the Spanish.
2. A minimal legal strip stays: SMS consent language (Connor's A2P registration depends
   on it) and the trade-name disclosure. Plain small text, no links.
3. The results/screenshot disclaimer is dropped. These pages show no screenshots.
4. Never the word "leads" in either language. The unit is "citas confirmadas" /
   "confirmed appointments".
5. Exactly one anchor per page, and it is the CTA. No `<nav>`, no footer link list, and
   the logo is not a link.
6. No invented business facts: no prices, no ad-spend minimums, no client names, no
   testimonials, no result numbers, no case studies.
7. Zero emoji.
8. Design tokens come from the live page, not from taste. See README.
