# CLAUDE.md

## What this repo is
The personal-name site at https://isaacrubinstein.com/: Isaac Rubinstein, MPH, Independent Program Evaluator & Advisor. This is the Brand A (Ink/Ochre/Teal) evaluation-practice surface under the two-brand firewall defined in `DESIGN.md`; the sibling identity (Rubinstein Productions, rubinsteinproductions.com) is a separate system, and its palette, typefaces, and vocabulary never cross into this repo. Static HTML and CSS, no framework, no build step, no dependencies. The home is `index.html`; the subpages `method/`, `work/central-providence-hez/`, and `writing/` (an index plus two essays) share `styles.css` with small per-page inline blocks. There are no JS files; each page carries one short inline script (masthead scroll cue and scroll-progress bar, duplicated per page; the IntersectionObserver nav highlight is home-page only), so a change to that behavior touches every page. `README.md` covers assets, SEO, and the pre-launch checklist, but its file table predates the CSS extraction and the subpages; trust the tree.

## Build & deploy
There is no build. Deploys are pushes: GitHub Pages serves `main` at the root (legacy Pages build), and `CNAME` sets the custom domain. Local preview: `./serve.sh` (Python http.server on port 8000). When adding a page, add its URL to `sitemap.xml` by hand; there is no generator.

## Design constraints
`DESIGN.md` at the repo root is the design source of truth and the portable contract; read it before touching anything visual. Web token values live in `styles.css` custom properties; reference the variable, never hand-type hex, even correct hex. The rules most often at risk:

- One job per accent. Ochre is the editorial accent (numerals, links, labels); teal is the analytical accent (findings and numbers). Never both on one element.
- Fraunces carries editorial weight, Inter carries everything functional. Weights 400 to 600 only, Fraunces opsz matched to rendered size, tabular lining numerals on any figure a reader compares.
- Structure is 1px hairlines and surface changes. No shadows (the headshot is the one exception), no gradients (the paper texture is the one exception), square corners, borders at or below 2px.
- Voice is plain and MPH-credentialed. No em-dashes anywhere, including microcopy and code comments. No promotional adjectives. The Brand B vocabulary listed in DESIGN.md's Firewall paragraph stays out of this repo entirely.
- Known deviations (two ochre grades, teal being print-only today, and the rest) are catalogued in DESIGN.md's Provenance section. Do not re-litigate them, and do not add new ones silently.

## Security
- PUBLIC repo. No client names, no pricing, no BD detail, no tokens or secrets. Nothing lands here that could not sit on the open web.
- Two per-clone git hooks guard that line; neither is committed, so wire both on any fresh clone:
  - `pre-commit`, secret scan: `ln -sf ~/scripts/git-hooks/pre-commit-secret-scan .git/hooks/pre-commit`
  - `pre-push`, privacy scan (wired 2026-08-08): `ln -sf ~/scripts/git-hooks/pre-push-privacy-scan .git/hooks/pre-push`
- The pre-push scan runs stack-data's `sd-privacy-scan` over every commit in the push and blocks on hits against a private denylist. It exists because the wall once failed by hand: in July 2026 a private page was briefly pushed to a public repo before the mistake was caught. The hook makes that class of leak mechanical to catch instead of attention-dependent. The denylist lives in the private stack-data clone on purpose; if `~/stack-data` is absent the hook skips rather than blocks, so a clean push on a machine without stack-data proves nothing. `git push --no-verify` is for confirmed false positives only, and only after reading the flagged line.

## Working here
- Copy lives directly in the HTML; find a section by its `id`. New project blocks go inside `#experience` on the home page; a new essay gets a directory under `writing/` plus links from `writing/index.html` and `sitemap.xml`.
- Keep the page light: `index.html` is about 20KB, there is no blocking JS, and fonts load with `display=swap`. A change that adds a framework, a build step, or a runtime dependency is out of scope by design.
- Honor `prefers-reduced-motion` fully and hold WCAG AA contrast. Accessibility is a constraint, not a finish; the web ochre grade was darkened for exactly this reason.

## Routing
- Tier: none. A public brand surface, not a stack-data consumer. The spine is stack-data, Tier 1, a sibling clone (`../stack-data`).
- The phase-zero `.claude/` kit is deployed here and its trigger phrases work. Kit files under `.claude/` are managed by the kit deploy, not edited ad hoc.
