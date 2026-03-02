# AGENTS.md — Cypherpunk Theme

## What This Is
A custom Jekyll theme for 757btc.org — a Bitcoin meetup group in Hampton Roads, VA.
The site currently uses `sylhare/Type-on-Strap` as a remote theme. We're replacing it with this standalone theme.

## Design Direction
- **Cypherpunk terminal aesthetic** — dark background, green phosphor (#00ff41), monospace fonts, sharp corners
- **Bitcoin orange (#f7931a)** as accent
- **CRT scan line effect** — subtle, not distracting
- **HUD overlay on hero** — live Bitcoin network data (block height, price, fees) from mempool.space API
- **Terminal vibe** — `root@757btc:~$` prompt, targeting brackets, grid overlay
- **Responsive** — must work on mobile

## Reference
- `reference/` dir has CSS/JS/HTML from the original prototype (by pfoytik/theGig)
- The prototype was an overlay hack on top of Type-on-Strap — we're doing this as a proper standalone theme
- Hero image: `assets/img/cypherpunk_mermaid.jpeg`

## Content
- `_posts/` has all existing meetup announcement posts from the live site
- `_data/authors.yml` has author info
- `.well-known/nostr.json` has NIP-05 verification data

## What Needs Work
The initial build was done quickly by a coding agent. Review everything for:
1. **Jekyll compatibility** — does it actually build and render correctly?
2. **CSS quality** — clean up any rough spots, make sure layouts work at all breakpoints
3. **HUD overlay** — the JS fetches from mempool.space API. Make sure it degrades gracefully if API is down
4. **Post layout** — individual post pages need to look good
5. **Navigation** — header nav should work properly
6. **Pagination** — uses jekyll-paginate
7. **Author display** — posts should show author info from _data/authors.yml
8. **Google Maps embed** — some posts have iframe embeds for meetup locations
9. **nostr.json** — must be served correctly at /.well-known/nostr.json

## Build
```
bundle install
bundle exec jekyll serve
```
Open http://localhost:4000

## DO NOT
- Change the design direction (dark/green/terminal aesthetic)
- Remove the CRT or HUD effects
- Add external CSS frameworks (Bootstrap, Tailwind, etc.)
- Change content in _posts/ (those are production posts)
