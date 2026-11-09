# HubSpot build spec: The Perpetual Wealth Podcast landing page

**Status:** Mockup only. Do not publish until Rachel approves.  
**Mockup:** https://rglaittli.github.io/upcoming-campaigns/podcast-landing-page/  
**Suggested HubSpot slug:** `/podcast` on `learn.paradigmlife.net`  
**Owner for publish OK:** Rachel (launches). Patrick for concept.

---

## Round 3 mockup notes (Nov 9, 2026)

- Header uses horizontal lockup: `/workspace/pwp-banner/pwp_horizontal_white_transparent.png` (copied to mockup as `pwp-lockup-horizontal-white.png`). White on transparent for the black page.
- Hero is taller: copy left + large ghosted shield right. Spotify is **full width** under the hero (height 352).
- YouTube section: **no big iframe**. Three custom-thumbnail cards only.

- Quote strip: skinny auto-slider between Spotify player and “What you will hear”; gold quote mark; 6s auto-advance; pause on hover; swipe on mobile; respects prefers-reduced-motion. Sources in QUOTE-SOURCES.md.
- Host photo: Rachel-selected AI placeholder (mic behind him), `patrick-host.jpg`.
- E.486 custom YouTube thumbnail (blue, EP. 486): `/workspace/thumbnails/ep486/E486-cash-flow-is-the-gate.png` (1280×720). Live YouTube `VHeVcar4oCg` maxres currently shows an **auto video frame** of Patrick (not this custom art). Rachel can re-upload the custom thumb in YouTube Studio; mockup already uses our file on the card.
- Ghosted shield background retained; no episode cover in the hero.

---

## Critical: use the NEW feed, not the WordPress page

| | Old (do not use) | New (use this) |
|---|---|---|
| Show name | The Perpetual Wealth **Strategy** Podcast | **The Perpetual Wealth Podcast** |
| Host | Libsyn (legacy) | **Riverside** |
| RSS | Old Libsyn feed | https://api.riverside.com/hosting/abvBf7Gm.rss |
| Apple | id**1494982325** | id**265016383** |
| Spotify | show/**2h4fJ5RGR5QsoMrLOB8SVs** | show/**08iIRqJgT7X9UnbrHGF9A3** |
| Latest verified | Stale archive on WP | **E.486 Cash Flow is the Gate** (Nov 6, 2026) |

YouTube channel: https://www.youtube.com/@ParadigmLife  
All-episodes playlist: `PL6ZUhtyHuVhFnPyTljFU4SmhOzaZYnqKh` (see YouTube section: **not** safe for auto-latest today)

---

## Brand tokens (PWP dark)

```css
--pwp-bg: #000000;
--pwp-bg-2: #0A0A0A;
--pwp-surface: #121212;
--pwp-text: #FFFFFF;
--pwp-muted: #9A9A9A;
--pwp-line: #2C2C2C;
--pwp-accent: #D4A80E;   /* gold highlight only (from E.483 YT art) */
--ws-fill: #58813d;      /* WealthScore CTA only */
--ws-ring: #73a950;      /* WealthScore CTA ring only */
```

**Wordmark / logo**
- Do **not** typeset “THE PERPETUAL / WEALTH / PODCAST” in HubSpot.
- Use the official logo PNG (shield + wordmark) as an image. Source: `/workspace/podcast-lp/assets/pwp-logo.png` (mockup uses cropped `pwp-logo-full.png`).
- Ghosted background: shield only, very low opacity (`pwp-shield-ghost.png`). No episode cover in the hero.

**Font ID (for reference only; logo image is the source of truth)**  
Likely **Gotham** (Paradigm Life brand) or **Montserrat** as a free stand-in. Thin tracked lines ≈ Light/Book (~300); `WEALTH` ≈ Bold (~700), **not** Black/900. Confidence ~65%. Prefer the logo asset so weight and tracking stay exact.

**Platform buttons:** white outline on black.  
**WealthScore™ CTA only:** fill `#58813d`, ring `#73a950`.

**Spacing:** generous page padding (`clamp(28px, 5vw, 48px)` horizontal; large section vertical padding). Keep CTA inner padding roomy, including mobile.

---

## Embeds

### Spotify (keep exactly as mockup; auto-updates)

```html
<iframe
  title="The Perpetual Wealth Podcast on Spotify"
  src="https://open.spotify.com/embed/show/08iIRqJgT7X9UnbrHGF9A3?utm_source=generator&theme=0"
  width="100%" height="352" frameborder="0"
  allow="autoplay; clipboard-write; encrypted-media; fullscreen; picture-in-picture"
  loading="lazy"></iframe>
```

### YouTube section (under “What you will hear”)

**Mockup seeding (Nov 9, 2026):**
- Featured embed: `https://www.youtube.com/embed/VHeVcar4oCg` (E.486)
- Cards: `VHeVcar4oCg` (E.486), `eOf9bsAOU9U` (E.485), `Uu2qa6zXfVk` (E.483)

**Playlist check:** `PL6ZUhtyHuVhFnPyTljFU4SmhOzaZYnqKh` RSS currently returns older videos first and **does not include** E.485/E.486. A `youtube.com/embed/videoseries?list=…` embed would **not** auto-show the latest today.

**Simplest HubSpot auto-update options (pick one):**
1. **Preferred:** Create a dedicated YouTube playlist “PWP Latest” kept **newest-first**, add each full episode when published, embed once with  
   `https://www.youtube.com/embed/videoseries?list=PLAYLIST_ID`  
   HubSpot HTML module; no weekly page edit.
2. **Manual light:** Keep featured iframe + 3 cards; update video IDs weekly from the channel RSS  
   `https://www.youtube.com/feeds/videos.xml?channel_id=UCKmGmR4v96Ia6N494cM1Kgw` (filter out Shorts).
3. HubSpot cannot auto-refresh static video-ID cards without a custom feed module / serverless proxy.

---

## Page modules

1. Header: full PWP logo image + draft not needed in HubSpot  
2. Hero: eyebrow, short H1, promise, CTA to player; ghosted shield background only  
3. Spotify player (HTML)  
4. Watch or listen platform pills (YouTube, Spotify, Apple, All episodes)  
5. What you will hear (3 cards)  
6. Watch on YouTube (featured + 3 cards or playlist embed once curated)  
7. Host (photo placeholder until Rachel supplies)  
8. Recent episodes (Riverside cover art; episode number is **in the art**, do not overlay)  
9. WealthScore™ CTA (green) + HubSpot email form for new-episode list

---

## “What you will hear” copy sources (for Trinity)

| Line | Source |
|---|---|
| Section lede: “This is not a tips show. It is a weekly look at how money actually works in a household, and what changes when you treat it as one connected system.” | **Adapted by Grok Bot** from June Google Doc `pws-podcast-lp__landing_page` (“This isn't a show about tips. It's a show about how money actually works in a household…”) |
| Card title “One theme, explored deeply” | **June Google Doc** (exact heading under “What You'll Hear”) |
| Card body “Every episode anchors on a single idea and stays there long enough to change how you think about it.” | **Adapted by Grok Bot** from June Doc (“Every episode anchors on a single idea and stays there long enough to actually change how you think about it. We don't tour five topics…”) |
| Card title “Framework, not opinion” | **June Google Doc** (exact heading) |
| Card body “Conversations sit inside the Perpetual Wealth Strategy: cash flow, protection, and asset allocation working together.” | **Written by Grok Bot** for the mockup (June Doc talks 4-3-2-1 / pillars at a higher level; this names the three pillars directly) |
| Card title “Patterns from real households” | **Adapted by Grok Bot** from June Doc heading “Real patterns from real households” |
| Card body “Drawn from two decades of work with thousands of families, including what quietly fails and what people rarely ask until it is late.” | **Adapted by Grok Bot** from June Doc (“We've sat across the table from thousands of families… what actually works, what quietly fails, and what most people never think to ask…”) |

Hero promise (“Most financial stress is not a bad investment…”) is adapted from the **Riverside / Apple / Spotify show description** and the current WP podcast page lede (same root copy). Host bio is adapted from the June Doc host section + WP about block, shortened.

---

## Meta (draft)

- **Title:** The Perpetual Wealth Podcast \| Patrick Donohoe  
- **Description:** Listen to the latest episode of The Perpetual Wealth Podcast. Watch on YouTube or listen on Spotify and Apple Podcasts.  
- **OG image:** PWP logo square

## Wording rules

- “livestream,” never “webinar”  
- No em dashes  
- No guarantees or tax advice  
- **WealthScore™** = short self-assessment (not “free”)  
- No Avalaunch  
- Keep PWP dark brand separate from FO360 and cream/green PL marketing pages (except WealthScore CTA green)

## Launch checklist

- [ ] Rachel approves mockup  
- [ ] Patrick photo supplied  
- [ ] Confirm slug / WP redirect  
- [ ] Spotify embed live  
- [ ] YouTube auto-update path chosen (new playlist vs manual)  
- [ ] Platform buttons = **new** Apple/Spotify IDs  
- [ ] WealthScore™ UTM link  
- [ ] HubSpot email form wired  
- [ ] Trinity review of “What you will hear”  
- [ ] Rachel publish OK
