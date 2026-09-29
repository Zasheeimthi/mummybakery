# New Mummy Bakery — Implementation Plan

## Product outcome
A mobile-first, modern bakery storefront for New Mummy Bakery, Ramanathapuram, preserving the source site's real products, prices, Tamil names, descriptions, three branches, contact details, hours, Instagram, and WhatsApp ordering.

## Architecture
- Static HTML/CSS/JS frontend with no server or database; content is embedded in the initial HTML for crawlability and fast first paint.
- One public route (`/`) with anchored sections: hero, menu, visit, and footer. Unknown routes are not part of this static build.
- Static delivery: `index.html` and versioned assets are served from the build output. No API paths.
- Cache intent: HTML revalidates; immutable hashed/build assets may be long-lived under the platform's static defaults.

## Structure
- `index.html`: semantic page shell, all product/business content, SEO metadata, accessible landmarks.
- `styles.css`: design tokens, responsive layout, states, reduced-motion support.
- `app.js`: category filtering, basket state, quantity controls, WhatsApp message generation, mobile navigation.
- `public/brand-mark.png`: project logo/favicon asset.
- `public/hero-bakes.jpg`: prominent editorial hero asset.
- `ideas.md`: accepted visual direction and asset placement.

## Product behavior
- Browse 18 source products across Sweets, Cakes, Savouries, and Combos.
- Filter menu by category using keyboard-friendly buttons.
- Add products to a client-side basket, adjust quantity, remove items, and see a live count.
- Build a prefilled WhatsApp enquiry containing selected product names, quantities, and prices.
- Persistent WhatsApp CTA remains visible on mobile without blocking content.
- Branch cards preserve source addresses, phone links, directions, daily hours, and WhatsApp/Instagram links.

## Verification
- Inspect source for all 18 products and exact prices/contact facts.
- Run HTML/CSS/JS syntax and link checks plus a local HTTP server request.
- Use the Web Dev validator only if additional integration uncertainty remains; no browser screenshot pass is required by the user.
