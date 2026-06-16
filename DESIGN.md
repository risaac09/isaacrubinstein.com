---
version: alpha
name: Isaac Rubinstein, Evaluation Practice
description: Ink, Ochre, Teal. A warm editorial system for an independent program evaluator. Fraunces and Inter on cream, hairline structure, two accents with one job each, accessibility as a constraint not a finish.
# Source of truth (web): styles.css. Source of truth (print): the proposal-builder ReportLab scripts in the toolkit and rp-intranet.
# This file is the portable contract. The frontmatter tokens are the WEB grades. If a value changes in styles.css, update this file in the same commit.
colors:
  primary: "#0F1729"      # Ink. Deep prussian. Headings, display, dark UI, the document signature bar.
  graphite: "#2A2D34"     # Body text. Warmer than black.
  slate: "#5A6170"        # Meta, labels, captions, muted figures.
  ochre: "#7E5825"        # Editorial accent, web grade. AA-safe on cream at text sizes.
  ochre-lt: "#B98345"     # Ochre hover, web grade.
  ochre-print: "#9A6B2F"  # Editorial accent, print grade. Richer; for large marks and bars where small-text contrast is not the constraint.
  ochre-print-lt: "#C8935A" # Ochre print light: hover and secondary in print artifacts.
  ochre-wash: "#F5EDE0"   # Ochre-headed table rows, callout and tag fills.
  teal: "#2B6A6E"         # Analytical accent: findings and numbers. Print today; no web CSS token exists yet (see Provenance 2).
  teal-lt: "#4A9EA3"      # Teal hover / secondary analytical.
  teal-wash: "#E6F3F4"    # Teal-headed table rows, the stats panel.
  rule: "#D8D2C3"         # Warm hairline. Borders, dividers, table grid.
  cream: "#F7F4EC"        # Page background. Warm off-white.
  surface: "#FFFFFF"      # Paper. Cards and panels.
  success: "#3A7D44"      # Semantic only: positive or on-track finding.
  caution: "#B5760A"      # Semantic only: mixed or needs attention.
  alert: "#A03030"        # Semantic only: risk or concern.
typography:
  display:
    fontFamily: Fraunces
    fontSize: 4.5rem
    fontWeight: 500
    lineHeight: 0.95
    letterSpacing: -0.035em
    fontVariation: '"opsz" 144, "SOFT" 30'
  headline:
    fontFamily: Fraunces
    fontSize: 2rem
    fontWeight: 600
    lineHeight: 1.15
    letterSpacing: -0.015em
    fontVariation: '"opsz" 144, "SOFT" 30'
  subhead:
    fontFamily: Fraunces
    fontSize: 1.5rem
    fontWeight: 600
    lineHeight: 1.2
    letterSpacing: -0.01em
    fontVariation: '"opsz" 36, "SOFT" 30'
  lede:
    fontFamily: Fraunces
    fontSize: 1.375rem
    fontWeight: 400
    lineHeight: 1.45
    fontVariation: '"opsz" 36, "SOFT" 30'
  body:
    fontFamily: Inter
    fontSize: 1.0625rem
    fontWeight: 400
    lineHeight: 1.65
    fontFeature: '"kern", "liga", "calt", "ss01"'
  body-sm:
    fontFamily: Inter
    fontSize: 0.9375rem
    fontWeight: 400
    lineHeight: 1.55
  numeral:
    fontFamily: Fraunces
    fontSize: 1rem
    fontWeight: 500
    fontFeature: '"tnum", "lnum"'
    fontVariation: '"opsz" 14'   # small numerals; scale opsz up to match larger figures (144 at stat-display size)
  label:
    fontFamily: Inter
    fontSize: 0.75rem
    fontWeight: 600
    letterSpacing: 0.14em
rounded:
  DEFAULT: 0px
  focus: 2px
spacing:
  xs: 0.5rem
  sm: 1rem
  md: 1.5rem
  lg: 2rem
  xl: 3rem
  2xl: 4.5rem
  3xl: 6rem
  base: 8px
  text-measure: 680px
  frame: 920px
components:
  link:
    textColor: "{colors.primary}"
    typography: "{typography.body}"
  button-cv:
    backgroundColor: "{colors.primary}"
    textColor: "{colors.cream}"
    typography: "{typography.label}"
    rounded: "{rounded.DEFAULT}"
    padding: "0.75rem 1.375rem"
  button-cv-hover:
    backgroundColor: "{colors.ochre}"
    textColor: "{colors.cream}"
  card:
    backgroundColor: "{colors.surface}"
    textColor: "{colors.graphite}"
    rounded: "{rounded.DEFAULT}"
    padding: 1.75rem
  masthead:
    backgroundColor: "{colors.cream}"
    textColor: "{colors.primary}"
---

# Design System: Isaac Rubinstein, Evaluation Practice

## Overview

This is the visual identity of an independent program evaluator. It reads as a warm editorial document: serif display on cream, plain sans body, hairline structure, and restraint everywhere. The job of the design is to make findings legible and credible, not to decorate them.

The governing test, from the brand spec: if an element exists only to look professional, remove it.

What this system refuses: no drop shadows, no gradients, no stock-diagram cliches (no gratuitous color, no clip-art icons), no borders heavier than 2px, no element that earns its place only by looking polished. Contrast is a hard requirement, not a final pass.

The brand spans two media. The web home (isaacrubinstein.com) is Fraunces and Inter on cream. The print deliverables (capabilities statement, cover letters, evaluation proposals) are Helvetica on white. The palette and the accent logic carry across both; the typefaces and a few grades do not, and the rules below say exactly where they diverge.

**The Firewall.** This file governs Brand A only: the evaluation practice, isaacrubinstein.com, and the proposal-builder PDFs, signed "Isaac Rubinstein, MPH." The sibling identity (the Digital Liver system at rubinsteinproductions.com, the Rubinstein Productions and Say Why facilitation and film work) is a separate system with a hard wall between them. Never import its palette (Marrow, Blood, Amber, Bone, Ash), its typefaces (EB Garamond), or its register here. Never let this brand's plain evaluator voice leak there. Forbidden across the wall into this brand: the words "embodied," "metabolize," "alchemy," "Say the thing," "Say Why," and Deleuzian or somatic vocabulary of any kind. Internal-only terms never appear in client-facing work: write "institutional metrics" not "Royal Metrics," "relational indicators" not "Nomadic Indicators," and never the deprecated tier names Mirror, Map, Territory.

**Sources of truth.** Web tokens: `styles.css`. Print palette and type: the proposal-builder ReportLab scripts (`build_capabilities_statement_generic.py` and the README in the toolkit; the bid-specific proposal scripts live in the rp-intranet repo). Philosophy and voice: the canonical brand spec in the vault at `07 Capture/Claude Visual Packets/00 - Visual System & Brand Spec.md`. When you need a web value, reference the CSS custom property; hand-typed hex values are a defect even when they match.

**Voice.** Plain, MPH-credentialed, industry-standard. Write the way an evaluation report reads: precise and sourced, never hurried. No promotional adjectives, no rule-of-three cadences, no em-dashes anywhere including microcopy and code comments. State the finding; let it stand.

## Colors

The palette is warm neutrals plus two working accents and three status colors. Ink, graphite, slate, rule, cream, and paper carry the same value in every medium. The accents have grades and rules.

- **Ink (#0F1729):** A deep prussian, not black. Headings, display type, dark UI, the cv button, and the 8pt signature bar at the top of every PDF.
- **Graphite (#2A2D34):** Body text. Warmer than pure black, which the brand never uses.
- **Slate (#5A6170):** Meta, labels, captions, footers, stat labels, muted figures.
- **Ochre, the editorial accent.** Two grades. Web grade #7E5825 (with hover #B98345) is darkened to clear WCAG AA on cream at text sizes, roughly 5.8:1. Print grade #9A6B2F (with light #C8935A) is richer and reads correctly on large marks and bars where small-text contrast is not the constraint. Ochre carries section numerals, links, the scroll-progress bar, section rules, H2 subheads in print, and the fee-table header band.
- **Teal, the analytical accent (#2B6A6E):** Findings and numbers. With secondary #4A9EA3 and wash #E6F3F4. In print this carries H3 subheads, the methods and effort table headers, callout text, and the stat numerals on the capabilities statement.
- **Rule (#D8D2C3):** A warm hairline. Borders, dividers, the 0.5pt table grid, the line between numbered sections.
- **Cream (#F7F4EC):** The page. A warm off-white, never clinical.
- **Paper (#FFFFFF):** Cards, panels, and the default table cell.
- **Washes:** Ochre-wash #F5EDE0 and teal-wash #E6F3F4 fill alternating table rows and panels, each paired to its accent.
- **Status colors:** Success #3A7D44, Caution #B5760A, Alert #A03030. These are semantic, never decorative.

### Color Rules

**The Accent Division Rule.** Ochre is the editorial accent; teal is the analytical accent. Never use both to decorate the same element. If it is a finding or a number, it is teal. If it is a label or a call to action, it is ochre. This is the single most important rule in the system, and the one most worth defending in review.

**The Two Ochre Grades Rule.** Web ochre is #7E5825 (roughly 5.8:1 on cream) because it must clear AA on cream at small sizes. Print ochre is #9A6B2F (4.23:1 on cream, below the 4.5:1 AA threshold for small text) because print marks are large and the richer value reads better on paper. Use the web grade for any screen text or small UI; reserve the print grade for large bars, headers, and marks. Do not put the print grade on small web text, and do not flatten the two into one value.

**The Semantic Color Rule.** Success, caution, and alert signal finding status only. They never decorate, never theme a section, and never appear because a color would look nice there.

**The Restraint Rule.** If an element exists only to look professional, remove it. Borders stay at or below 2px. Structure is carried by 1px rule hairlines and surface changes, not by chrome. No drop shadows, no gradients, no decorative color.

## Typography

Two families on the web, one in print.

- **Fraunces** (variable serif) carries display, headings, the lede, pull quotes, and all numerals. It is the editorial voice. Match the optical-size axis to the rendered size: opsz 144 for display and large headings, opsz 72 for pull quotes and list titles, opsz 36 for the lede and subheads, opsz 14 for small numerals. Weights 400, 500, 600. SOFT 30 softens the terminals at display sizes.
- **Inter** carries body, labels, navigation, captions, and UI. Weights 400, 500, 600. Body at 17px on 1.65, with `"kern", "liga", "calt", "ss01"` enabled. Use `"tnum", "lnum"` on any tabular numbers.
- **Print uses Helvetica throughout**, as a system-font substitute. The brand typefaces are not embedded in the PDFs. This is a pragmatic deviation, not a preference; see Provenance.

The web type scale is a fixed set of px values, the spec's canonical scale: 12, 14, 17, 19, 24, 32, 48, 72 (19 carries the about-page lead paragraph; 48 is a reserved step with no current element, do not invent one to fill it).

### Hierarchy (web)

- **Display (hero name):** Fraunces 500, `clamp(2.75rem, 7.5vw, 4.5rem)`, line-height 0.95, tracking -0.035em, opsz 144. Max-width 780px.
- **Headline (H2):** Fraunces 600, 2rem (32px), line-height 1.15, tracking -0.015em, opsz 144.
- **Subhead (H3):** Fraunces 600, 1.5rem (24px), line-height 1.2, tracking -0.01em, opsz 36.
- **Lede:** Fraunces 400, `clamp(1.125rem, 1.8vw, 1.375rem)`, line-height 1.45, opsz 36, color ink, max-width 540px.
- **Body:** Inter 400, 17px, line-height 1.65, graphite.
- **Body small (cards, projects):** Inter 400, 15px, line-height 1.55.
- **Numerals (section numbers, stat figures):** Fraunces 500, ochre, tabular and lining, opsz matched to size.
- **Label / eyebrow / small-caps:** Inter 600, 12px, tracking 0.14em, uppercase, slate.
- **Pull quote:** Fraunces italic 400, `clamp(1.25rem, 2.4vw, 1.625rem)`, line-height 1.3, opsz 72, ink, behind a 2px ochre left border.

### Typography Rules

**The Two Families Rule.** Fraunces carries editorial weight, Inter carries everything functional. Never set body in Fraunces or a headline in Inter. There is no third web family, and there is no mono in use anywhere despite the spec naming one.

**The Optical Size Rule.** Always match Fraunces opsz to the rendered size. Large type takes opsz 144, small numerals take opsz 14. A display face set at the small optical size, or the reverse, is a defect.

**The Tabular Numbers Rule.** Any figure a reader might compare or scan (outcomes, dates, read times, stat panels) uses tabular lining numerals (`tnum`, `lnum`). Findings are quantitative; their numbers align.

**The Weight Ceiling Rule.** The web applies Fraunces and Inter at 400, 500, and 600. Nothing heavier. Hierarchy comes from size, optical size, weight within that range, color, and space. Heavier weights are loaded in the font request but unused; do not start using them, and trim the request when convenient.

### The Wordmark

The mark is typographic. There is no graphic logo on this side.

- **Masthead:** "Isaac Rubinstein" in Fraunces 600, opsz 36, ink, 17px, tracking -0.005em, baseline-aligned with "MPH" as a credential tag in Inter 600, 11px, tracking 0.12em, uppercase, slate. The tag sits inline beside the name, not raised.
- **Hero:** the name at display scale (Fraunces 500, opsz 144) with "MPH" as a raised suffix at 0.45em, Inter uppercase, slate, vertical-align 0.5em. An eyebrow sits above: "Independent Program Evaluator & Advisor," uppercase 12px slate.
- **Print:** "ISAAC RUBINSTEIN, MPH" in Helvetica-Bold 18 all-caps on the capabilities statement, "Isaac Rubinstein, MPH" in Helvetica-Bold 14 on the cover letter, always beneath the ink bar and ochre line signature.

## Layout

Structure is editorial: a single reading column inside a wider frame, sections separated by hairlines and numbered.

- **Measures:** 680px reading column (`--maxw-text`), 920px outer frame (`--maxw-wide`). Display caps at 780px, the lede at 540px. Body paragraphs default to the reading measure.
- **Spacing:** an 8pt grid. The web scale is 0.5, 1, 1.5, 2, 3, 4.5, 6rem (8 through 96px). The px type scale (12 to 72) matches the spec exactly. Section blocks use the 4.5rem step for vertical rhythm.
- **Sections:** each opens with a numbered header (Fraunces ochre numeral plus a 28px ochre tick rule, then an H2) and closes with a 1px rule border. The last section drops the border.
- **Breakpoints:** 820px (the large steps shrink, grids collapse toward single column, the outcomes strip goes to two columns) and 640px (body drops to 16px, nav stacks, every grid goes single column).
- **Print page:** US Letter. Margins are 1in left and right, 0.9in top, 0.85in bottom for the capabilities statement and proposals; the cover letter runs tighter at 0.85in sides and 0.55in top and bottom.

### Layout Rules

**The Numbered Section Rule.** Sections are numbered (01 through 05 on the home) with a Fraunces ochre numeral and a short ochre tick. The numbering is part of the structure, not ornament; it gives the document the feel of a report with a table of contents.

**The Hairline Structure Rule.** Separation comes from 1px rule hairlines and surface changes (cream, paper), not from boxes or shadows. The service grid uses 1px rule gutters so cells are divided by hairlines rather than borders. If you are about to add a box, try a hairline first.

**The Reading Measure Rule.** Body text holds the 680px measure. Do not let paragraphs run the full 920px frame; the frame is for structure, the measure is for reading.

## Elevation & Depth

The system is nearly flat. Hierarchy is carried by type, color, hairlines, and surface, not by elevation.

The few real depth cues, all restrained:

- **The Headshot Lift.** The hero headshot carries `box-shadow: 0 1px 0 var(--rule), 0 20px 40px -20px rgba(15,23,41,0.15)`: a hairline plus one soft, far-offset ink shadow. This is the only true drop shadow in the system, reserved for the single photographic element. Portraits are also desaturated (grayscale 15 percent on the hero headshot, 20 percent on secondary portraits; contrast 1.02) so the warm palette stays dominant.
- **The Masthead Scroll Cue.** On scroll the sticky masthead gains a rule bottom-border and a 1px near-invisible ink shadow (`0 1px 0 rgba(15,23,41,0.03)`). It is a hairline wearing a shadow's syntax.
- **The Paper Texture.** A fixed, pointer-events-none layer carries two radial gradients at 2.5 percent alpha (print-grade ochre, rgb(154,107,47) = #9A6B2F, at top-left; ink at bottom-right; catalogued in Provenance 8). It is felt, not seen, and it is the only gradient the brand permits.

Everything else is flat. No card shadows, no layered elevation model, no glass beyond the masthead's cream-tinted blur backdrop.

## Shapes

Square by default. `rounded.DEFAULT` is 0px and applies to every container: cards, the cv button, the headshot, panels, tables. The brand is hairlines and right angles.

The only radius in the system is the 2px focus radius on interactive outlines, and the 4pt rounded corner on the print stats panel. Neither is a decorative move; both are functional softening at a single small scale.

## Components

- **Masthead:** sticky, cream at 0.92 alpha with a `saturate(180%) blur(12px)` backdrop. The wordmark left, numbered nav links right. Links are Inter 13px with a Fraunces ochre numeral; the active link (set by IntersectionObserver) and hover both draw a 1px ink underline via a scaleX transform and shift the text to ink.
- **Links (body):** ink text with a 1px ochre underline at 3px offset; hover shifts the text to ochre and the underline to the light grade. Credential links are muted until hover.
- **CV button:** ink background, cream text, uppercase label, padding 0.75rem by 1.375rem, square. Hover fills ochre and lifts 1px. Focus-visible draws the 2px ochre outline at 4px offset.
- **Service cards:** paper background, 1.75rem padding, a lowercase roman numeral in Fraunces ochre, an H3, body-small copy, then an uppercase slate keyword line over a top rule. Hover warms the background to #FDFCF7. Cells are divided by 1px rule gutters, not borders.
- **Pull quote and asides:** a 2px ochre left border with the content indented. This left-border motif marks the editorial aside register and is reused by the method and writing teasers.
- **Projects:** a 120px uppercase meta column (labels in ochre, values in graphite) beside the body, separated from the next by a rule border.
- **Numbered section header:** Fraunces ochre numeral, a 28px by 1px ochre tick, then the H2. The signature structural element.
- **Print tables:** a colored header band keyed to the table's job (teal for methods and effort, ochre for fees, ink for timeline), a 1.5pt rule above in the band color, a 0.5pt rule grid, alternating wash rows paired to the accent, and total rows on an ink band with white bold text.
- **Print signature:** an 8pt ink bar across the very top of the page, a 1.5pt ochre line just below it, and a 0.75pt ochre rule near the foot. This is the locked document signature on every PDF.
- **Skip link and focus:** the skip link is off-screen until focus, then ink on cream. Global focus-visible is a 2px ochre outline at 3px offset with a 2px radius. Accessibility furniture is brand furniture.

### Motion

The web motion is minimal and functional. The print side is fully static.

- **Durations and eases:** 0.2s for link color and decoration, 0.25s for the nav underline, masthead border, and card background, 0.1s linear for the scroll-progress width.
- **Scroll-progress bar:** a 2px ochre bar at the top, width driven by scroll position.
- **Masthead:** toggles its scroll cue past 8px of scroll.
- **No entrance choreography.** Content is present on load; nothing fades or slides in. The brand does not perform.
- **Reduced motion:** `prefers-reduced-motion` nulls every transition and hides the scroll-progress bar. Honor it fully.

## Do's and Don'ts

- Do keep one job per accent: teal for findings and numbers, ochre for labels and calls to action. Don't decorate a single element with both.
- Do use the web ochre grade (#7E5825) for screen text and the print grade (#9A6B2F) for large print marks. Don't put the print grade on small web text.
- Do set findings' numbers in tabular lining numerals. Don't let figures that a reader compares sit in proportional numerals.
- Do match Fraunces optical size to rendered size. Don't ship display type at a small opsz or small numerals at a large one.
- Do carry structure with 1px rule hairlines and surface changes. Don't add boxes, drop shadows (the headshot is the one exception), or borders over 2px.
- Do keep corners square. Don't round cards, buttons, or panels; the 2px focus radius and 4pt print stats panel are the only curves.
- Do write in the plain MPH-credentialed register. Don't use em-dashes, promotional adjectives, rule-of-three cadences, or any Brand B vocabulary.
- Do treat semantic colors as status signals. Don't use success, caution, or alert to decorate.
- Don't use pure black or clinical white; the floor is ink, the ground is cream, panels are paper.
- Don't introduce a third web typeface, a mono face, or Fraunces and Inter weights above 600.
- Do reference CSS custom properties for every web value. Don't hand-type hex, even correct hex.
- Do hold the firewall: this palette, these typefaces, and this voice never mix with the Digital Liver brand.
- Do maintain WCAG AA on all text, the reason the web ochre is darkened in the first place. Don't reintroduce the lighter ochre on small text.
- Do remove any element that exists only to look professional.

## Provenance

Decisions this file arbitrates, so they are not re-litigated:

1. **Ochre has two grades, on purpose.** Web #7E5825 (darkened for AA on cream), print #9A6B2F (richer for large marks). Both are canonical in their medium (The Two Ochre Grades Rule). The web CSS still cites the old value in a comment; that is documentation, not a second token.
2. **Teal is the analytical accent, realized in print today.** The Accent Division Rule is the canonical intent: findings and numbers are teal. The live styles.css renders the hero outcome figures in ochre and ships no teal CSS custom property, even though this contract defines teal tokens for the print side and any future web reconciliation. That is a known deviation, not a counter-rule. Reconciling it (introducing a web teal token for data and figures, or formally exempting the hero) is an open decision; until then, the rule stands as intent and the deviation is named here.
3. **Print uses Helvetica as a system-font substitute.** The brand typefaces (Fraunces, Inter) are not embedded in the PDFs. The frontmatter typography tokens are the web grades. If PDF font embedding is set up later, the print side should move to Fraunces and Inter to match the web.
4. **Web heading sizes are the source of truth for the frontmatter.** Print heading sizes are documented in prose. The toolkit README's "H1 17pt" line matches nothing in the current scripts (RIPCA uses H1 18, H2 14, H3 11, body 10.5 on 16); treat the README figure as stale.
5. **The spacing grid is 8pt and the type scale is 12 to 72px,** both per the spec and both honored at the token level. Some component paddings sit off-grid; the tokens, not the one-off paddings, are the standard.
6. **Contact and location strings have drifted** across artifacts (Providence on the web, Providence-relocating-Oslo on the capabilities statement, Seattle with a phone on the cover letter, Rhode Island in the RIPCA footer). Not a design rule, but flagged: pick one canonical contact block.
7. **The repo README, favicon, and OG image still carry the pre-rebrand navy and gold identity** (Navy #1B2A4A, Gold #C5A55A, Source Serif 4, Source Sans 3). These are stale assets that contradict Ink/Ochre/Teal and should be replaced; the shipped favicon and social-share image currently present the wrong brand.
8. **Print ochre appears in two web spots.** The Central Providence HEZ case-study SVG hardcodes #9A6B2F instead of the web grade (inline SVG cannot always read host CSS variables), and the body paper-texture radial uses the same print grade. The HEZ SVG also uses an off-token outcome-box fill (#FAF6EE) that should be reconciled to ochre-wash (#F5EDE0). These are the known print-ochre-in-web exceptions; constrained and noted, not the standard.
9. **A malformed `font-variation-settings` value** on `.section-num` in styles.css (a stray trailing quote) silently drops the opsz axis on in-section numerals. A defect to fix, not a design choice.
10. Ground truth read 2026-06-11 from `styles.css`, `index.html`, the repo pages, the canonical brand spec, and the proposal-builder scripts (`build_capabilities_statement_generic.py`, `build_cover_letter.py`, and the RIPCA reference).
