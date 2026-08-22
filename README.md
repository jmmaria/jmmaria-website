# jmmaria.com

UGC & branded content portfolio for JM Maria — travel and lifestyle content
creator, Dubai. Static site, no build step.

## Structure

    index.html          One page: About me / Video / Photography / Clients / Contact
    style.css           Whole design system. Every page loads this.
    services/           Ongoing & retainer services (unlisted from main nav)
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

## Homepage structure

    #about        About me — portrait, bio, what I make, audience numbers
    #video        Video examples — intro
      #video-hotels    10 hotel & resort films (filterable by market)
      #video-venues    9 Dubai café & venue films
      #video-short     live TikTok + Instagram feeds
    #photography  Photography examples — 6 gallery slots
    #clients      Previous clients — logo wall + Agoda / Klook programmes
    #contact      Contact me — form, details, three-step "what happens next"
    #shop         Book & shop — affiliate links

Nav is About / Video / Photography / Clients / Book & shop / Contact.

## Still to supply

1. **Photography** — `#photography` has six 4:5 placeholder slots and no real
   images. Add files to `/photos/` and swap each
   `<div class="slot slot--shot">` for `<img src="/photos/01.jpg" alt="...">`.
   The grid, ratio and hover are already styled. Until these are filled the
   section advertises a service with nothing behind it, so either add stills
   or delete the section.
2. **Portrait** — `index.html`, About section. Drop a 4:5 image at
   `/portrait.jpg` and replace the `<div class="slot slot--portrait">` with
   `<img src="/portrait.jpg" alt="JM Maria">`. Styling is already there. This
   is the single highest-value addition: brands hiring a UGC creator are
   hiring a person.
3. **Rate card** — currently a `mailto:` CTA. No pricing is published anywhere.
4. **Bio accuracy** — the About copy is written from facts already on the old
   site (Dubai-based, 10 properties, 5 countries, 9 Dubai venues, solo
   pipeline). Anything about how long you've been filming, your kit, or where
   you're from was left out rather than guessed. Add it if you want it.

## Brand logos

`/brands/` holds the client marks used in the Partners section. Each source
screenshot was background-knocked-out and flattened to a single ink tone
(`--ink`) so the wall reads as one row rather than three competing brand
palettes.

Sizing is by **equal optical area**, not equal height — a wide wordmark set to
the same height as a stacked mark looks twice as big. Each `<img>` carries an
inline `--w` equal to its natural width x 0.34. To add a logo:

1. Knock out the background, flatten to `#141416`, trim, and scale so
   `width x height` is roughly 34,000px.
2. Add `<div class="wall__i"><img src="/brands/NAME.png" alt="Brand"
   style="--w:Xpx"></div>` where X is the new file's natural width x 0.34.

Currently on the wall: Flowwow, Lorealistar, Casa Barkada Salon.

Logos are shown at 55% opacity, full on hover. If any brand's guidelines
require full colour, drop the original PNG into `/brands/` and remove that
image's opacity rule.

## OG image

`og-image.jpg` was regenerated to match the new design. `og-image.html` is the
source: open it, screenshot the `.og` box at exactly 1200×630, save over
`og-image.jpg`. The committed JPG was rendered with a substitute serif, so
regenerate it once for correct Instrument Serif.

## Ongoing services page

`/services` covers social media management, content strategy, content creation
for client channels, and virtual assistant work. It is deliberately kept off
the homepage and out of the main nav, so the film portfolio stays the first
impression for hospitality clients. It is reachable from:

- the footer "Inquiries" column on every page
- one line at the end of the homepage Capabilities section
- a row in the homepage inquiry contact table
- the "For brands" set on `/links`
- two extra options in the inquiry form dropdown, so retainer leads route

To promote it later, add `<a href="/services">Ongoing services</a>` to the
`.nav__links` block in `index.html`.

## Notes

- Removed: Tailwind CDN, Font Awesome, the custom cursor, the marquee tickers,
  the iframe `chapter-*.html` architecture (folded into `index.html`), and all
  emoji.
- `Hijrnotes`, `Daily` and `JaneAust` font files are no longer referenced. Safe
  to delete if unused elsewhere.
- Third-party embeds preserved as-is: Elfsight app IDs, all Klook widget
  `data-adid`/`data-cid` values, the Agoda link, the Formspree form action.
