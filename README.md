# wildwillow.cc — demo prototype

A static HTML/CSS prototype of the wildwillow.cc concept. No build step, no dependencies — just files.

## What's here

- `index.html` — landing page with search, body region tiles, and "how it works" section
- `swimmers-ear.html` — the fully built condition page (the demo flow target)
- `styles.css` — shared stylesheet for all pages
- `README.md` — this file

## Demo flow

1. Open `index.html` in a browser
2. Type "swim" or "ear" in the search bar
3. Click the "Swimmer's ear" result (or press Enter — it picks the first available match)
4. Land on the swimmer's ear condition page

The 8 other conditions appear in search results marked "Coming soon" — they're not built yet but show that the system handles a real catalog.

## Preview locally

Open `index.html` in any browser. It just works.

## Deploy to GitHub Pages

1. Create a new repo (public is simpler).
2. Drag these files into the repo root and commit.
3. Repo → Settings → Pages → Source: **Deploy from branch** → Branch: **main** → Folder: **/ (root)** → Save.
4. Wait ~60 seconds. Your site is live at `https://[username].github.io/[repo-name]/`.

## What's a placeholder vs. real

**Real:** the search UX, all visible product names, brand names, classical Sanskrit terms, the editorial layout, modality colors, the YouTube tutorial links (Art of Living, Brett Larkin, Yoga with Adriene).

**Plausible placeholders that you should verify before publishing for real:**
- Product prices ($12, $9, $18, etc.) — educated guesses
- Star ratings and review counts — also estimates
- Review snippet attribution (e.g. `r/ayurveda · u/khichdi_eater`) — illustrative, not actual Reddit users
- YouTube video durations ("3 min", "5 min") — approximate

For the demo, these are fine. Before the site goes live publicly, verify and replace.

## Search behavior

The search uses a local in-page JS array of 9 conditions. Typing filters by name and body region. Only swimmer's ear is clickable. Available items get a green "View" badge; unbuilt items show "Coming soon" and are non-interactive. Press Enter to jump to the first available match.

## Notes on extending

When you add the next 8 condition pages, they'll live at `/[slug].html` (matching the search slugs in the JS). Setting `available: true` in the conditions array unlocks them in search.

For example, after building `mosquito-bites.html`:
```js
{ name: "Mosquito bites", slug: "mosquito-bites", region: "Skin", available: true }
```

## Fonts

The page loads Newsreader (serif) and Inter (sans) from Google Fonts. First load takes ~200ms; subsequent loads are cached.

## What's not in this prototype

No real analytics. No actual affiliate tracking IDs (Amazon links go to search results). No SEO meta tags beyond title and description. No structured data. These all belong in v1 of the real site, not the demo.
