# HubSpot build spec: The Perpetual Wealth Podcast landing page

**Status:** Mockup only. Do not publish until Rachel approves.  
**Mockup:** https://rglaittli.github.io/upcoming-campaigns/podcast-landing-page/  
**Production URL / slug:** `https://paradigmlife.net/podcast/` (replace the current WordPress page)  
**Owner for publish OK:** Rachel (launches). Patrick for concept. Trinity for copy. Whitney for compliance before launch.

---

## SEO / AEO (production HubSpot ONLY)

### Critical robots / indexing rule
- **GitHub Pages mockup stays `noindex,nofollow`** with the draft footer. Do not index the mockup.
- **In HubSpot production:** remove the robots noindex. Set indexable. Add the canonical below.
- Share image file to upload in HubSpot: `og-share.png` (1200×630) from the mockup folder (also `og-share.webp`).

### Exact title / meta / slug / canonical
| Field | Value |
|---|---|
| Title tag | `Perpetual Wealth Podcast | Patrick Donohoe` (42 chars) |
| Meta description | `Listen to The Perpetual Wealth Podcast with Patrick Donohoe. Weekly episodes on cash flow, financial freedom, and rebuilding the system under stress.` (149 chars) |
| Slug | `/podcast` |
| Canonical | `https://paradigmlife.net/podcast/` |
| OG image | `https://paradigmlife.net/podcast/og-share.png` (upload asset; update absolute URL if HubSpot CDN path differs) |

### Primary / secondary keywords (intent-ranked; no invented volumes)
No paid search-volume tool was available this pass. Ranked by brand intent and competitor-page patterns:

1. **Primary:** `perpetual wealth podcast` (branded navigational; must win)
2. **Secondary:** `patrick donohoe podcast` (host navigational)
3. **Secondary:** `cash flow podcast` (high topical fit to current episodes)
4. **Secondary:** `financial freedom podcast` / `wealth podcast` (category; competitive)
5. **Affinity (use carefully in FAQ/body, not as primary H1):** `infinite banking podcast`, `whole life insurance podcast` (topic overlap; page frames them as system conversations, not product pitches)

Current live WP page title/meta are weak: title `Podcast - Paradigm Life`; description mentions "Paradigm Life and Wealth Standard podcast" and is stale. Replace entirely.

### 301 / feed replacement notes
- Keep URL `https://paradigmlife.net/podcast/` so existing backlinks stay. If HubSpot must use `learn.paradigmlife.net/podcast`, 301 from paradigmlife.net/podcast to the HubSpot URL and set canonical to the final public URL.
- **Replace all old Libsyn / old Apple (id 1494982325) / old Spotify (show/2h4fJ5RGR5QsoMrLOB8SVs) links** with the new Riverside feed and current platform IDs (table below).

### Head HTML to paste (production: NO noindex)

```html
<meta name="description" content="Listen to The Perpetual Wealth Podcast with Patrick Donohoe. Weekly episodes on cash flow, financial freedom, and rebuilding the system under stress.">
<link rel="canonical" href="https://paradigmlife.net/podcast/">
<meta property="og:type" content="website">
<meta property="og:site_name" content="Paradigm Life">
<meta property="og:title" content="Perpetual Wealth Podcast | Patrick Donohoe">
<meta property="og:description" content="Listen to The Perpetual Wealth Podcast with Patrick Donohoe. Weekly episodes on cash flow, financial freedom, and rebuilding the system under stress.">
<meta property="og:url" content="https://paradigmlife.net/podcast/">
<meta property="og:image" content="https://paradigmlife.net/podcast/og-share.png">
<meta property="og:image:width" content="1200">
<meta property="og:image:height" content="630">
<meta name="twitter:card" content="summary_large_image">
<meta name="twitter:title" content="Perpetual Wealth Podcast | Patrick Donohoe">
<meta name="twitter:description" content="Listen to The Perpetual Wealth Podcast with Patrick Donohoe. Weekly episodes on cash flow, financial freedom, and rebuilding the system under stress.">
<meta name="twitter:image" content="https://paradigmlife.net/podcast/og-share.png">
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@type": "Organization",
      "@id": "https://paradigmlife.net/#organization",
      "name": "Paradigm Life",
      "url": "https://paradigmlife.net/",
      "logo": "https://paradigmlife.net/wp-content/uploads/paradigm-life-logo.png"
    },
    {
      "@type": "Person",
      "@id": "https://paradigmlife.net/podcast/#patrick-donohoe",
      "name": "Patrick Donohoe",
      "jobTitle": "CEO",
      "worksFor": {
        "@id": "https://paradigmlife.net/#organization"
      },
      "url": "https://paradigmlife.net/podcast/",
      "sameAs": [
        "https://www.youtube.com/@ParadigmLife",
        "https://open.spotify.com/show/08iIRqJgT7X9UnbrHGF9A3",
        "https://podcasts.apple.com/us/podcast/the-perpetual-wealth-podcast/id265016383"
      ]
    },
    {
      "@type": "PodcastSeries",
      "@id": "https://paradigmlife.net/podcast/#series",
      "name": "The Perpetual Wealth Podcast",
      "description": "Weekly conversations with Patrick Donohoe on cash flow, financial freedom, and rebuilding the financial system most people never chose.",
      "url": "https://paradigmlife.net/podcast/",
      "webFeed": "https://api.riverside.com/hosting/abvBf7Gm.rss",
      "author": {
        "@id": "https://paradigmlife.net/podcast/#patrick-donohoe"
      },
      "publisher": {
        "@id": "https://paradigmlife.net/#organization"
      },
      "inLanguage": "en-US",
      "image": "https://paradigmlife.net/podcast/og-share.png"
    },
    {
      "@type": "PodcastEpisode",
      "@id": "https://paradigmlife.net/podcast/#e486",
      "name": "E.486 Cash Flow is the Gate",
      "datePublished": "2026-11-06",
      "description": "Net worth is the number most people are taught to track. Patrick Donohoe and Wealth Strategist Jaden Zubal make the case that cash flow is the real gate every dollar passes through.",
      "url": "https://www.youtube.com/watch?v=VHeVcar4oCg",
      "timeRequired": "PT50M40S",
      "episodeNumber": 486,
      "partOfSeries": {
        "@id": "https://paradigmlife.net/podcast/#series"
      },
      "author": {
        "@id": "https://paradigmlife.net/podcast/#patrick-donohoe"
      }
    },
    {
      "@type": "PodcastEpisode",
      "@id": "https://paradigmlife.net/podcast/#e485",
      "name": "E.485 Write Your Own Rules",
      "datePublished": "2026-10-30",
      "description": "Patrick unpacks the pull between certainty and uncertainty, and how writing your own rules changes how you experience both.",
      "url": "https://www.youtube.com/watch?v=eOf9bsAOU9U",
      "timeRequired": "PT28M25S",
      "episodeNumber": 485,
      "partOfSeries": {
        "@id": "https://paradigmlife.net/podcast/#series"
      },
      "author": {
        "@id": "https://paradigmlife.net/podcast/#patrick-donohoe"
      }
    },
    {
      "@type": "PodcastEpisode",
      "@id": "https://paradigmlife.net/podcast/#e484",
      "name": "E.484 Are You Investing or Just Gambling?",
      "datePublished": "2026-10-26",
      "description": "Patrick and John Stewart dig into control, rate of return fixation, and the difference between a financial picture and a plan that only works if every assumption holds.",
      "url": "https://podcasts.apple.com/us/podcast/e-484-are-you-investing-or-just-gambling/id265016383?i=1000798223025",
      "timeRequired": "PT27M24S",
      "episodeNumber": 484,
      "partOfSeries": {
        "@id": "https://paradigmlife.net/podcast/#series"
      },
      "author": {
        "@id": "https://paradigmlife.net/podcast/#patrick-donohoe"
      }
    },
    {
      "@type": "PodcastEpisode",
      "@id": "https://paradigmlife.net/podcast/#e483",
      "name": "E.483 How Healthy Is Your Financial Picture? Taking the WealthScore Together",
      "datePublished": "2026-10-16",
      "description": "A walkthrough of WealthScore as a short self-assessment of cash flow, protection, and asset allocation across Certainty, Vitality, Independence, and Freedom.",
      "url": "https://www.youtube.com/watch?v=Uu2qa6zXfVk",
      "timeRequired": "PT34M35S",
      "episodeNumber": 483,
      "partOfSeries": {
        "@id": "https://paradigmlife.net/podcast/#series"
      },
      "author": {
        "@id": "https://paradigmlife.net/podcast/#patrick-donohoe"
      }
    },
    {
      "@type": "FAQPage",
      "@id": "https://paradigmlife.net/podcast/#faq",
      "mainEntity": [
        {
          "@type": "Question",
          "name": "What is The Perpetual Wealth Podcast?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "The Perpetual Wealth Podcast is a weekly show hosted by Patrick Donohoe, CEO of Paradigm Life. Each episode takes one financial tension apart, traces it to its root, and rebuilds what is underneath using the Perpetual Wealth Strategy."
          }
        },
        {
          "@type": "Question",
          "name": "Who hosts The Perpetual Wealth Podcast?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Patrick Donohoe hosts the show. He co-founded Paradigm Life in 2007 and developed the Perpetual Wealth Strategy from patterns across thousands of households."
          }
        },
        {
          "@type": "Question",
          "name": "Where can I listen to The Perpetual Wealth Podcast?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "You can listen on this page via the Spotify player, or on YouTube, Spotify, and Apple Podcasts. The show RSS feed is hosted on Riverside."
          }
        },
        {
          "@type": "Question",
          "name": "What topics does the podcast cover?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Episodes focus on cash flow, protection, asset allocation, and the four dimensions of Certainty, Vitality, Independence, and Freedom."
          }
        },
        {
          "@type": "Question",
          "name": "What is WealthScore?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "WealthScore is a short self-assessment that looks at how your financial picture is working across cash flow, protection, and asset allocation."
          }
        },
        {
          "@type": "Question",
          "name": "Is The Perpetual Wealth Podcast about infinite banking or whole life insurance?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "The show covers cash flow and wealth strategy topics that often include whole life insurance and related frameworks, but every episode starts from a specific financial tension rather than a product pitch."
          }
        },
        {
          "@type": "Question",
          "name": "How often do new episodes publish?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "New episodes publish every week. The Spotify show player on this page updates when a new episode goes live."
          }
        }
      ]
    },
    {
      "@type": "BreadcrumbList",
      "@id": "https://paradigmlife.net/podcast/#breadcrumb",
      "itemListElement": [
        {
          "@type": "ListItem",
          "position": 1,
          "name": "Home",
          "item": "https://paradigmlife.net/"
        },
        {
          "@type": "ListItem",
          "position": 2,
          "name": "Podcast",
          "item": "https://paradigmlife.net/podcast/"
        }
      ]
    }
  ]
}
</script>
```

Schema includes: Organization, Person (Patrick Donohoe), PodcastSeries (webFeed `https://api.riverside.com/hosting/abvBf7Gm.rss`), PodcastEpisode (E.486–E.483), FAQPage, BreadcrumbList. Validate after paste (Rich Results Test).

### On-page SEO checklist for HubSpot modules
- One H1 (hero). Logical H2/H3s matching mockup.
- Crawlable episode list with titles, dates, short summaries (do not rely on iframes for indexing).
- FAQ accordion (7 questions) matching FAQPage schema.
- Internal links: WealthScore™ portal, Wealth Strategist consult, episode platform URLs, YouTube.
- Descriptive alt text on logo, host photo, thumbs, covers.
- Lazy-load Spotify iframe + images; width/height attrs; prefer WebP assets.
- Sticky header scroll-margin on `#listen #watch #episodes #host #faq`.

---

## Round notes (Nov 9, 2026)

### Header / nav
- Slim **sticky** top bar, thin bottom border, dark translucent background.
- Horizontal lockup ~**36px tall** desktop / ~30px mobile (not the previous oversized logo).
- Right-side on-page nav: Listen, Watch, Episodes, About Patrick, FAQ + small green WealthScore™ pill.
- Mobile: hamburger toggle. Smooth scroll with `scroll-margin-top` for sticky offset.

### Quote strip (final 7)
See `QUOTE-SOURCES.md`. Removed write-certain-rules and straight-lines quotes. E.484 uses accumulation/net-worth line (distinct theme).

### Design tokens (PWP dark)
```css
--pwp-bg: #000000;
--pwp-surface: #121212;
--pwp-text: #FFFFFF;
--pwp-muted: #9A9A9A;
--pwp-line: #2C2C2C;
--pwp-accent: #D4A80E;
--ws-fill: #58813d;
--ws-ring: #73a950;
```

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
Playlist: `PL6ZUhtyHuVhFnPyTljFU4SmhOzaZYnqKh`

---

## Embeds

### Spotify (auto-updates)
```html
<iframe
  title="The Perpetual Wealth Podcast on Spotify"
  src="https://open.spotify.com/embed/show/08iIRqJgT7X9UnbrHGF9A3?utm_source=generator&theme=0"
  width="100%" height="352" frameborder="0"
  allow="autoplay; clipboard-write; encrypted-media; fullscreen; picture-in-picture"
  loading="lazy"></iframe>
```

### WealthScore™ CTA
- URL: `https://portal.paradigmlife.net/wealthscore?utm_source=podcast-page&utm_medium=referral&utm_campaign=podcast-lp`
- Label: short self-assessment (never "free")
- Strategist: `https://learn.paradigmlife.net/or-lib-consultation-request?utm_source=podcast-page&utm_medium=referral&utm_campaign=podcast-lp`

### Wording rules
- No em dashes. No guarantees. No tax advice.
- "livestream" not "webinar".
- Dimensions: Certainty / Vitality / Independence / Freedom.
- Pillars: Cash Flow / Protection / Asset Allocation.
- WealthScore™ = short self-assessment.

---

## Module map (HubSpot)
1. Sticky header (logo + nav + WealthScore pill)
2. Hero (copy left, ghosted shield right)
3. Spotify player full width
4. Quote strip (7 slides)
5. Platform buttons
6. What you will hear (3 cards)
7. YouTube thumbnail cards (3)
8. Host
9. Recent episodes (crawlable HTML + summaries)
10. FAQ (8)
11. WealthScore / Strategist CTA + email form placeholder
12. Footer

Trinity copy review Doc is separate (Rachel Drive). Do not publish until Trinity + Whitney sign off.

## Trinity copy fixes (Nov 9, 2026)
- FAQ A4: remove duplicate "financial freedom" before the Freedom dimension. Use: "Cash flow, protection, asset allocation, and the four dimensions of Certainty, Vitality, Independence, and Freedom."
- Replace "nearly two decades" with **"nearly nearly two decades"** (co-founded 2007) everywhere on page (What you will hear card, host/FAQ if present).

## Header / hero (Rachel visual pass)
- Sticky header uses **shield mark only** (`pwp-shield-mark-white.png`), ~38px tall. Not the full horizontal lockup.
- Hero places the **full horizontal white lockup** above the Listen button.
- Ghosted shield is **massive** (absolute, overflow cropped, opacity ~0.07), including mobile.
- YouTube section: **do not change** without Rachel asking. Landscape 16:9 custom-thumb cards, H2 "Watch on YouTube", **no** "custom thumbnails / auto frames" lede.

## Production checklist (HubSpot publish)
- [ ] Remove `noindex,nofollow` robots meta (mockup keeps it; production must be indexable).
- [ ] Strip **Draft for internal review** pill and internal draft footer/banner.
- [ ] Set canonical `https://paradigmlife.net/podcast/` (or final chosen host) + OG image absolute URL.
- [ ] Paste JSON-LD schema from this spec; validate in Rich Results Test.
- [ ] Replace old Libsyn / old Apple / old Spotify links with Riverside + current IDs.
- [ ] **Listen-through of quote strip quotes 1–7 against episode audio** before publish (sources in QUOTE-SOURCES.md).
- [ ] Whitney compliance + Trinity copy sign-off.

## FAQ copy (Rachel Nov 9, 2026 — 8 questions)

**1. What is The Perpetual Wealth Podcast about?**  
Each episode takes a familiar financial tension, looks at what is driving it, and explores how to make better decisions about it. The show is not a tips list. It is a weekly look at the system underneath money stress, hosted by Patrick Donohoe of Paradigm Life.

**2. Who hosts The Perpetual Wealth Podcast?**  
Patrick Donohoe, co-founder and CEO of Paradigm Life, hosts The Perpetual Wealth Podcast. He is frequently joined by fellow wealth strategists, colleagues, and outside experts.

**3. Who is The Perpetual Wealth Podcast for?**  
It is for people who want to understand how everyday decisions about cash flow, housing, investing, and retirement fit together. You do not need to be wealthy to listen. You need to be serious about seeing the full picture.

**4. What topics does The Perpetual Wealth Podcast cover?**  
Episodes cover cash flow, home equity and liquidity, family and money, investing versus gambling, and how investors read economic news. Start with E.477 House Rich, Cash Poor (https://podcasts.apple.com/us/podcast/e-477-house-rich-cash-poor/id265016383?i=1000786355797), E.478 The Family Fight (https://podcasts.apple.com/us/podcast/e-478-the-family-fight/id265016383?i=1000786355633), or E.475 The Investor's Read: Jobs, Market Sentiment + the Fear Paradox (https://podcasts.apple.com/us/podcast/e-475-the-investors-read-jobs-market-sentiment-the/id265016383?i=1000786355579).

**5. Which episode should I start with?**  
If most of your wealth is tied up in your home, start with E.477 House Rich, Cash Poor (https://podcasts.apple.com/us/podcast/e-477-house-rich-cash-poor/id265016383?i=1000786355797). If you want a clearer read on where you stand, listen to E.483 How Healthy Is Your Financial Picture? (https://podcasts.apple.com/us/podcast/e-483-how-healthy-is-your-financial-picture-taking/id265016383?i=1000796701914). If cash flow is the open question, start with E.486 Cash Flow is the Gate (https://podcasts.apple.com/us/podcast/e-486-cash-flow-is-the-gate/id265016383?i=1000800322683). If you want the 4321 system laid out, start with E.481 Why Skipping Ahead Never Actually Gets You Ahead (https://podcasts.apple.com/us/podcast/e-481-why-skipping-ahead-never-actually-gets-you-ahead/id265016383?i=1000792906552).

**6. Where can I listen to or watch The Perpetual Wealth Podcast?**  
Listen on Apple Podcasts (https://podcasts.apple.com/us/podcast/the-perpetual-wealth-podcast/id265016383) or Spotify (https://open.spotify.com/show/08iIRqJgT7X9UnbrHGF9A3), or watch the YouTube All Episodes playlist (https://www.youtube.com/playlist?list=PL6ZUhtyHuVhFnPyTljFU4SmhOzaZYnqKh). You can also use the Spotify player on this page.

**7. How often are new episodes released?**  
New episodes publish weekly. Follow the show on Apple Podcasts (https://podcasts.apple.com/us/podcast/the-perpetual-wealth-podcast/id265016383), Spotify (https://open.spotify.com/show/08iIRqJgT7X9UnbrHGF9A3), or the YouTube playlist (https://www.youtube.com/playlist?list=PL6ZUhtyHuVhFnPyTljFU4SmhOzaZYnqKh) so new episodes show up automatically.

**8. What is the Perpetual Wealth Strategy, and how does it relate to the podcast?**  
The Perpetual Wealth Strategy is Paradigm Life's approach to building, protecting, and using wealth as one connected system across cash flow, protection, and asset allocation. The podcast is where Patrick works through the tensions that show up inside that system. For a deeper overview, read The Perpetual Wealth Strategy (https://paradigmlife.net/perpetual-wealth-strategy-grow-wealth/).


Also keep FAQPage JSON-LD in page head in sync with these eight Q&As.

### FAQ revision (same day)
- Q2: Patrick only; joined by wealth strategists/colleagues/experts (no other names).
- Q5: plain sentences (no arrows); added E.481 as 4321-system starting point (no episode titled "4321" found; E.481 Apple description covers the framework).
- Strategy link (FAQ Q8): https://paradigmlife.net/perpetual-wealth-strategy-grow-wealth/

### Strategy URL swap (Nov 9, 2026)
- FAQ Q8 and related links now point to https://paradigmlife.net/perpetual-wealth-strategy-grow-wealth/ (Rachel). Verified HTTP 200.
