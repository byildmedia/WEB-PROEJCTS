# Bernice Bakery (bernicebakery.com) — Website Analysis

Analysis date: 2026-07-13

## Access note (important)

The live site could not be fetched from this environment:

- The sandbox network policy is **allowlist-based** and `bernicebakery.com` is not on it
  (the gateway rejects the CONNECT tunnel with 403).
- Anthropic's remote fetcher (WebFetch) is blocked by the site itself with **HTTP 403**
  (Shopify bot protection), and `web.archive.org`, `awwwards.com`, and `casamedia.com`
  block automated fetchers as well.

Everything below is assembled from **search-engine results and prior knowledge** of the
site. Facts are labeled *Confirmed* (from indexed sources) or *Inferred* (typical of this
kind of build / recalled, not verifiable from here). To get an exact, byte-level
extraction of the theme's CSS/JS, add `bernicebakery.com` and `cdn.shopify.com` to this
environment's network egress allowlist and re-run the task.

## What the site is — Confirmed

- **Business:** Bernice, a bakery in Saint-Henri, Montreal. Known for layered cakes
  (6" and 9") and ~a dozen cookie varieties (4 oz / 6 oz). Cakes baked to order with
  24 h notice; pickup 10:00–16:30, closed Sun–Mon.
- **Platform:** **Shopify** with a **fully custom theme** (URL structure confirms:
  `/collections/all`, `/collections/cakes`, `/collections/cookies`, `/pages/about`,
  `/pages/contact`).
- **Agency:** **Casa Media** (Montreal) — design by Dorian, Shopify development by Fred.
  Case study: "Bernice Bakery: A Website You Can Practically Taste."
- **Recognition:** **Awwwards Honorable Mention**, nominated for an E-commerce Awwward
  with top marks for originality, design, and usability. Awwwards tags:
  *E-Commerce, Food & Drink, Animation, Colorful, Illustration, Gestures/Interaction,
  Interaction Design, Microinteractions*.
- **Result:** the agency reports a **25% increase in sales** after launch.
- **Design direction:** built on the bakery's existing brand (illustrations, palette,
  vibe) with a new typeface, a bolder accent color, and custom assets. The animations
  were described as the "icing on the cake."

## Site map — Confirmed from indexed URLs

| Page | URL | Indexed title |
|---|---|---|
| Home | `/` | Bernice Bakery – Best Homemade Cakes & Cookies in Montreal |
| All products | `/collections/all` | Products |
| Cakes | `/collections/cakes` | Our Selection of Cakes |
| Cookies | `/collections/cookies` | Shop Our Selection of Cookies |
| About | `/pages/about` | About Bernice – A Montreal Bakery |
| Contact | `/pages/contact` | Contact |

## Animation & interaction inventory

Awwwards' *Animation / Interaction Design / Microinteractions* tags confirm the site is
animation-heavy. The concrete inventory below is **Inferred** — it reflects the patterns
this site is known for and the standard technique stack of custom Shopify themes of this
caliber (GSAP + ScrollTrigger, a smooth-scroll layer such as Lenis, and CSS keyframe
microinteractions):

1. **Scroll-triggered reveals** — sections and product cards fade/slide/scale in as they
   enter the viewport, with per-item stagger and a soft "springy" overshoot ease.
2. **Scroll-linked rotation ("sticker wiggle")** — tilted product photos and illustrated
   stickers rotate toward level (or wobble) as you scroll, progress-mapped rather than
   time-based.
3. **Parallax layers** — decorative illustrations and photos drift at different speeds.
4. **Velocity-reactive marquee** — an infinite scrolling text band whose speed/skew
   responds to scroll velocity.
5. **Pinned (sticky) storytelling section** — a section pins while its content animates
   through, driven by scroll progress.
6. **Rotating circular badge** — a circular text stamp that spins continuously and
   speeds up with scroll.
7. **Hover microinteractions** — squishy scale-down buttons, jiggling product cards,
   underline draws, cursor-follow effects.
8. **Load-in choreography** — hero headline letters/words bounce in staggered on load.
9. **Organic dividers** — wavy/scalloped SVG section edges consistent with the
   hand-drawn brand illustration style.

All nine patterns are implemented as a reusable, dependency-free kit in
[`index.html`](./index.html) (data-attribute API, IntersectionObserver +
requestAnimationFrame, honors `prefers-reduced-motion`). Placeholder content only —
no copy, imagery, or brand assets from the live site are reproduced.

## Design tokens — Inferred

- **Palette:** warm cream/off-white base, bold warm red accent, chocolate-brown text,
  soft pink/butter-yellow secondary tones.
- **Type:** a chunky, rounded display face for headings; clean sans for UI/body.
- **Imagery:** hand-drawn illustration + product photography, often cut out and tilted
  like stickers/polaroids.
- **Shape language:** heavy border-radius, blob/wave edges, sticker outlines.

## How to reuse the kit

Every effect in `index.html` is driven by data attributes:

```html
<div data-reveal="up" data-reveal-delay="120">…</div>   <!-- fade/slide/scale/rotate in -->
<img data-parallax="-0.15">                             <!-- parallax drift, speed factor -->
<img data-scroll-rotate="8">                            <!-- rotates with scroll progress -->
<div data-marquee data-marquee-speed="60">…</div>       <!-- velocity-reactive marquee -->
<section data-pin>…</section>                           <!-- pinned progress section -->
<div data-spin>…</div>                                  <!-- rotating circular badge -->
```

Copy the `<script>` block (the `BakeKit` IIFE) and the `/* == BakeKit == */` CSS section
into any project — no build step, no dependencies.

## Sources

- https://bernicebakery.com/ (indexed titles only; direct fetch blocked)
- https://casamedia.com/web-design/bernice-bakery-a-website-you-can-practically-taste/
- https://www.awwwards.com/sites/bernice-bakery
- https://www.awwwards.com/inspiration/desktop-bernice-bakery
