# Frontend Simplified Capstone

A polished, single-page frontend capstone that markets the Frontend Simplified program using semantic HTML, modular section-level CSS, and lightweight vanilla JavaScript interactions.

This project is intentionally static and deploys directly to GitHub Pages.

## What This Project Is

- A static marketing/landing page built with `index.html` + CSS.
- A section-driven architecture where each major page block has its own stylesheet in `styles/sections/`.
- A practical showcase of modern HTML/CSS patterns (responsive layout, theming, animations, accessibility foundations).

## Quick Start

### Option 1: Open directly

Open `index.html` in a browser.

### Option 2: Run a local static server (recommended)

From the repository root:

```bash
python -m http.server 5500
```

Then visit `http://localhost:5500`.

## Tech Stack

- HTML5 (semantic page structure and content)
- CSS3 (tokens, responsive layout, animation, section-scoped styling)
- Vanilla JavaScript (theme toggle + FAQ accordion behavior)
- GitHub Actions + GitHub Pages (deployment)

## Project Structure

```text
capstone/
├─ index.html
├─ styles.css
├─ styles/
│  └─ sections/
│     ├─ firstlight.css
│     ├─ proof-luxe.css
│     ├─ whyus-luxe.css
│     ├─ dossier-finale.css
│     ├─ countdown-monument.css
│     ├─ curriculum-mission.css
│     ├─ newswall.css
│     ├─ mission-control.css
│     ├─ mentors-wall.css
│     ├─ broadcast-coaching.css
│     ├─ contract-closer.css
│     ├─ faq-interrogation.css
│     ├─ transmission-footer.css
│     └─ theme-overrides.css
├─ assets/
│  └─ fes.png
└─ .github/
   └─ workflows/
      └─ static.yml
```

## How The Modules Work

The page is organized into visual/content modules (sections). Each module is rendered in `index.html` and styled by one dedicated file in `styles/sections/` (plus shared base styles in `styles.css`).

| Module (Section) | HTML Anchor / Class | Primary CSS File | Purpose |
|---|---|---|---|
| Header + Hero | `.firstlight-nav`, `.firstlight-hero` | `styles/sections/firstlight.css` | First impression, positioning, CTA |
| Social Proof | `.proof-luxe` | `styles/sections/proof-luxe.css` | Reviews, outcomes, credibility |
| Stats Prism | `.stats-block` | `styles.css` | Guarantee/time/salary highlight cards |
| Value Proposition | `#value-prop`, `.value-prop-section` | `styles.css` | Core messaging and value story |
| Why Us | `#four-steps`, `.whyus-luxe` | `styles/sections/whyus-luxe.css` | Four-step path explanation |
| Waitlist Story + Form | `#join-waitlist`, `.dossier-finale` | `styles/sections/dossier-finale.css` | Success story and capture form |
| Timeline | `.countdown-monument` | `styles/sections/countdown-monument.css` | 6+4+2 week journey framing |
| Curriculum | `#curriculum`, `.curriculum-mission` | `styles/sections/curriculum-mission.css` | 09-module learning roadmap |
| Student Outcomes | `.newswall` | `styles/sections/newswall.css` | Alumni result snapshots |
| Community | `.mission-control` | `styles/sections/mission-control.css` | Community scale and signup |
| Mentors | `.mentors-wall` | `styles/sections/mentors-wall.css` | Instructor credibility |
| Coaching | `.broadcast-coaching` | `styles/sections/broadcast-coaching.css` | Weekly support model |
| Guarantee CTA | `.contract-closer` | `styles/sections/contract-closer.css` | Offer reinforcement |
| FAQ | `.faq-interrogation` | `styles/sections/faq-interrogation.css` | Objection handling |
| Footer | `.transmission-footer` | `styles/sections/transmission-footer.css` | Navigation and policy links |

## Curriculum Modules Covered (Content)

The curriculum content in this repository is represented in `index.html` under the Curriculum section:

1. Onboarding  
2. Master HTML & CSS  
3. Build Four Impressive Projects  
4. Start Making $250 per Website (Milestone)  
5. Practise & Learn JavaScript  
6. Learn React  
7. Specialize in Frontend  
8. Practice Interviews  
9. Land a Job (Milestone)

## HTML Topics Covered

This codebase covers HTML through both explicit curriculum copy and practical implementation patterns:

- Semantic page structure: `header`, `main`, `section`, `article`, `aside`, `footer`, `nav`.
- Accessible navigation and jump links: skip link + section anchors.
- Forms and validation primitives: `form`, `label`, `input type="email"`, `required`, placeholders.
- Structured content primitives: ordered/unordered lists, headings hierarchy, blockquotes, paragraphs.
- Media and responsive image patterns: `img`, `picture`, `source`, width/height attributes.
- Link behavior and external linking safety (`target="_blank"`, `rel="noopener noreferrer"`).
- Accessibility attributes in context: `aria-label`, `aria-hidden`, `aria-pressed`.
- Progressive interaction wiring points through HTML class hooks for JS (theme toggle, FAQ accordion).

## CSS Topics Covered

The project demonstrates a broad set of practical CSS topics:

- Design tokens and theming with CSS custom properties (`:root` variables).
- Theme switching with `html[data-theme="light"]` and system preference handling (`prefers-color-scheme`).
- Responsive design with breakpoint-based media queries.
- Layout systems:
  - Flexbox (`display: flex`) for nav/actions/cards.
  - Grid (`display: grid`) for module layouts and card collections.
- Visual layering and composition:
  - Gradients (linear/radial)
  - pseudo-elements (`::before`, `::after`)
  - overlays, clipping, and depth/shadow composition
- Motion and transitions:
  - keyframe animations
  - hover/focus transitions
  - staged reveal patterns
- Accessibility-friendly styles:
  - `:focus-visible` outlines
  - `prefers-reduced-motion` fallbacks
  - `.visually-hidden` utility
- Browser UX polish:
  - custom scrollbars
  - custom cursor assets (SVG data URI)

## JavaScript Behavior

There are two focused behaviors in `index.html`:

- Theme toggle:
  - Detects system preference on load.
  - Updates `data-theme` and syncs button `aria-*` state.
- FAQ accordion:
  - Click-to-toggle per item.
  - Ensures only one item is open at a time.

## Accessibility and UX Patterns

- Skip link for keyboard users.
- Labeled inputs for all email fields.
- Consistent focus-visible states on interactive controls.
- Motion-reduction handling in base and section styles.
- Semantic grouping of content and navigation landmarks.

## Deployment

Automated deployment is configured in `.github/workflows/static.yml`:

- Trigger: push to `main` (and manual dispatch).
- Action flow:
  1. Checkout repository
  2. Configure GitHub Pages
  3. Upload repository as Pages artifact
  4. Deploy via `actions/deploy-pages`

This means the page can ship with no build step.

## Project Insights

### Strengths

- Clear modular styling strategy: section-by-section CSS improves ownership and readability.
- Strong visual direction with consistent typography, gradients, and motion language.
- Thoughtful responsiveness and accessibility baselines included from the start.
- Low operational complexity: static hosting + zero build dependencies.

### Current Gaps

- Forms currently submit to placeholder targets (`action="#"`), so no backend capture flow exists.
- Some links are placeholders and need real destinations.
- JavaScript lives inline in `index.html`; future growth would benefit from extracting to `scripts/`.
- No automated tests or linting pipeline in this repository.

### Recommended Next Upgrades

1. Wire forms to a real endpoint (serverless function, Forms API, or email automation).
2. Replace placeholder links with production routes.
3. Extract JS into dedicated files and add basic unit/integration checks.
4. Add performance and accessibility audits (Lighthouse baseline targets).
5. Add contribution notes and code standards for collaborators.

## Ownership Notes

If you are onboarding a contributor:

- Start in `index.html` to understand the content model and section order.
- Use `styles.css` for global primitives/tokens.
- Use `styles/sections/<module>.css` for module-specific visual changes.
- Keep section responsibilities isolated to preserve maintainability.
