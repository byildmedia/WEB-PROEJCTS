# Prompt — Site web « bazar indien vintage » (inspiré de gourouindianfood.fr)

Prompt prêt à l'emploi pour générer un site du même univers. Remplacer les valeurs
entre `[crochets]` par celles du client.

---

Build a complete, single-page-first restaurant website (with secondary pages) for
**[NOM DU RESTAURANT]**, a modern Indian street-food restaurant in **[VILLE]**. The
site must feel like a **vintage Indian bazaar meets Parisian bistro** — warm, playful,
handcrafted, and a little nostalgic. All visible copy in **French**.

## Tech
- Static site: semantic HTML5, modern CSS (custom properties, grid/flex), vanilla JS only.
- Fully responsive (mobile-first), smooth scroll, subtle scroll-reveal animations.
- No external UI frameworks; Google Fonts allowed.
- SEO: French meta description, Open Graph tags, JSON-LD `Restaurant` schema
  (address, hours, phone, rating), and a `<title>` starting with the 🔥 emoji:
  `🔥 [NOM] | Indian Food Company — Restaurant indien à [VILLE]`.

## Design system
- **Palette** — cream/off-white porcelain background `#F5EFE2`; deep charcoal text
  `#241F1C`; spice accents: saffron `#E8A020`, chili red `#C6431F`, turmeric
  `#D9A441`; secondary: patinated wood brown `#6B4A2F`, bottle green `#3E5C3A`
  (nod to the vine-covered 1930s bistro façade); small touches of stainless-steel
  grey `#B9BDB9`.
- **Typography** — display: a chunky retro/hand-painted feel (e.g. "Fraunces" or
  "Clash Display" style serif with character) for headings, evoking hand-lettered
  bazaar signage; body: a clean humanist sans (e.g. "Inter" / "Work Sans");
  optional stencil-style accents for labels and prices.
- **Texture & details** — subtle paper-grain background, thin double-rule borders
  like vintage packaging, ticket-style price tags, hand-drawn dividers, stamp/label
  badges ("Fait maison", "Végétarien", "Vegan", "Sans gluten"), dotted lines like
  a market receipt. Corners slightly rounded, shadows soft and warm.
- **Imagery** — use warm-toned placeholder images (spices, copper/steel teapots,
  chai glasses, naans, painted signs). Duotone or slightly faded treatment to keep
  the vintage mood.

## Pages / sections
1. **Hero** — full-width, painted-sign style logotype, tagline
   « La street food indienne, faite maison à [VILLE] », three CTAs side by side:
   **Réserver** (primary, saffron), **Commander en ligne**, **Appeler**.
2. **Notre histoire** — split layout: the founders' travels across India, the
   heritage of the historic space the restaurant occupies **[HISTOIRE DU LIEU]**,
   chef's fine-dining background applied to street food. Vintage-postcard framing.
3. **La carte** — tabbed or anchored categories: Street Food (Vada Pav…), Currys
   (Butter Chicken, Palak Paneer, Gobi Tikka…), Biryanis, Pains maison (naans,
   Ladi Pav), Desserts (crème caramel cardamome, glaces maison), Boissons (chaï,
   lassis, cocktails maison, sirops frais). Each item: name, one-line French
   description, price in a ticket-tag, diet badges. Note « Tout est fait maison,
   nos pains sont cuits chaque jour ».
4. **Le lieu** — gallery grid of the room: exposed electrical circuits on the walls,
   aged wooden chairs, glass shelves with vintage clocks, old advertising posters,
   Indian street-intersection signs, portraits — described in captions.
5. **Preuve sociale** — Google rating badge (**[NOTE]/5 · [N] avis**) + 3 short
   press quotes in a carousel with publication names.
6. **Infos pratiques** — two-column: address **[ADRESSE]** with métro line badge
   **[MÉTRO]**, hours table (weekdays split service, weekend continuous), phone
   **[TÉLÉPHONE]**, email for groups of 8+ **[EMAIL]**, embedded-map placeholder.
7. **Footer** — logotype, nav links, Instagram **[@HANDLE]**, delivery partner
   links, legal links, « Fait avec ❤️ et beaucoup d'épices ».

## Interactions
- Sticky header that condenses on scroll; mobile burger menu.
- Hover states: price tags tilt slightly, images warm up (saturate), buttons get a
  stamped/pressed effect.
- Menu category switcher without page reload; smooth anchors.
- Prefers-reduced-motion respected.

Deliver as `index.html` + `styles.css` + `script.js` in one folder, with realistic
French placeholder content everywhere a `[crochet]` value is missing.
