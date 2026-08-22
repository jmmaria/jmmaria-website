# jmmaria.com

UGC & branded content portfolio for JM Maria — travel and lifestyle content
creator, Dubai. Static site, no build step.

## Structure

    index.html          Portfolio: work, capabilities, reach, process, inquiry
    style.css           Whole design system. Every page loads this.
    uae/                Market page — Dubai & UAE (9 venues)
    thailand/           Market page — Thailand (6 properties)
    france/             Market page — France (2 properties)
    agoda/              Agoda Ambassador
    klook/              Klook Kreator + JMMARIAKLOOK code
    amazon/             Amazon storefront
    buymeacoffee/       Support page
    links/              Link-in-bio

## Design system

All tokens live in `:root` at the top of `style.css`. Change them there and the
whole site follows.

    --ink     #141416   near-black
    --paper   #E8E8E6   page ground
    --bone    #F4F4F0   raised surface
    --stone   #86867E   secondary text
    --wine    #5A2A2E   the one accent, used sparingly

Type: Instrument Serif (display) / Instrument Sans (body) / IBM Plex Mono
(labels and spec sheets), all from Google Fonts.

## Still to supply

1. **Client logos** — `index.html`, Partners section. Four `<div class="slot">`
   placeholders. Replace each with `<img src="..." alt="Brand name">`.
2. **Rate card** — currently a `mailto:` CTA. No pricing is published anywhere.
3. **Photography** — the site runs on YouTube embeds only. A portrait in the
   hero or on `/links` would lift it.

## Notes

- Removed: Tailwind CDN, Font Awesome, the custom cursor, the marquee tickers,
  the iframe `chapter-*.html` architecture (folded into `index.html`), and all
  emoji.
- `Hijrnotes`, `Daily` and `JaneAust` font files are no longer referenced. Safe
  to delete if unused elsewhere.
- Third-party embeds preserved as-is: Elfsight app IDs, all Klook widget
  `data-adid`/`data-cid` values, the Agoda link, the Formspree form action.
