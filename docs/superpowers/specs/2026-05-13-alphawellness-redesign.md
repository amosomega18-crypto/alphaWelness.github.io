# AlphaWellness Website Redesign — Design Spec
**Date:** 2026-05-13  
**Approach:** Option A — Full Cinematic Overhaul  
**Site:** alphawellness.fr (GitHub Pages, single `index.html`)

---

## Goal
Transform the existing dark/gold website into a cinematic editorial luxury experience that immediately converts first-time visitors into coaching enquiries. Target audience: expats, busy professionals, and high-performers in France.

---

## Visual Direction
- **Style:** Editorial / Magazine — cinematic full-screen photo backgrounds, large dramatic typography
- **Palette:** Unchanged — `#0c0c0b` black, `#c8a95a` gold, `#f5f2eb` cream white
- **Fonts:** Unchanged — Playfair Display (serif headings) + Jost (body)
- **French integration:** Sprinkle — key eyebrow labels and taglines in French, body copy stays English

---

## Sections & Changes

### Navigation
- Replace text logo with `images/logo.png` (gold triangle mark + "Alpha Wellness")
- Logo width: 140px max, height auto
- All other nav elements unchanged

### Hero
- Full-screen background: Unsplash luxury gym/athlete image (dark, dramatic)
- Dark overlay: `rgba(0,0,0,0.75)`
- Logo mark (triangle SVG inline, ~60px) centered above headline as page opener
- French eyebrow: *"Votre Transformation Commence Ici"*
- Headline unchanged: *"Train smarter. Live better. In your language."*
- French sub-tagline added below subtitle: *"L'excellence à votre service — en France et au-delà"*
- Fade-in entrance animation: logo → eyebrow → headline → subtitle → buttons (CSS keyframes, staggered delays)
- Stats bar at bottom unchanged

### Credentials Bar
- Unchanged content
- Glassmorphism background: `rgba(20,20,18,0.7)` + `backdrop-filter: blur(12px)`

### Who I Work With (`#who`)
- Background: Unsplash yoga/stretch image with `rgba(0,0,0,0.78)` overlay
- French eyebrow: *"Pour Qui"*
- Section title unchanged
- Cards: glassmorphism — `rgba(20,20,18,0.6)` + `backdrop-filter: blur(8px)` + gold border

### How It Works (`#how`)
- Background: Unsplash personal training/coaching image with overlay
- French eyebrow: *"Votre Parcours"*
- Section title unchanged
- Callout card: glassmorphism

### Nutrition (`#nutrition`)
- Background: Unsplash clean wellness/food image with overlay
- French eyebrow: *"Nutrition & Bien-être"*
- Meal cards: glassmorphism

### Reviews (`#reviews`)
- Background: Unsplash luxury spa/massage image with overlay
- French eyebrow: *"Ils Témoignent"*
- Review cards: glassmorphism

### Booking (`#booking`)
- Background: Unsplash outdoor sunrise/nature wellness image with overlay
- French eyebrow: *"Réservez Votre Appel"*

### FAQ (`#faq`)
- No background image — stays dark solid (`var(--black)`)
- French eyebrow: *"Questions Fréquentes"*

### Footer CTA
- Background: subtle dark gradient over wellness image
- French closing line added: *"Façonnez votre meilleur vous."*

### Footer
- Logo full image (`images/logo.png`) at top of brand column, ~160px wide
- Rest unchanged

---

## Animations
- **Hero entrance:** CSS `@keyframes fadeInUp` with staggered delays on `.hero-eyebrow`, `h1`, `.hero-sub`, `.hero-actions`
- **Scroll reveal:** `IntersectionObserver` adds `.visible` class; CSS transitions `opacity 0 → 1`, `translateY(24px) → 0`, `duration 0.6s ease`
- Applied to: section titles, card grids, step items
- No external JS libraries

---

## Images
All sourced from Unsplash (already whitelisted in CSP `img-src`).

| Section | Query / URL |
|---|---|
| Hero | Dark dramatic gym athlete |
| Who I Work With | Yoga stretch luxury |
| How It Works | Personal trainer coaching |
| Nutrition | Clean wellness food |
| Reviews | Luxury spa massage |
| Booking | Outdoor sunrise wellness |

User logo: `images/logo.png` — user provides the file (shared in chat as PNG).

---

## Technical Constraints
- Single `index.html` — no build tools, no frameworks
- GitHub Pages static hosting
- Must preserve existing CSP headers
- Mobile-first responsive (existing breakpoint at 768px)
- No external JS libraries added
