# isaacrubinstein.com

Single-page static site for Isaac Rubinstein, MPH, Independent Program Evaluator & Advisor.

## Files

| File | Purpose |
|---|---|
| `index.html` | Entire site (HTML, CSS, JS inline) |
| `favicon.svg` | Primary favicon (monogram "IR" on ink) |
| `favicon.ico` | Legacy favicon for older browsers |
| `apple-touch-icon.png` | iOS home-screen icon (180×180) |
| `og-image.png` | Open Graph / Twitter social-share image (1200×630) |
| `og-image.svg` | Source for the OG image (regenerate via `qlmanage`) |
| `robots.txt` | Crawler directives |
| `sitemap.xml` | Sitemap for search engines |
| `serve.sh` | Local dev server wrapper (`python3 -m http.server`) |
| `headshot.jpg` | **You must add this.** Square ~500×500px. Until present, a neutral silhouette placeholder renders. |
| `cv.pdf` | **You must add this.** Referenced from the Contact section "Download CV" button. |

## Deploy

### Netlify (drag-and-drop)
1. Go to https://app.netlify.com/drop
2. Drag this folder onto the drop zone
3. Point `isaacrubinstein.com` at the Netlify site (Domain settings → Add custom domain)

### GitHub Pages
1. Push to a GitHub repo
2. Repo → Settings → Pages → Source: `main` / `(root)`
3. For a custom domain, add a `CNAME` file containing `isaacrubinstein.com` and configure DNS

### Vercel
```
vercel
```
Accept defaults.

## Local development
```
./serve.sh
```
Serves on `http://localhost:8000`.

## Pre-launch checklist

- [ ] Add `headshot.jpg` (square, ≥500×500)
- [ ] Add `cv.pdf`
- [ ] Verify `mailto:isaac@isaacrubinstein.com` resolves
- [ ] Test Open Graph preview in the [Meta Sharing Debugger](https://developers.facebook.com/tools/debug/) and [LinkedIn Post Inspector](https://www.linkedin.com/post-inspector/)
- [ ] Submit `sitemap.xml` to Google Search Console
- [ ] Run Lighthouse audit (target: 95+ perf, 100 a11y, 100 best practices, 100 SEO)
- [ ] Validate HTML at https://validator.w3.org/
- [ ] Validate JSON-LD at https://search.google.com/test/rich-results

## SEO & technical notes

- **Structured data:** `Person` + `ProfessionalService` JSON-LD schemas are embedded in `<head>`. Validate with Google's Rich Results Test.
- **Open Graph:** 1200×630 PNG, generated from `og-image.svg`. Regenerate with:
  ```
  qlmanage -t -s 1200 -o . og-image.svg && mv og-image.svg.png og-image.png && sips -c 630 1200 og-image.png --out og-image.png
  ```
- **Canonical URL:** `https://isaacrubinstein.com/` (update if deploying elsewhere).
- **Accessibility:** WCAG 2.2 AA, focus-visible styles, skip link, `prefers-reduced-motion` support, semantic landmarks, labeled regions.
- **Print:** dedicated print stylesheet; hero, about, services, and projects survive a paper print.
- **Core Web Vitals:** headshot has explicit `width`/`height` (no CLS); fonts use `display=swap`; single HTML file, no blocking JS.
- **Page weight:** `index.html` is ~18KB. Total (excluding headshot + CV) well under 50KB.

## Design system

This site is **Brand A (Ink/Ochre/Teal)**, the evaluation-practice identity. The full spec lives in [`DESIGN.md`](DESIGN.md) at the repo root, which is the source of truth. Summary:

| Token | Value | Role |
|---|---|---|
| Ink | `#0F1729` | Headings, display, dark UI |
| Graphite | `#2A2D34` | Body text |
| Slate | `#5A6170` | Meta, labels, captions |
| Ochre (web) | `#7E5825` | Editorial accent: numerals, links, rules (darkened for WCAG AA) |
| Teal | `#2B6A6E` | Analytical accent: findings and numbers (print today) |
| Rule | `#D8D2C3` | Warm hairlines |
| Cream | `#F7F4EC` | Page background |
| Paper | `#FFFFFF` | Cards and panels |

Headings: Fraunces (variable serif) · Body: Inter · Reading column 680px inside a 920px frame.

## Updating content

All copy lives directly in `index.html`. Search for a section heading (e.g. `id="about"`) to find the corresponding block.

When you add a new project, drop another `.project` block inside `#experience`. When you add a testimonial, uncomment the `<figure class="testimonial">` block at the bottom of the experience section and fill in the quote and citation.
