# HubSpot build spec: The Perpetual Wealth Podcast landing page

**Status:** Mockup only. Do not publish until Rachel approves.  
**Mockup:** https://rglaittli.github.io/upcoming-campaigns/podcast-landing-page/  
**Suggested HubSpot slug:** `/podcast` on `learn.paradigmlife.net` (replace or redirect the WordPress `paradigmlife.net/podcast/` page later).  
**Domain:** learn.paradigmlife.net  
**Owner for publish OK:** Rachel (launches). Patrick for concept.

---

## Critical: use the NEW feed, not the WordPress page

The live WordPress page at https://paradigmlife.net/podcast/ still points at the **old** show.

| | Old (do not use) | New (use this) |
|---|---|---|
| Show name | The Perpetual Wealth **Strategy** Podcast (and older Wealth Standard branding) | **The Perpetual Wealth Podcast** |
| Host | Libsyn (legacy) | **Riverside** |
| RSS | Old Libsyn feed | https://api.riverside.com/hosting/abvBf7Gm.rss |
| Apple | https://podcasts.apple.com/.../id**1494982325** | https://podcasts.apple.com/us/podcast/the-perpetual-wealth-podcast/id**265016383** |
| Spotify | https://open.spotify.com/show/**2h4fJ5RGR5QsoMrLOB8SVs** | https://open.spotify.com/show/**08iIRqJgT7X9UnbrHGF9A3** |
| Latest verified | Stale / Season 1–3 archive on WP | **E.486 Cash Flow is the Gate** (pub Fri Nov 6, 2026) |

YouTube channel (video): https://www.youtube.com/@ParadigmLife  
All-episodes playlist: https://www.youtube.com/playlist?list=PL6ZUhtyHuVhFnPyTljFU4SmhOzaZYnqKh

---

## Page goal

A listen / watch hub. Hero promise, **embedded player for the latest episode**, platform buttons, short “what you’ll hear,” host, a few recent episodes, one soft WealthScore™ CTA. Keep the Perpetual Wealth Podcast brand separate from Paradigm Life marketing pages and from FO360.

---

## Brand tokens (PWP dark)

Taken from the official logo + episode cover art, with one gold accent borrowed from recent dark YouTube thumbnails (e.g. E.483).

```css
--pwp-bg: #000000;
--pwp-bg-2: #0A0A0A;
--pwp-surface: #121212;
--pwp-surface-2: #1A1A1A;
--pwp-text: #FFFFFF;
--pwp-muted: #9A9A9A;
--pwp-ghost: #2A2A2A;   /* ghosted shield behind type */
--pwp-line: #2C2C2C;
--pwp-accent: #D4A80E;  /* restrained gold highlight only */
```

**Type (Montserrat):**
- `THE PERPETUAL` — weight 300, letter-spacing ~0.42em, all caps
- `WEALTH` — weight 900, tight tracking, all caps
- `PODCAST` — weight 300, letter-spacing ~0.55–0.58em, all caps
- Body / UI — Montserrat 400/600/700
- Episode numbers (`E.486`) — Montserrat 800/900, large, white

**Logo assets (source of truth):**
- `/workspace/podcast-lp/assets/pwp-logo.png` (shield + mic + rising bars, white on black)
- `/workspace/podcast-lp/assets/pwp-episode-cover-e480.png` (ghosted shield + stacked wordmark + big episode number)

Do **not** use FO360 jade, soft cream WYOR backgrounds, or the Paradigm Life green wash as the page field. PWP is intentionally black. Color is highlight-only (thin accent line, play/episode number, button hover).

**Platform buttons:** white outline on black, pill shape, fill white / text black on hover.  
**WealthScore™ CTA:** same outline style (understated), not a loud green fill.

---

## Recommended embed (auto-updates)

### Primary: Spotify show embed (preferred for HubSpot)

Auto-updates to the latest episode. No weekly edit.

```html
<iframe
  title="The Perpetual Wealth Podcast on Spotify"
  src="https://open.spotify.com/embed/show/08iIRqJgT7X9UnbrHGF9A3?utm_source=generator&theme=0"
  width="100%"
  height="352"
  frameborder="0"
  allow="autoplay; clipboard-write; encrypted-media; fullscreen; picture-in-picture"
  loading="lazy"></iframe>
```

- `theme=0` = dark player (matches the page).
- Height `152` = compact; `352` = show player with episode list (recommended).

### Alternative: Riverside episode embed

Riverside supports single-episode embeds only (no playlist). The embed code stays stable if you **Replace file** on that embed each week so the same code always plays the latest. Requires a HubSpot HTML module and a weekly ops step. Docs: Riverside Help → Embed a video or podcast episode.

### Not recommended

- Anything scraped from paradigmlife.net/podcast/ (old Apple/Spotify IDs).
- A hard-coded episode Spotify/Apple embed that must be swapped by hand every week unless ops owns it.

---

## Suggested HubSpot modules / structure

1. **Global / page settings**
   - Background `#000`
   - Custom CSS with the tokens above
   - Meta title / description (below)
   - Favicon: PWP shield crop if available

2. **Header**
   - PWP logo + stacked wordmark (or logo alone)
   - No Paradigm Life wordmark in the header (keep PWP separate)

3. **Hero**
   - Eyebrow: “New episodes every week” (accent color)
   - H1 stacked wordmark style
   - One-line promise (lean copy from June draft, shortened)
   - Optional ghosted episode-cover treatment behind / beside hero

4. **Player (HTML module)**
   - Spotify show embed above
   - Label: “Listen here” / “Latest episode”

5. **Watch or listen row**
   - Buttons: YouTube, Spotify, Apple Podcasts, All episodes (playlist)
   - URLs in the table at the top of this doc

6. **What you’ll hear** (3 cards)
   - One theme · Framework not opinion · Patterns from real households

7. **Host**
   - Patrick Donohoe, CEO, Paradigm Life
   - Short bio (no guarantees, no tax advice)

8. **Recent episodes** (manual or HubDB later)
   - Seed with E.486–E.483
   - Each card: art, `E.###`, title, duration, links to YT / Apple / Spotify
   - Style: black card, bold episode number over art (match cover art)

9. **Soft CTA**
   - WealthScore™ short self-assessment  
     `https://portal.paradigmlife.net/wealthscore?utm_source=podcast-page&utm_medium=referral&utm_campaign=podcast-lp`
   - Optional secondary: strategist consult (existing learn.paradigmlife.net form)
   - Optional HubSpot email form for “new episode” list (placeholder in mockup)

---

## Meta (draft)

- **Title:** The Perpetual Wealth Podcast | Patrick Donohoe  
- **Description:** Listen to the latest episode of The Perpetual Wealth Podcast. Patrick Donohoe takes one financial tension apart each week. Watch on YouTube or listen on Spotify and Apple Podcasts.  
- **OG image:** PWP logo square or latest episode cover from Riverside

---

## Wording rules (Rachel)

- Say “livestream,” never “webinar.”
- No em dashes.
- No guarantees or tax advice.
- Write **WealthScore™** and call it a **short self-assessment**, not “free.”
- No Avalaunch mention.
- Keep PWP brand separate from FO360 and from standard Paradigm Life cream/green marketing pages.

---

## Copy sources

- Lean rewrite of June draft: Google Doc `pws-podcast-lp__landing_page`  
  https://docs.google.com/document/d/1DJo6i9chmFKLySbXHCiKaRj6o1zdCAWlTsIJzPyMj70/edit  
- Show description: Riverside RSS / Apple / Spotify (aligned).

---

## Launch checklist

- [ ] Rachel approves mockup design + copy
- [ ] Confirm HubSpot slug (`/podcast` vs new path) and whether WP `/podcast/` redirects
- [ ] Paste Spotify show embed; confirm latest episode plays
- [ ] Platform buttons use **new** Apple/Spotify IDs
- [ ] WealthScore™ UTM link live
- [ ] Email form (if any) connected to HubSpot list
- [ ] Trinity / compliance if required for public page
- [ ] Rachel publish OK (HubSpot is build-by-human; Grok Bot is read-only there)
