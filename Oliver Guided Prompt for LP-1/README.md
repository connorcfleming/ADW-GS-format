# Oliver Guided Prompt for LP-1

The version of the landing page that actually answers Oliver's brief.

The long-form page at the repo root (`../index.html`) was built before the brief was
seen. It is a good page, but it is not the assignment: it has a sticky header with a
nav CTA, two embedded Calendly widgets, a screenshot gallery, a FAQ, a fit/anti-fit
section and a full footer with a link list. Oliver asked for a one-page VSL funnel with
one goal and one click. This folder is that page.

Two guides govern it:

1. **Oliver's brief** — the structure. Fidelity to it is the deliverable.
2. **The six principles** — a conversion guide applied on top. Where the two collide,
   the resolutions are written out below rather than picked silently.

```
Oliver Guided Prompt for LP-1/
├── README.md          this file
├── PROMPT.md          Oliver's brief verbatim, the filled-in version, the six principles
├── index.html         Spanish (primary)
├── en/index.html      English
└── .render-check/     Playwright screenshots at 375px and 1280px (build artifact)
```

Both HTML files are single self-contained files. All CSS is in one inline `<style>`
block, the logo is inlined as a base64 data URI, and the only external request is the
Inter webfont from Google Fonts (with a real system fallback stack, so the page is
readable if that request fails). No build step. No framework. No external JS.

---

## READ THIS BEFORE THE ENGLISH PAGE TAKES TRAFFIC

**The English SMS consent paragraph on `en/index.html` has NOT been checked against
Connor's registered A2P 10DLC campaign.** It is a faithful rendering of the approved
Spanish paragraph in standard US carrier phrasing, written for this build. The live
page has no English version to copy from, so there was nothing authoritative to lift.

**Connor must replace it with the exact text registered with the A2P campaign before
this page is put in front of traffic.** If the registered wording differs, the
registered wording wins. This is the single highest-risk item in this folder.

---

## Connor's deliberate calls — do not "fix" these

Six things on these pages look like mistakes against the two guides. They are not.
They are Connor's explicit instructions, recorded here so nobody quietly reverts them
in a later pass.

**1. The hero is the offer alone. The problem was moved below the video.**
His words: *"nothing before the VSL video"* and *"everything else you think will help
will come below the hero offer."* Above the video there is now only the brand mark and
the H1. The eyebrow `<p>`, the pain `<h2 class="pain">` and the subheadline
`<p class="sub">` were deleted as elements, not just emptied. The pain survives as the
first H2 under the video.

This **reverses principle 1** of the conversion guide, which asks the first screen to
lead with the reader's problem rather than the product. The page now leads with the
offer. That is the trade he chose, knowingly. If someone later "restores principle 1"
by moving the pain back above the video, they will have undone a user decision.

**2. The exclamation mark stays.**
`Guaranteed!` / `¡Garantizadas!`. The brand voice rules forbid exclamation marks
everywhere else in the copy, and this is the one documented exception. He wrote it that
way, so it ships. ES uses the feminine plural `Garantizadas` (agreeing with *citas*)
and opens with the inverted `¡`, matching the EN comma-then-guarantee shape. Do not
normalise either one to a full stop.

**3. The niche eyebrow is gone. The niche itself was put back into the mechanism H2.**
"Solo landscaping y lawn care" / "Landscaping and lawn care only" was the first line of
visible text and the page's only statement of niche exclusivity — one of the three real
proof assets listed under principle 4. The eyebrow element was deleted with the rest of
the pre-video stack and is **not** coming back.

For a short window the niche existed only in the `<title>` and meta description, where
no visitor reads it. **That gap is closed.** The niche now rides inside the mechanism
H2, which had the most slack of any element on the page:

> ES: "Cómo te llenamos el calendario **de landscaping**"
> EN: "How we fill your **landscaping** calendar"

That puts it back in the heading sequence, so a reader who scans only the headings still
learns the page is landscaping-only. It cost **one word in EN (5 → 6) and two in ES
(5 → 7)**, both inside the 9-word cap; it added no element and did not touch the hero.
Verified: `landscaping` now returns ≥1 match in the visible body of both pages.

The ES line is the live page's approved heading — "Cómo te llenamos el calendario" —
with "de landscaping" appended, so it is not a rewrite of approved copy. An earlier
draft read "Cómo llenamos tu calendario de landscaping", which dropped the dative `te`
and swapped `el` for `tu`; that lost the warmth the copy deck uses throughout and was
reverted to the approved construction.

The niche is still **not** the first thing on the page the way the eyebrow was. If
Connor wants it higher, the honest options are to put it back in the H1 (Alternative A
under principle 5 does exactly that) or to accept its current position.

**4. Pronoun rule: every "them"/"they" ties to the customer.**
His words: *"everything that mentions 'them' and 'they' needs to be tied to 'the
customer'."* The customer is named on first reference in a block; pronouns follow after
that. The full before/after table is under principle 2. The rule is not "say 'the
customer' in every clause" — it is that a reader never has to guess who "they" is.

**5. Three stacked ~20-word problem headings, and the 9-word cap is lifted for them.**
The single problem H2 under the video was replaced on 2026-09-08 (third pass) by three
H2s, one per problem: the quote that goes cold, the marketplaces that sell you phone
numbers and leave you the prospecting, and the phone nobody can answer. They run 20-24
words each, well over the 9-word `h2` cap that governs every other heading on the page.

**Connor chose this after being shown a layout preview of exactly how heavy three
stacked headings of that length would render.** He saw the weight and said ship it. The
cap is lifted **for these three elements only**; the bullets, the mechanism H2, the
objection H2 and the risk-reversal line are all still capped and still inside their
caps. Do not "bring these back under the cap" in a later pass — that would be undoing a
user decision made with the render in front of him.

The English is his own wording, shipped **verbatim**, punctuation included. The only
change made to it was the source typo `cusotmer` → `customer`. If a line reads
awkwardly, that is his voice, not an error to fix.

**6. `Angie's List` is named on the page, at Connor's explicit direction.**
Naming a specific competitor by brand is a real decision with real trade-offs, so it is
recorded here rather than left to look accidental. It stays in English on the Spanish
page: it is a US brand name, not a phrase to translate. He asked for it by name.

---

## Where it was built from

- **Foundation / source of truth:** the live repo,
  `github.com/connorcfleming/adswentnuts-landingpage-30citasen30dias`. Design tokens,
  brand voice and approved Spanish copy all come from its `index.html`. The logo data
  URI is its `assets/logo.b64.txt`, inlined the same way the live page inlines it.
- **Also read (never written to):** `../COPY-DECK.md` and `../GHL-BUILD-GUIDE.md`.
- **Warning about this local repo:** the `Landing Page -1` git repo you are standing in
  points at `github.com/connorcfleming/30-citas-en-30-d-as.git`, which is a
  **different, older** GitHub repo than the live one above. Do not assume pushing from
  here updates the live page. Check `git remote -v` before pushing anything.

### Design tokens (taken from the live page, unchanged)

| Token | Value | Use here |
| --- | --- | --- |
| `--ink` | `#0B0B0B` | page background |
| `--ink-2` | `#141414` | video placeholder surface |
| `--paper` | `#FFFFFF` | focus ring |
| `--accent` | `#21C48C` | button fill, bullet checkmarks, mechanism-H2 underline, headline highlight |
| `--accent-dark` | `#189E70` | button hover |
| `--on-dark` | `#FFFFFF` | body text, all headings |
| `--on-dark-muted` | `#A8AFB4` | secondary text |
| `--line-dark` | `rgba(255,255,255,.12)` | hairlines and the video border |

Those eight values are the complete colour set. Nothing else appears in either file.

**Contrast.** `#21C48C` on white is about 1.9:1 and fails AA, which is why the live
page forbids accent-as-text on light bands. This page has no light bands — the whole
document is `#0B0B0B` — so accent text is safe here. Measured:

- `#21C48C` on `#0B0B0B` → **8.75:1**
- `#FFFFFF` on `#0B0B0B` → **19.68:1**
- `#A8AFB4` on `#0B0B0B` → **8.86:1** (secondary text)
- `#A8AFB4` on `#141414` → **8.30:1** (video label)
- `#0B0B0B` on `#21C48C` → **8.75:1** (button)
- `#0B0B0B` on `#189E70` → **5.78:1** (button hover)

---

## Guide 1 — mapping: Oliver's requirements → where they are satisfied

| # | Oliver asked for | Where it lives | Notes |
| --- | --- | --- | --- |
| 1 | One-page VSL funnel for a [niche] agency | Whole file, single `<main class="wrap">` | Landscaping / lawn care. The niche eyebrow was **deleted** on 2026-09-08 (second pass) at Connor's request — the hero is the offer alone. The niche was then folded into the mechanism H2 ("How we fill your landscaping calendar" / "Cómo te llenamos el calendario de landscaping") so it stays visible and in the scan path. See "Connor's deliberate calls" below. |
| 2 | Bold headline highlighting the offer | `<h1>` | Rewritten to the principle-5 formula — see "Guide 2, principle 5" and the labelled alternative below. The number phrase is wrapped in `<span class="hl">` and rendered in the accent, same treatment as the live hero. |
| 3 | Subheadline: biggest pain point + hints the offer solves it | `<h2>` immediately **below** the video | The `<p class="sub">` and the `<h2 class="pain">` above the video were both **deleted** on 2026-09-08 (second pass). Connor asked for nothing between the brand mark and the video. The pain survives below the video — as a single H2 in the second pass, and as **three stacked H2s** in the third (2026-09-08). See principle 1 and "Connor's deliberate calls". |
| 4 | Video placeholder in the centre of the page | `<div class="booking calendly-inline-widget">` | **Replaced by the Calendly embed on 2026-09-08 (fourth pass), on explicit instruction.** The slot is the same one Oliver specified for the VSL; what sits in it is now the booking calendar. See "The Calendly embed" below. The old `.video` markup and its `VIDEO_URL` script are gone; the `.video` / `.play` / `.video-label` CSS is left orphaned, on the same grounds as `.eyebrow` and `h2.pain`, and is the revert path if the VSL comes back. |
| 5 | 3 to 5 bullets showing what they get | `<ul class="points">` | **4 bullets**, each a single bold fragment — the benefit, not the explanation. Cut from 5 full-sentence bullets in the 2026-09-08 pass; the definition-of-a-confirmed-appointment bullet was dropped (see the word-count table under principle 6). ES bullet 2 opens "Clientes que..." rather than "Los que..." under the pronoun rule below. Bullet 2 is now the only place the screening idea is stated, since "qualified jobs only" never reached the shipped H1. |
| 6 | A single CTA button linking to the calendar | `<a class="cta">` | **Exactly one anchor exists in each document.** ES "Agenda tu llamada", EN "Book your call". Both point at `https://calendly.com/connor-adswentnuts/30-citas-en-30-dias`, byte-exact, with `target="_blank" rel="noopener"`. |
| 7 | Short risk-removal line below the button | `<p class="reversal">` | Directly under the button, as Oliver requires, and directly after the objection H2, as principle 4 requires. See the collision resolution below. |
| 8 | Clean and minimal, dark bg, white text, one accent | inline `<style>` | Single centred column, one breakpoint at 480px, `background-color` and `color` set explicitly on `body` so the page does not depend on browser or OS theme. |
| 9 | No navigation menu | — | Zero `<nav>` elements. No header bar at all. **The logo is an `<img>`, not a link.** |
| 10 | No footer links | `<div class="legal">` | No `<footer>` element and no link list. The legal strip is plain small text with zero anchors — phone and email are text, not `tel:`/`mailto:`. |
| 11 | One goal only: get the click | — | One anchor, one destination, no secondary action, no anchor jumps. **The "no embedded widget" half of this no longer holds**: the Calendly calendar was embedded in the hero on 2026-09-08 (fourth pass) on explicit instruction. The goal is unchanged and the destination is unchanged — the embed and the button point at the same event — but the booking now starts on the page instead of after a click. |

### The Calendly embed

**The VSL slot holds the booking calendar now.** Swapped on 2026-09-08 (fourth pass) on
explicit instruction. The `VIDEO_URL` single-point-of-change constant and the script that
built the video iframe are **gone** — there is no video on these pages any more.

```html
<div class="booking calendly-inline-widget"
     data-url="https://calendly.com/connor-adswentnuts/30-citas-en-30-dias?background_color=0B0B0B&amp;text_color=FFFFFF&amp;primary_color=21C48C"
     style="min-width:320px"></div>
<script src="https://assets.calendly.com/assets/external/widget.js" async></script>
```

**The `data-url` is the same link as the CTA button**, deliberately, so the calendar and
the button cannot drift onto different events. That does mean the single point of change
is now *two* points: change the `data-url` here **and** the `href` on the button. Both
pages, ES and EN, point at the same Spanish-slugged event, which is how the CTA already
worked before this change.

**The three colour parameters are the page palette** (`background_color`, `text_color`,
`primary_color`) minus the `#`, which is the shape Calendly expects. Without them the
calendar lands as a white block on a black page. Verified in the browser: the widget
renders dark with the accent green. A thin white gutter from Calendly's own page
background is still visible around the card; that is inside the iframe and not styleable
from here.

**`widget.js` is the only external resource on either page.** Everything else, the logo
included, is inlined. It is needed because the embed will not size itself without it, and
it is `async` so it never blocks render. If it fails to load, the div is simply empty and
the button at the foot of the page is still the route to the call.

**Calendly's own `widget.css` is deliberately *not* loaded**, to avoid a second external
request. That stylesheet is what normally gives the iframe its height, so the page
supplies the two rules itself:

```css
.booking{
  position:relative; left:50%; transform:translateX(-50%);
  width:min(1080px,calc(100vw - 32px));   /* breaks out of --measure on purpose */
  height:700px;                           /* not min-height: % height must resolve */
}
.booking iframe{width:100%;height:100%}
```

Without them the iframe sits at the default 150px and all you see is a white band — that
was the first render of this change, and it is the failure mode to check for if the box
ever looks wrong. Measured after the fix: the iframe renders at 698px and the calendar
appears in full. `widget.css` also hides Calendly's spinner (which stays in the DOM
forever rather than being removed), so `.booking .calendly-spinner` is positioned behind
the iframe here to do the same job.

**The block is 1080px wide and breaks out of the page measure. That width is load-bearing,
not decoration.** Calendly picks its own layout from the width it is handed, and the
layout is inside the iframe, so it cannot be set from here — only the width can. Measured
on this event:

| Width given to the widget | What Calendly renders |
| --- | --- |
| 736px (`--measure`, the page's own width) | Stacked. Description on top, **truncated behind a "SHOW MORE" link**, calendar below. |
| 900px | Still stacked, still truncated. |
| 1000px | Still stacked, still truncated. |
| **1080px** | **Two columns. Full description in a left panel, calendar on the right, nothing truncated.** |

So the two-column breakpoint sits between 1000px and 1080px, and 1080 is the shipped
value — chosen with margin above the breakpoint rather than right on it, because Calendly
owns that number and can move it. **Do not narrow `.booking` back to the page measure:
that silently re-truncates the description**, which is the exact thing this width exists to
prevent. This is the only block on either page that leaves `--measure`; everything else
still sits inside 46rem. `body` already carries `overflow-x:hidden`, so the `100vw` cap
cannot produce a horizontal scrollbar (verified: `body.scrollWidth` 1521 at a 1536px
viewport).

**700px tall desktop, 1000px at ≤640px.** 700 is Calendly's documented minimum and it fits
the two-column card without internal scrolling. 620px was tried and clips the card, so do
not trim it. Below 640px the width collapses to the viewport, Calendly stacks the layout
anyway, and the taller box absorbs it.

**Known cosmetic limitation:** in two-column mode Calendly centres a fixed-width dark card
inside its own white page background, so a white frame is visible around the card on the
black page. That background is inside the iframe and `background_color` does not reach it.
Narrowing the box to hide the frame drops it under the breakpoint and re-truncates the
description, so the frame is the accepted cost of the readable description. A crop — an
outer `overflow:hidden` wrapper narrower than a negatively-offset iframe — would hide it,
but the card changes height once a date is picked and the time slots appear, so cropping
risks clipping the confirm step. Not done.

---

## Guide 2 — the six principles, and how each is satisfied

### Principle 1 — lead with the reader's problem, not the product

**This principle is now deliberately reversed at the top of the page, on Connor's
explicit instruction.** The first screen is: brand mark → offer H1 → video. Nothing
else. The reader meets the offer first, not the problem.

The problem is not deleted — it is relocated. It is the **first thing under the video**.
As of the 2026-09-08 third pass it is no longer one H2 but **three stacked H2s**, one
per problem Connor named:

> EN: "Once customers get a quote, they go dark, and it's up to you to follow up, when you're on the jobsite"
> EN: "Angie's List and big marketing companies give you numbers to call, but nothing is automated, and you have to do the prospecting"
> EN: "Your customer service representative is either you, someone on the jobsite, or simply a human that can't answer every call"

> ES: "El dueño de casa recibe el estimado, se desaparece, y buscarlo otra vez te toca a ti, cuando andas en la chamba."
> ES: "Angie's List y las agencias de marketing grandes te dan puros números, pero nada es automático, y buscar clientes te lo dejan a ti."
> ES: "Quien contesta el teléfono eres tú, alguien de la cuadrilla, o simplemente una persona que no da abasto con todas las llamadas."

The single line it replaced — ES "Le das el precio al cliente y desaparece." / EN "You
give the customer a price. They ghost you." — is retired, not lost: its beat is the
first of the three.

So the page still makes the reader feel understood; it just does it after the video
rather than before it. Connor's words were *"nothing before the VSL video"* and
*"everything else you think will help will come below the hero offer."* Those two
instructions together only resolve one way: hero → video → everything else.

**Do not "fix" this by moving the pain back above the video.** It is a user decision,
recorded under "Connor's deliberate calls" below.

### Principle 2 — mirror the audience's actual language

Spanish reuses the approved copy-deck phrasings verbatim or near-verbatim: "le das el
precio al cliente y desaparece", "clientes que solo preguntan precio", "citas
confirmadas", "te decimos derecho".

English is written, not translated, in the words a US landscaping owner uses: *they
ghost you*, *price shoppers*, *we tell you straight*. No "leverage", no "solutions",
no "elevate". The three problem H2s added on 2026-09-08 (third pass) are **Connor's own
words, shipped verbatim** — the only edit was the source typo `cusotmer` → `customer`.
They are not tightened, not rewritten, not word-capped.

The three Spanish problem H2s were **written, not translated**: they mirror the meaning
and the beats of Connor's English, not its syntax. They reuse the deck's motifs —
`dueño de casa`, `estimado`, `se desaparece`, `te toca a ti`, `cuadrilla` — and add
`la chamba`, which is the register the deck is written in but is **not** attested
anywhere in `../COPY-DECK.md` or `../index.html`; it is the one new word in the set.
`Angie's List` stays in English: it is a US brand name.

The 2026-09-08 second pass removed three more motifs with the elements that carried
them: "sin competir contra el más barato" and "getting underbid by the cheapest guy"
(the old H1 without-clause), "te pide que le bajes" / "ask you to come down" (the
deleted subheadline), and "ni uno más" / "not a minute more" (the 30-minute ask, see
below). All three still live on the long-form page at `../index.html`.

**The 30-minute ask is gone from both pages entirely.** Standing instruction from
Connor: remove every reference to the call length, and do not replace it with anything.
Verified: zero matches for `30 min`, `minuto`, `minute` and `treinta` in either file.
The offer strings `30 citas confirmadas en 30 días` and `30 confirmed appointments in
30 days` are appointments and days, not minutes, and are untouched.

### Pronoun rule — every "them"/"they" ties to the customer

Connor's instruction: *"everything that mentions 'them' and 'they' needs to be tied to
'the customer'."* The reader must never have to guess who "they" is. The customer is
named on first reference in a block; pronouns may follow naturally after that. Register
is unchanged — `tú` for the reader, `el cliente` for the homeowner.

| Was | Now | Why |
| --- | --- | --- |
| ES `Contestas, les das el precio y la persona desaparece.` | `Le das el precio al cliente y desaparece.` *(retired in the third pass; replaced by problem H2 #1, which names `El dueño de casa` and lets `se desaparece` take it as its implicit subject)* | `les` and `la persona` both floated. `al cliente` names the referent; the implicit subject of `desaparece` is then unambiguous. |
| ES `Los que solo preguntan precio, filtrados antes.` | `Clientes que solo preguntan precio, filtrados antes.` | `Los que` was a bare relative with no antecedent on the page. |
| EN `You give them a number and they ghost you.` | `You give the customer a price. They ghost you.` *(retired in the third pass; replaced by problem H2 #1, where `they` follows `customers` four words later)* | `them` had no antecedent. `the customer` is named, then `They` follows it directly. |
| EN `Price shoppers screened out before they reach you.` | *unchanged* | `they` refers to "Price shoppers", named four words earlier in the same sentence. Nothing floats, so nothing was changed. There is now one other surviving ` they ` — problem H2 #1, "Once customers get a quote, **they** go dark", where `customers` is named four words earlier in the same clause. Both satisfy the rule. |

The 2026-09-08 cut removed several of these motifs along with the sentences that
carried them — "regateando por teléfono", "en temporada baja el teléfono deja de sonar",
"el que solo anda curioseando precios", "sin letras chiquitas", "te decimos derecho",
*tire kickers*, *chasing referrals*, *the phone goes quiet in the off-season*. They all
still live on the long-form page at `../index.html`.

**Never "leads", in either language.** The unit is "citas confirmadas" / "confirmed
appointments". Verified: 0 occurrences in both pages.

### Principle 3 — one page, one goal, one CTA

Exactly one `<a>` element per page, and it is the CTA. No nav, no footer links, no
`tel:`/`mailto:`, no anchor jumps, no embedded Calendly widget. Verified by count.

### Principle 4 — social proof placement — HANDLED BY PLACEMENT, BECAUSE THERE IS NO SOCIAL PROOF

**Ads Went Nuts has no testimonials, no case studies, no named clients, no results
numbers, no client screenshots and no logo strip. None exist. Nothing of the kind is
invented, implied or paraphrased anywhere on these pages.** No "trusted by", no client
count, no star rating, no quote, no past-performance number. There is nothing to cite,
so nothing is cited.

**This is a deliberate honesty constraint, not an oversight.** The live page already
treats radical transparency as its chosen substitute for social proof — it publishes
the guarantee conditions in full instead of publishing praise. These pages do the same.

What the principle actually describes is a **placement** mechanism: proof lands
immediately after the biggest objection, not in a block at the bottom. That mechanism
is applied to the proof assets that genuinely exist:

- **the guarantee** (a number and a date, publicly stated),
- **niche exclusivity** — the eyebrow that used to carry it was deleted, so it was folded into the mechanism H2 instead ("How we fill your **landscaping** calendar" / "Cómo te llenamos el calendario **de landscaping**"). Still on the page, still in the scan path, one word deeper down than before,
- **willingness to disqualify** — now carried by the objection H2 itself: "Te decimos
  derecho si no encajas." The first pass of the 2026-09-08 cut lost this line and put
  "decide tú" in its place; it was restored by rewriting the H2 rather than by adding a
  sentence, so it costs nothing against the word cap. The approved motif "te decimos
  derecho" is intact.

The biggest objection to a guaranteed-number offer is *this sounds too good to be
true*. So it is said out loud, in an H2, immediately before the CTA:

> ES: "Suena demasiado bueno. Te decimos derecho si no encajas."
> EN: "Too good to be true? We tell you straight."

The heading does two jobs in nine words: it says the objection out loud, and it answers
it with the one piece of proof that genuinely exists — the willingness to turn the
reader away. The 30-minute ask that used to sit one line down has since been removed
from the page entirely.

The risk-reversal line then lands directly after it (one button in between, because
Oliver mandates the risk line sit under the button). It is not a detached footnote at
the bottom of the page; it is the answer to the sentence directly above it.

### Principle 5 — headline formula

`[End result] + [Time frame] + [Without the thing they fear]`

**The shipped H1 does not carry a without-clause.** Connor chose the offer alone, so
the formula is satisfied on its first two terms only. This is his call, not an
oversight — the without-clause versions are preserved below so one can be swapped back
in a single edit.

| | Headline |
| --- | --- |
| **ES (shipped)** | **30 citas confirmadas** *(end result)* **en 30 días** *(time frame)*, **¡Garantizadas!** |
| **EN (shipped)** | **30 confirmed appointments** *(end result)* **in 30 days** *(time frame)*, **Guaranteed!** |

**The exclamation mark is Connor's own wording and it ships.** The brand voice rules
otherwise forbid exclamation marks anywhere in the copy; this is the single documented
exception, and it exists because he wrote it that way. ES uses `¡Garantizadas!` —
feminine plural, agreeing with *citas*, and opening with the inverted `¡` — matching
the EN comma-then-guarantee shape. Do not "normalise" either one.

The niche is no longer named **in the hero**: "para tu empresa de landscaping" was
dropped from the H1 earlier, and the eyebrow that had been carrying it was deleted in
the second 2026-09-08 pass. It was then folded into the mechanism H2 so it stays in the
scan path — see "Connor's deliberate calls", item 3. Restoring Alternative A below would
put it back in the H1 itself.

#### H1 ALTERNATIVES — kept, not discarded

Two earlier H1s are preserved so either can be swapped back in one edit:

> **Alternative A (the live page's H1, still valid):**
> ES — "30 citas confirmadas en 30 días para tu empresa de landscaping. Garantizadas."
> EN — "30 confirmed appointments in 30 days for your landscaping company. Guaranteed."

> **Alternative B (the without-clause version, shipped until 2026-09-08):**
> ES — "30 citas confirmadas en 30 días, sin competir contra el más barato. Garantizadas."
> EN — "30 confirmed appointments in 30 days, without getting underbid by the cheapest guy. Guaranteed."

Alternative B is the only one of the three that satisfies principle 5 in full. It was
replaced on Connor's instruction. It also wrapped to **four lines** at 1280px and
orphaned "guy. Guaranteed." on a line of its own; the shipped H1 wraps to two. If B is
ever restored, re-check that wrap.

Nothing else on either page depends on the headline wording.

#### H1 ALTERNATIVE — Connor's choice, not discarded

The live page's current H1 is preserved here so it can be swapped back in one edit:

> **Alternative A (the live page's H1, still valid):**
> ES — "30 citas confirmadas en 30 días para tu empresa de landscaping. Garantizadas."
> EN — "30 confirmed appointments in 30 days for your landscaping company. Guaranteed."

Alternative A is end-result + time frame with **no without-clause**, which is why it
was not shipped here — but it is shorter, it names the niche in the H1 itself, and it
is the version already approved and live. If Connor prefers it, replace the `<h1>`
contents on both pages; nothing else on the page depends on the headline wording.

### Principle 6 — nobody reads, they scan

Headings in document order, extracted programmatically from the rendered DOM, plus the
button text. This is the pitch a scanner gets without reading a single paragraph:

**Spanish (`index.html`)**

```
H1:  30 citas confirmadas en 30 días, ¡Garantizadas!
H2:  El dueño de casa recibe el estimado, se desaparece, y buscarlo otra vez te toca a ti, cuando andas en la chamba.
H2:  Angie's List y las agencias de marketing grandes te dan puros números, pero nada es automático, y buscar clientes te lo dejan a ti.
H2:  Quien contesta el teléfono eres tú, alguien de la cuadrilla, o simplemente una persona que no da abasto con todas las llamadas.
H2:  Cómo te llenamos el calendario de landscaping
H2:  Suena demasiado bueno. Te decimos derecho si no encajas.
CTA: Agenda tu llamada
```

**English (`en/index.html`)**

```
H1:  30 confirmed appointments in 30 days, Guaranteed!
H2:  Once customers get a quote, they go dark, and it's up to you to follow up, when you're on the jobsite
H2:  Angie's List and big marketing companies give you numbers to call, but nothing is automated, and you have to do the prospecting
H2:  Your customer service representative is either you, someone on the jobsite, or simply a human that can't answer every call
H2:  How we fill your landscaping calendar
H2:  Too good to be true? We tell you straight.
CTA: Book your call
```

Read in order that is: the offer → the three problems, in the owner's own words → the
mechanism **and the niche** → the objection and the ask → the click. Six headings
(1 × `h1`, 5 × `h2`), no `<h3>`, no skipped levels. The mechanism H2 carries the word "landscaping" because the eyebrow that
used to carry it was deleted; that heading is now the only place a scanner learns the
page is landscaping-only.

Note the change of shape from the first 2026-09-08 build: **the H1 is now the only text
above the video.** The first H2 no longer sits next to the H1 in the hero; it is the
first thing below the video. The eyebrow `<p>` that used to open the page has been
deleted outright, so no visible text precedes the H1 except the brand wordmark.

The four bullets are fragments, not sentences — the benefit, with no explanation under
it. The explanation is what the call is for.

```
Tus anuncios, solo en las ciudades donde trabajas. / Your ads, only where you want to work.
Clientes que solo preguntan precio, filtrados antes. / Price shoppers screened out before they reach you.
La cita confirmada, ya en tu calendario.           / The confirmed appointment, already on your calendar.
Optimización semanal: más presupuesto a lo que funciona. / Week-by-week optimization: more budget on what works.
```

#### The 2026-09-08 cut — word counts before and after

The first build satisfied every other principle and then violated this one: 421 / 439
visible words, including a 42/43-word bullet that defined "cita confirmada" in a full
paragraph. Nobody scans a 42-word bullet. The copy was cut by roughly two thirds against
fixed ceilings. Counts are per element from the rendered DOM, whitespace-split.

Four states are shown: the first build, the first 2026-09-08 cut, the second 2026-09-08
pass (Connor's hero rewrite), and the third 2026-09-08 pass (the three problem
headings), which is what ships. Counts are per element from the rendered DOM,
whitespace-split.

| Element | Cap | ES v1 | ES cut | ES p2 | **ES now** | EN v1 | EN cut | EN p2 | **EN now** |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Brand wordmark | — | 3 | 3 | 3 | **3** | 3 | 3 | 3 | **3** |
| Eyebrow | 6 | 7 | 5 | *deleted* | *deleted* | 5 | 5 | *deleted* | *deleted* |
| H1 | 14 | 13 | 13 | 7 | **7** | 16 | 14 | 7 | **7** |
| Subheadline | 18 | 51 | 16 | *deleted* | *deleted* | 64 | 17 | *deleted* | *deleted* |
| Video label | — | 7 | 4 | 4 | **4** | 7 | 5 | 5 | **5** |
| H2 #1 (problem — the quote goes cold) | **cap lifted** | 9 | 9 | 8 | **22** | 9 | 9 | 9 | **21** |
| H2 #2 (problem — marketplaces sell numbers) | **cap lifted** | — | — | — | **24** | — | — | — | **22** |
| H2 #3 (problem — nobody answers the phone) | **cap lifted** | — | — | — | **22** | — | — | — | **20** |
| H2 #4 (the mechanism + niche) | 9 | 5 | 5 | 7 | **7** | 5 | 5 | 6 | **6** |
| Bullet 1 | 9 | 34 | 8 | 8 | **8** | 32 | 8 | 8 | **8** |
| Bullet 2 | 9 | 32 | 7 | 7 | **7** | 34 | 8 | 8 | **8** |
| Bullet 3 | 9 | 30 | 7 | 7 | **7** | 35 | 7 | 7 | **7** |
| Bullet 4 | 9 | 21 | 8 | 8 | **8** | 18 | 7 | 7 | **7** |
| Bullet 5 | — | 42 | *deleted* | *deleted* | *deleted* | 43 | *deleted* | *deleted* | *deleted* |
| H2 #5 (the objection) | 9 | 9 | 9 | 9 | **9** | 14 | 9 | 9 | **9** |
| CTA | 4 | 3 | 3 | 3 | **3** | 3 | 3 | 3 | **3** |
| Risk-reversal line | 18 | 70 | 16 | 11 | **11** | 76 | 15 | 9 | **9** |
| **Total, excluding the legal strip** | *see note* | **336** | 113 | 82 | **142** | **364** | 115 | 81 | **135** |
| Legal strip (exempt — compliance, not copy) | — | 83 | 83 | 83 | 83 | 73 | 73 | 73 | 73 |

**The 9-word `h2` cap does not apply to the three problem H2s, and the 120-word page
total no longer applies either.** Both were lifted by Connor, explicitly, for these
three elements only — see "Connor's deliberate calls", item 5. The three run 20-24 words
each. The page total went 82 → 142 (ES) and 81 → 135 (EN); +60 and +54 words, all of it
the three headings. Against the first build that is still ES −58% and EN −63%.

**Every other cap still stands and was re-verified after the change:** bullets ≤ 9
(ES 8/7/7/8, EN 8/8/7/7), mechanism H2 ≤ 9 (ES 7, EN 6), objection H2 ≤ 9 (both 9),
risk-reversal ≤ 18 (ES 11, EN 9), H1 ≤ 14 (both 7), CTA ≤ 4 (both 3). The legal strip is
untouched: the SMS consent paragraph and the trade-name disclosure are compliance text,
not copy, and are out of scope for any cut.

Note the H2 sequence renumbered twice. What used to be "H2 #1 (the pain)" sat above the
video; the same job is now done by **three** H2s below the video, still first in the
heading order after the H1. The mechanism H2 moved from #2 to #4 and the objection H2
from #3 to #5. Neither of their strings changed. The risk-reversal line dropped again (16→11 ES, 15→9 EN)
because the 30-minute sentence was removed with nothing put in its place.

What the cut cost, stated plainly rather than hidden: the off-season / seasonality pain
point, the haggling-all-day pain point, and the mechanism detail under each bullet. All
of it is still on the long-form page at `../index.html`, and the call is where it
belongs on a VSL funnel anyway.

One line was cut and then put back. The first pass lost the disqualification promise
("si no encajas, te lo decimos ahí mismo"), which is one of only three real proof assets
on a page with no social proof. It was restored **by swap, not by addition** — H2 #3 was
rewritten from "Dedícale 30 minutos y decide tú" to "Te decimos derecho si no encajas",
still nine words. The objection heading now answers itself. The 30-minute ask that had
moved into the risk-reversal copy was removed from both pages in the second 2026-09-08
pass and was not replaced.

The English H2 #3 carries the same motif ("we tell you straight") but not the explicit
"if you are not a fit" clause — English needs five words for "too good to be true" where
Spanish needs three, and both halves do not fit in nine. The disqualification is
implicit in English and explicit in Spanish.

---

## The two collisions, and how they were resolved

### Collision A — principle 1 (lead with the problem) vs Oliver (headline carries the offer)

Oliver's structure wins, because it is the assignment. The **H1 carries the offer**.

Originally the **subheadline carried the pain**, directly under the H1, which is where
both guides agree it should go. **Connor overruled that on 2026-09-08.** He asked for
nothing between the brand mark and the video, and for everything else to sit below the
hero offer. So the subheadline element is gone and the pain is now a single `<h2>`
immediately below the video.

The resolution therefore moved: the H1 carries the offer, the video carries the pitch,
and the **first heading under the video carries the pain**. Principle 1 is satisfied
later on the page than the guide intends, and that is a knowing trade. See "Connor's
deliberate calls".

### Collision B — principle 4 vs the fact that there is no social proof

Resolved in full under **principle 4** above. Short version: the principle's mechanism
is placement, so placement is what was applied — to the guarantee, the niche
exclusivity and the willingness to disqualify. **No proof was invented.**

---

## Deviations from the brief

### (a) A minimal legal strip stays, even though Oliver said "no footer links"

Not optional, and not really a deviation from the spirit of the instruction. Oliver
banned a **footer link list** — a secondary navigation surface that competes with the
CTA. What is at the bottom of these pages is not that. It has **zero anchors**: no
Privacy link, no Terms link, no SMS Program link, no phone or email link. It is four
short paragraphs of plain text.

Two of them cannot be removed:

1. **The SMS consent paragraph.** Connor's A2P 10DLC registration depends on this
   language being publicly visible on the page that collects contact information. The
   Spanish version is carried over word for word from the live page. (The English
   version is the flagged item at the top of this file.) Deleting it is a compliance
   problem, not a design choice.
2. **The trade-name (DBA) disclosure.** "Ads Went Nuts es un nombre comercial de Connor
   Fleming (propietario único)." Ads Went Nuts is not a registered entity; it is a sole
   proprietor's trade name, so the real name has to appear.

The contact line and the copyright line are the only two that are discretionary. They
are kept as plain text because a page that names a guarantee with no way to reach the
guarantor reads worse than it needs to, and both are one line each.

**Consequence:** because the strip has no anchors, the CTA is still the only clickable
thing on the page. That is the constraint Oliver actually cared about, and it holds.

### (b) The results/screenshot disclaimer is dropped

The live page carries this line in its footer:

> Las capturas de pantalla de este sitio son ejemplos de las plataformas de anuncios,
> no resultados de clientes de Ads Went Nuts; los resultados varían según el mercado,
> el presupuesto y cada negocio.

It is there because the live page shows four ad-dashboard screenshots. **These pages
show none.** Carrying the line over would produce a disclaimer that describes nothing
on the page — text pointing at an image that is not there. That is exactly the bug the
thank-you page already has, and it makes legal copy read as boilerplate nobody
maintains, which is the opposite of what a disclaimer is for.

So it is deliberately not here. **If anyone ever adds a screenshot, a result number, a
client name or a testimonial to these pages, that line has to come back with it.**

The bullet that spelled out what counts as a confirmed appointment used to carry the
honesty load here. It was cut on 2026-09-08 as a 42-word paragraph masquerading as a
bullet. The load now sits on the risk-reversal line, which says the guarantee has
conditions and that they are covered on the call — and on the long-form page, where the
full definition is still stated.

### (c) The guarantee: headline states the offer, the line under the button states the terms

The offer is real and Oliver's example format is "get X or you don't pay", so the
number belongs in the headline. But the live page never states the number without also
showing four client-side conditions next to it: answer the same day, show up to
estimates, keep the agreed ad spend running the full 30 days (if it is paused or
lowered, the clock stops), and cover the service area. On top of that, three guarantee
clauses are still flagged in `../COPY-DECK.md` as awaiting sign-off against the signed
contract.

A bare, unconditioned "30 or you don't pay" on a one-page funnel with no conditions
visible would overstate the actual terms. A one-page funnel also cannot carry four
conditions and a remedy paragraph without ceasing to be a one-page funnel.

**Resolution:**

- The `<h1>` carries the offer and the word "Garantizadas" / "Guaranteed".
- The line under the button says the guarantee has conditions and says they are
  explained on the call: "Gratis, sin compromiso. Las condiciones de la garantía, en la
  llamada." / "Free, no obligation. Guarantee conditions covered on the call."
  Shortened on 2026-09-08 from 70/76 words to 16/15, then to **11/9** when the
  "30 minutos, ni uno más." / "30 minutes, not a minute more." sentence was removed on
  standing instruction. Nothing was added in its place. It acknowledges exactly what it
  acknowledged before, in fewer words, and still promises nothing the long-form page
  does not. The disqualification promise that used to sit in this line now sits in the
  H2 directly above the button. **Side effect worth knowing:** the removed sentence was
  the only `<strong>` in this paragraph, so the risk line now has no bold emphasis at
  all. The `.reversal strong` CSS rule is retained but currently unused.
- **No condition is invented**, and **the remedy is not stated** — nothing here
  promises anything the live page does not, and nothing contradicts the live page's
  remedy wording. The remedy is stated in full on the live page; this page points at
  the call rather than paraphrasing it into something a dispute could turn on.

This is the one place where Oliver's literal example ("or you dont pay") is not
followed to the letter. It is followed in structure — offer in the headline, risk
removed under the button — but not in wording, because the wording would not be true as
written.

### (d) Headings were added (`h2` ×5 per page)

Oliver's list does not mention headings, and Oliver forbids a **nav menu** and **footer
links** — not headings. Principle 6 requires a scannable heading sequence, which one
lone `<h1>` cannot provide. Five `<h2>`s: three problems, the mechanism, the objection.
They are scan labels, not new sections; they add no links, no navigation and no second
goal. The full sequence is printed under principle 6 above.

All five sit **below** the video. The pain H2 used to sit in the hero with
`class="pain"` (which zeroes its top margin so it hugs the H1); the relocated ones are
plain `<h2>`s so they pick up the normal section spacing instead. **No CSS was changed
to achieve any of this.** The three problem headings still carry no class and no bespoke
sizing or spacing. The `<style>` block stayed byte-identical to the pre-change file
until the 2026-09-08 marker/underline pass (documented below) — that pass is the only
CSS ever added here, and it touched nothing the three problem headings inherit.

**The consequence, stated plainly, because it is the weakest thing about the rendered
page.** There are now five `<h2>`s in a row below the video at identical size, weight
and colour (1280px: 24px / 800 / `#FFFFFF`; 375px: 19px / 800 / `#FFFFFF`), and the
vertical gutter is identical between every pair of them and between the video and the
first one — 52px at 1280, 34px at 375. Nothing in the layout says where the problems
stop and the mechanism starts.

Measured at 1280px: the three problem headings render at 3 lines each and the run from
the top of problem H2 #1 to the bottom of the mechanism H2 is a continuous **456px of
centred bold white text**. At 375px the problem headings render at 4 lines each (EN #1
is 3), the run is 411px (EN) / 435px (ES), and the 34px gutter is only ~1.4 line-heights
— so the three read closer to one twelve-line bold paragraph than to three separate
statements. The mechanism H2, at 1 line (1280) or 2 lines (375), is the *shortest* thing
in that run and therefore reads as subordinate to the problems above it, which inverts
the intended hierarchy. Every measurement in this paragraph is still true after the
accent underline was added — see "What the underline did and did not fix" below.

Compounding it: `.points strong` is also 700-weight white, so at 375px the bold white
run effectively continues through all four bullets down to the objection H2. Between the
video and the CTA there is almost no typographic relief except the green bullet
checkmarks and the left-alignment of the list.

This is the obvious candidate if a CSS pass is ever authorised — a smaller/lighter
treatment for the three problems, or extra top margin on the mechanism H2, would fix it
without touching a word of copy. **That pass has NOT been authorised.** CSS was unfrozen
on 2026-09-08 for exactly two cosmetic changes and nothing else; type sizes, weights,
colours and the 52px / 34px gutters are all still as measured above.

Orphaned CSS: `.eyebrow`, `.sub` and `h2.pain` rules all remain in the `<style>` block
with no element left to match them. They were **not** deleted — they have never been in
scope for any authorised change, and removing them has not been asked for.

#### The 2026-09-08 marker/underline pass — the only CSS ever added

Three changes. The first two are both `#21C48C` and introduced no new hex. The third
replaced the markers from this same pass with emoji, which puts colour on the page that
the palette does not control — see below.

**1. Bullet markers are checkmarks, not squares.** `.points li::before` changed from a
12px rounded square (`background:var(--accent)`) to `content:"✓"` — U+2713 CHECK MARK —
in `color:var(--accent)`. The character lives in the `<style>` block, **not in the
HTML**, so it never enters `textContent`: bullet word counts and text extraction are
unchanged (verified — `body.innerText` is byte-identical pre→post on both pages). A
checkmark rather than an invented glyph because the live long-form page already uses
green checkmarks for its `Sí es para ti si...` list, so it is an existing brand element,
and because the four bullets are what-you-get statements. The marker sits at `top:0`
with the inherited `line-height:1.6`, so it shares a line box with the first line of
each bullet and stays baseline-aligned when a bullet wraps to two lines at 375px.

> **Swapping the marker.** Change the single character in `content:"✓"`. Two alternates
> that need no other CSS edit: `▸` (U+25B8, small right triangle) or `→` (U+2192,
> arrow). `▸` is category `So` and would have to be added to the emoji allow-list
> below; `→` is category `Sm` and does not trip the sweep at all.

**2. The mechanism H2 is underlined in the accent.** It carries a real class,
`h2.mechanism`, deliberately **not** a positional selector like `h2:nth-of-type(4)`,
which would break silently if the headings were ever reordered:

```css
h2.mechanism{
  text-decoration:underline;
  text-decoration-color:var(--accent);
  text-underline-offset:6px;
}
```

`text-decoration` was chosen over a `border-bottom` on an `inline-block` because at
375px this heading wraps to two lines in **both** languages (measured): an underline
follows each line, whereas a border draws one rule at the width of the box. The
`6px` offset keeps the rule clear of the descenders in "your landscaping" /
"llenamos". The heading text stays `#FFFFFF`; only the rule is accent. The other four
`<h2>`s compute `text-decoration-line: none` and were not touched.

#### What the underline did and did not fix

It is a real improvement and it is **not** a fix for the hierarchy problem above. The
mechanism H2 now carries a rule none of the other four has — the three problem headings
are marked with a leading emoji instead — so it is *distinguishable* from them and the
eye stops there. But it is still 24px / 800 /
`#FFFFFF` with the same 52px gutter as everything around it, so it still sits in the
same visual tier — it now reads as an *underlined caption* rather than as the page's
pivot from problem to mechanism. Promoting it properly still needs the size / weight /
spacing pass, which remains unauthorised.

**3. The three problem H2s each carry an emoji marker, to the left of the text.** One
emoji each, inline before the first line of the heading:

| Codepoint | Char | Class | The problem it marks |
| --- | --- | --- | --- |
| `U+23F0` | ⏰ | `h2.problem-ghost` | Alarm clock — the time that goes into chasing a homeowner who went dark. |
| `U+1F916` | 🤖 | `h2.problem-manual` | Robot — the automation that is not there. |
| `U+1F4DF` | 📟 | `h2.problem-phone` | Pager — the calls nobody gets to. |

**This reverses the no-emoji rule, deliberately.** It was asked for explicitly, after the
first version of these markers shipped as monochrome maths symbols (`↛` U+219B, `⊘` U+2298,
`∄` U+2204) chosen specifically to stay in category `Sm` and leave the sweep alone. Those
are gone. All three replacements are pictographic: `U+23F0` sits in `U+2300–2400` and the
other two in `U+1F000–1FAFF`, so **the sweep now fails on three codepoints** until they are
allow-listed. That is a decision, not an accident — the allow-list section below has been
updated to match rather than left to contradict this one. If the no-emoji rule is ever
reinstated, the three `Sm` characters above are the drop-in revert: change the three
`content` values back and nothing else moves.

**They sit to the left of the text, not above it.** The first version put the marker on its
own centred line above each heading; this one is an inline `::before` with
`margin-right:12px`, so the emoji leads the first line. That also let the tightened
`h2.problem + h2.problem` gap go away — the marker no longer adds a line of height, so the
three headings are back on the standard H2 rhythm.

**Still written as CSS escapes, still in the `<style>` block.** The rules spell them
`content:"\23F0"`, `content:"\1F916"`, `content:"\1F4DF"`, so the two HTML files gain
zero new non-ASCII bytes and `✓` (U+2713) remains the only symbol codepoint literally
present in either source file. The file-level sweep therefore still sees pure ASCII here;
it is the **rendered-DOM** pass, which resolves `::before` computed `content`, that fails.
`textContent` is untouched, so the ~22-word counts on these three headings and any text
extraction are unchanged. The classes still name the problem (`-ghost`, `-manual`,
`-phone`) and never the position, for the same reason `h2.mechanism` does.

**No `U+FE0F`.** All three codepoints are `Emoji_Presentation=Yes` already, so the
variation selector would be redundant bytes — and `U+FE0F` is itself on the sweep's fail
list, so leaving it out keeps one fewer thing to explain. `color:var(--accent)` was also
dropped from the rule: these render as colour glyphs and `color` does not reach them.

The `::before` carries an emoji font stack (`Apple Color Emoji`, `Segoe UI Emoji`,
`Noto Color Emoji`) because the body stack is a text face, and `content` is still declared
twice — the second as `content:"\23F0" / ""` — so the empty alt text stops a screen reader
announcing "alarm clock" / "robot" / "pager" ahead of each heading. Both pages were
re-rendered and all three glyphs resolve in colour, inline, at 1280px.

#### The 2026-09-08 copy pass — the Spanish body copy was replaced wholesale

Supplied as finished copy and shipped verbatim. **Spanish page only** (`index.html`); the
English page was not part of the instruction and still carries its original wording, so the
two pages are no longer translations of each other.

| Block | Now reads |
| --- | --- |
| Problem 1 | "Le das el estimado al cliente y desaparece… cuando ya andas en la yarda con la cuadrilla." |
| Problem 2 | "Angi y las agencias grandes te venden puros números…" |
| Problem 3 | "El teléfono lo contestas tú, alguien de la cuadrilla…" |
| Mechanism H2 | "¿Cómo te llenamos la agenda?" (shipped as "Así te llenamos la agenda"; reworded to a question the same day) |
| Bullets | Four full sentences (see the file) |
| Objection H2 | "¿Suena demasiado bueno para ser verdad? En la llamada te decimos de frente si esto no es para ti." |
| CTA button | "Agenda tu llamada" — unchanged |
| Risk reversal | "Es gratis y sin compromiso. En la llamada te explicamos las condiciones de la garantía." |

Nothing structural moved: same elements, same classes, same CSS, same order, all of it still
below the Calendly embed. Only the text nodes changed.

**Three earlier decisions this overrides**, recorded so they are not re-applied by mistake:

1. **The niche is gone from the body.** The mechanism H2 carried the word "landscaping"
   specifically because the eyebrow that used to hold the niche was deleted, making that H2
   the only place the niche appeared in the scan path. "Así te llenamos la agenda" drops it,
   so "landscaping" now survives only in the `<title>` and the meta description. If it should
   come back into the body, that H2 is where it goes.
2. **The bullets are sentences now, not fragments.** They were deliberately fragments — the
   benefit, not the explanation. The new copy writes them out in full.
3. **"Angi", not "Angie's List".** Shipped as written.

Every copy string quoted elsewhere in this README predates this pass and is historical.
`index.html` is the live text.

### (e) Other choices worth naming

- **4 bullets, not 5.** Still inside Oliver's 3-to-5 range. Each is a fragment, not a
  sentence. The fifth bullet (the definition of a confirmed appointment) was deleted on
  2026-09-08 — a definition is not a scannable benefit, and it already lives on the
  long-form page.
- **Button labels.** ES "Agenda tu llamada" (the live page's header CTA copy), EN "Book
  your call" (Oliver's literal wording). The live hero CTA is "Agenda tu llamada
  gratis"; "gratis" was moved into the risk-reversal line so the button stays short at
  375px, where it renders full-width.
- **`target="_blank"`.** Sends the reader to Calendly without destroying the page they
  are on, so the pitch is still behind them if they bounce off the calendar. Paired
  with `rel="noopener"`.
- **~~No embedded Calendly widget.~~ Reversed on 2026-09-08 (fourth pass), on explicit
  instruction.** The original reasoning stands on its own terms and is kept here so the
  trade-off stays visible rather than forgotten: the single goal was the click, an inline
  embed replaces that click with a scroll, and it costs an iframe plus a third-party
  script on load. What was bought in exchange is that the booking now starts on the page.
  The button was **not** removed — it is still there, still pointing at the same event.
- **`&copy;` entity.** The copyright line uses the HTML entity rather than a literal
  character. Note that since the 2026-09-08 marker pass the source is no longer free of
  Unicode symbol codepoints: `✓` (U+2713) appears once per file, inside the `<style>`
  block. It is still the only one — the three emoji markers added in the same pass are
  written as CSS escapes (`\23F0`, `\1F916`, `\1F4DF`) and add no non-ASCII bytes to
  either file, even though they resolve to emoji in the DOM. See the allow-list below.
- **`.render-check/`** holds four Playwright screenshots (ES and EN at 375px and
  1280px) taken during the build. Verification artifact, not part of the deliverable —
  safe to delete.

---

## What is deliberately NOT on these pages

No testimonials. No case studies. No client names. No results numbers. No logo strip.
No star ratings. No client counts. No prices. No ad-spend minimums. No years in
business. No team size. No dashboard screenshots. No second CTA. No nav. No
word "leads", in either language.

**"No emoji" was on this list until 2026-09-08 and is not any more.** Three were added to
the problem headings on explicit instruction. Everything else on the list still holds.

### The emoji allow-list — why the sweep has five exemptions

The sweep still runs and still fails on any pictographic character it is not told about.
**Five** codepoints are now allow-listed: the two typographic ones that were always here,
and the three emoji added to the problem headings on 2026-09-08. Nothing else is:

| Codepoint | Char | Where it lives | Why it is allowed |
| --- | --- | --- | --- |
| `U+2713` | `✓` | `<style>` block, `.points li::before` `content` | Typographic dingbat, not an emoji — no colour glyph, no `U+FE0F`, no emoji presentation. Attested on the live long-form page. |
| `U+00A9` | `©` | legal strip (source spells it `&copy;`) | Pre-existing. Required copyright notice. |
| `U+23F0` | ⏰ | `<style>` block, `h2.problem-ghost::before` (as `\23F0`) | Real emoji, added on instruction. Fails the sweep on category and on the `U+2300–2400` range; exempt by decision, not by category. |
| `U+1F916` | 🤖 | `<style>` block, `h2.problem-manual::before` (as `\1F916`) | Real emoji, added on instruction. Same. |
| `U+1F4DF` | 📟 | `<style>` block, `h2.problem-phone::before` (as `\1F4DF`) | Real emoji, added on instruction. Same. |

Everything else in `So` / `Sk`, and every codepoint in the pictographic ranges
(`U+1F000–1FAFF`, `U+2600–26FF`, `U+2700–27BF`, `U+2B00–2BFF`, `U+1F1E6–1F1FF`) plus the
variation selector `U+FE0F`, still fails. The three emoji rows above are the only
instruction-driven exemptions — **do not widen the list further on your own judgement**,
and do not delete the sweep because a legitimate character tripped it. Note that the
three emoji are exempt by decision and not by category: unlike `U+2713`, they are exactly
what the sweep was written to catch.

The `Sm` markers that briefly held these three slots (`↛` U+219B, `⊘` U+2298, `∄` U+2204)
never needed an exemption: category `Sm` does not fire the sweep at all. They are recorded
in the marker pass above as the drop-in revert if the no-emoji rule is reinstated.

The sweep runs over the **whole file, `<style>` block included** — not just body text —
and again over the rendered DOM (`body.innerText` plus every `::before` computed
`content`). That is what makes the `U+2713` exemption deliberate rather than an accident
of only scanning the markup.
