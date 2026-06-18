# wildwillow.cc — prototypes

Static HTML/CSS prototypes for two parallel positionings of wildwillow. No build step, no dependencies.

## File structure

```
wildwillow/
├── index.html              # Four-modality landing (Ayurveda lead)
├── herbalism.html          # Western herbalism landing
├── vision.html             # Shared vision/strategy document
├── styles.css              # Shared design system
├── README.md               # This file
│
└── conditions/             # Condition pages
    ├── swimmers-ear.html              # Four-modality treatment
    ├── swimmers-ear-herbalism.html    # Western herbalism deep dive
    └── brain-fog.html                 # Four-modality treatment
```

## The two prototypes

**Four-modality (`index.html` → `conditions/swimmers-ear.html`, `conditions/brain-fog.html`)**
Curated content across Ayurveda, Western herbalism, yoga, and breathwork. Each condition page shows where the four traditions converge and diverge, with editorial synthesis as the differentiator. Demo audience: integrative MD / clinician collaborators (e.g., Darshan Shah).

**Western herbalism (`herbalism.html` → `conditions/swimmers-ear-herbalism.html`)**
Single-modality deep dive. Real preparation guidance, branded product recommendations with collapsible reviews, and herbalism-specific framing. Demo audience: practicing herbalists (e.g., Ginger Webb).

The two prototypes share styles.css and the vision document, but their landing pages don't reference each other. Send the right URL to the right audience.

## Vision document

`vision.html` is the strategic explainer — the "Zocdoc for alternative healing practitioners" framing, market sizing, risks. Shared between prototypes; can go to either audience.

## Demo flows

**Four-modality flow:**
1. Open `index.html`
2. Search "swim" or "brain"
3. Click result → lands on `conditions/swimmers-ear.html` or `conditions/brain-fog.html`

**Western herbalism flow:**
1. Open `herbalism.html`
2. Search "swim"
3. Click result → lands on `conditions/swimmers-ear-herbalism.html`

## Preview locally

Open `index.html` or `herbalism.html` in any browser. No server needed.

## Deploy to GitHub Pages

1. Create a public repo
2. Push these files maintaining the directory structure
3. Repo → Settings → Pages → Deploy from branch → main → `/` (root) → Save
4. Live at `https://[username].github.io/[repo-name]/`

URLs after deploy:
- `wildwillow.cc/` → four-modality landing
- `wildwillow.cc/herbalism.html` → herbalism landing
- `wildwillow.cc/vision.html` → vision document
- `wildwillow.cc/conditions/swimmers-ear-herbalism.html` → herbalism deep dive

## What's a placeholder vs. real

**Real:**
- Search UX, condition catalog architecture, editorial layout
- Brand names (Herb Pharm, Wise Woman Herbals, Kerala Ayurveda, Banyan Botanicals, Wally's Natural)
- Classical Sanskrit terms and Western herbalism nomenclature
- Modality colors, design system
- YouTube tutorial links (real channels) on four-modality pages
- Vision document market data (practitioner counts, Headway comp)

**Plausible placeholders, verify before publishing:**
- Product prices — estimates
- Star ratings and review counts — illustrative
- Review snippets and attribution (e.g. `r/herbalism · u/openwaterswim`) — fictional but realistic
- The "100K practitioners" full-platform TAM number
- Capital commitment placeholder in vision doc

## Adding new condition pages

1. Create `conditions/[slug].html`
2. In the relevant landing page, find the conditions array in the script
3. Set `available: true` for that slug
4. The search will now route to it

Match the slug to filename: `slug: "mosquito-bites"` → `conditions/mosquito-bites.html`

## Notes on extending the structure

Currently both prototypes live in the same directory tree, which works while there are only a few conditions per prototype. If the herbalism prototype grows to 20+ condition pages, consider a subdirectory split:

```
herbalism/index.html
herbalism/conditions/*.html
ayurveda/index.html
ayurveda/conditions/*.html
```

Don't do that yet — the current flat structure stays easier to manage until each prototype has substantially more content.

## Fonts

Newsreader (serif) and Inter (sans) loaded from Google Fonts. First load ~200ms.

## What's not in these prototypes

No analytics, no actual affiliate IDs (Amazon links go to search), no SEO meta beyond basic title/description, no structured data, no commenting (planned via Supabase for the vision page). These belong in production, not the demo.
