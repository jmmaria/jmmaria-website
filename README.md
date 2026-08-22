# jmmaria.com

Static site, no build step. Two audiences, two front doors:

- **`/`** — the travel/creator site. Films, destination guides, affiliate links.
- **`/ugc`** — the UGC & branded content portfolio. One page, sendable to brands.

## Structure

    index.html          Creator site: about, hotel films, cafés, short-form,
                        destinations, book & shop
    ugc/                UGC portfolio — the link to send to brands
    services/           Ongoing & retainer services (social, strategy, VA)
    style.css           Whole design system. Every page loads this.
    brands/             Client logos, processed to a single ink tone
    uae/ thailand/ france/     Destination guides
    agoda/ klook/ amazon/ buymeacoffee/   Affiliate pages
    links/              Link-in-bio
    og-image.html       Source for og-image.jpg — screenshot at 1200x630

## The split

`/` sells the films to viewers. `/ugc` sells you to brands. They cross-link
once each — "For brands" in the site nav, "Travel site" in the UGC footer —
and otherwise stay out of each other's way.

Send **jmmaria.com/ugc** in pitch emails. It has no affiliate links, no
destination guides and no Buy Me a Coffee, so a marketing lead sees only
audience, brands, work, deliverables and contact.

## Design system

All tokens live in `:root` at the top of `style.css`.

    --ink     #141416   near-black
    --paper   #E8E8E6   page ground
    --bone    #F4F4F0   raised surface
    --stone   #86867E   secondary text
    --wine    #5A2A2E   the one accent, used sparingly

Type: Instrument Serif (display) / Instrument Sans (body) / IBM Plex Mono
(labels and spec sheets), from Google Fonts.

## Still to supply

1. **Brand UGC video.** This is the gap that matters. The wall shows nine
   logos; the work shown is your own hotel and café content. A brand will
   notice that the logos say beauty, food and retail while the work says
   hospitality. `ugc/index.html` has a commented-out **Vertical UGC** block
   ready — uncomment it and add embeds. Until then the page is honest but
   thinner than it should be.
2. **Portrait.** `index.html`, About section — a commented `<img>` is waiting.
   Drop a 4:5 image at `/portrait.jpg` and uncomment. The styling is done.
3. **Rate card.** Currently a `mailto:` CTA. No pricing is published anywhere.

## Brand logos

`/brands/` holds the client marks. Each source screenshot was cropped to its
content rows (several carried a grey rule or shadow band from the screenshot
itself), background-knocked-out, and flattened to `--ink` so the wall reads as
one row rather than nine competing brand palettes.

Sizing is by **equal optical area**, not equal height — a wide wordmark set to
the same height as a stacked mark looks twice as big. Each `<img>` carries an
inline `--w` equal to its natural width x 0.34. To add one:

1. Crop off screenshot chrome, knock out the background, flatten to `#141416`,
   trim, and scale so `width x height` is roughly 34,000px.
2. Add `<div class="wall__i"><img src="/brands/NAME.png" alt="Brand"
   style="--w:Xpx"></div>` where X is the new file's natural width x 0.34.

On the wall: Tim Hortons, Agoda, Klook, Amazon.ae, YesStyle, TIRTIR, Flowwow,
Lorealistar, Casa Barkada Salon.

Note that Agoda, Klook and Amazon are affiliate/ambassador programmes rather
than paid brand work. Mixing them with paid clients is a judgement call — if
you'd rather separate them, split the wall into two rows with their own labels.

Logos render at 55% opacity, full on hover. If a brand's guidelines require
full colour, drop the original PNG in and remove that image's opacity rule.

## OG image

`og-image.jpg` matches the design system. `og-image.html` is the source: open
it, screenshot the `.og` box at exactly 1200x630, save over `og-image.jpg`.
The committed JPG was rendered with a substitute serif, so regenerate it once
for correct Instrument Serif.

## Notes

- No build step, no framework, no Tailwind, no Font Awesome. Plain HTML + one
  stylesheet.
- Third-party embeds preserved as-is: Elfsight app IDs, Klook widget
  `data-adid`/`data-cid` values, the Agoda link, the Formspree form action.
- `Hijrnotes`, `Daily` and `JaneAust` font files are unreferenced. Safe to
  delete if unused elsewhere.
- The old `chapter-*.html` files are gone. If they still exist in the GitHub
  repo, delete them there — nothing links to them.
