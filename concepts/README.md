# RHRI — Website redesign concepts

Self-contained directions for the RHRI site, built from the canonical copy in
[`CONTENT.md`](./CONTENT.md). Each is a **single self-contained `index.html`**
(inline CSS/JS, Google Fonts via CDN, no build step).

Two rounds so far:

- **Round 1** (2026-06, reviewed — none selected): Dossier, Signal, Bloom.
  Feedback: competent but safe; Signal closest. "Something more out there —
  reduce the content, add graphics."
- **Round 2** (2026-06-11, for review): Mitosis, Specimen, Deepfield — radical,
  graphics-first, ~100–130 words of visible copy each, rebrands allowed.

```
concepts/
├── index.html      ← review hub: both rounds, compare and open each
├── CONTENT.md      ← canonical copy deck (single source of truth)
├── README.md       ← this file
├── mitosis/index.html   04 · R2 — one living cell divides through the story
│                          (abyss black + bioluminescent teal + coral;
│                          Instrument Serif × mono; scroll-driven canvas)
├── specimen/index.html  05 · R2 — lab brutalism, type as the graphic
│                          (bone + ink + acid; variable Archivo; cursor-reactive
│                          headline, stamp-slam pillars, VALIDATED roundel)
├── deepfield/index.html 06 · R2 — fly THROUGH the network (Signal v2)
│                          (3D point-field flight in vanilla JS, HUD chrome,
│                          station rail; broken edges → dense validated core)
├── dossier/index.html   01 · R1 — editorial validation-dossier (paper + teal ink)
├── signal/index.html    02 · R1 — dark animated clinic-network
└── bloom/index.html     03 · R1 — warm cell-to-clinic editorial
```

All round-2 pages share: `prefers-reduced-motion` static fallbacks, rAF paused
on hidden tabs, reduced particle counts + no parallax on mobile, keyboard-
accessible interactions (`:focus-visible`, real buttons/links, skip links), and
a `mailto:dm@rhri.bio` CTA. Same content guardrails as round 1 (below).

## Run locally

The pages work by **double-clicking** any `index.html` (file://). For clean
behaviour (relative links in the hub, no CORS quirks), serve over http:

```bash
cd /Users/dm/dai/rhri/site-repo/concepts
python3 -m http.server 8080
# then open http://localhost:8080/
```

Start at the hub (`/`) and open each concept, or go direct:
`/dossier/`, `/signal/`, `/bloom/`.

## The three directions

| | Idea | Mood | Palette | Type | Signature UX |
|---|---|---|---|---|---|
| **01 Dossier** | The site *is* a validation dossier | Authoritative, editorial | Teal ink on warm paper | Spectral + JetBrains Mono | Numbered protocol spine, four-pillar **scorecard** |
| **02 Signal** | The decentralized network, alive | Kinetic, technical, dark | Dark navy + teal/coral | Space Grotesk + Inter | Animated clinic-network canvas, **audience channels** |
| **03 Bloom** | From cell to clinic | Warm, human, optimistic | Cream + coral + teal | Fraunces + Inter | Cell-division motif → pillars, color-blocked scroll |

All three share: the brand palette (Deep Teal `#0A5F5F`, Warm Coral `#E86C5C`,
Slate Blue `#4A5F7F`), the tagline **"Rigorous Science. Real-World Impact."**, a
recreated RHRI monogram (inline SVG, per-concept colorway), a working contact form
that builds a `mailto:` to **dm@rhri.bio**, scroll-progress + on-scroll reveals,
`prefers-reduced-motion` support, and full mobile→desktop responsiveness.

## Content guardrails honored

- **No fabricated statistics.** The old structure doc had `$XXM` / `XX%`
  placeholders — none were invented. Process durations are labelled "typical".
- **No named clinic/startup partners.** Partners/advisory board are shown as
  "in formation" (workspace rule 2 — soft commitments don't authorize naming).
- **Real team only:** Daniel Madero, Cynthia Hudson, Felicitas Azpiroz.
- **No PHI.**

## Notes & next steps

- These do **not** touch the live `site-repo/index.html` (still serving rhri.bio).
  Once a direction is chosen, promote its `index.html` to the repo root.
- The contact form uses `mailto:` (no backend), matching the current site. For
  real submissions, wire to a form service (Formspree/Netlify) at launch.
- Audit finding worth flagging: the **current live site is off-brand** (navy +
  purple, Cormorant Garamond) vs. the brand system (teal/coral, Inter family).
  All three concepts correct this.
