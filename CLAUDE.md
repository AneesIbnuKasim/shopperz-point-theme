# Shopperz Point — Claude Code Master Instructions

## Project identity

This repository is the Shopify theme for **Shopperz Point**, based on Shopify Horizon 4.1.4.

Development branch: `develop`.

Shopperz Point should feel like a real, premium Indian gifting/lifestyle ecommerce brand:
- warm
- refined
- editorial
- minimal
- trustworthy
- spacious but not wasteful
- premium through restraint

It must NOT look like:
- a generic Shopify starter theme
- an AI-generated ecommerce template
- an overly rounded SaaS UI
- a luxury-fashion clone
- a theme overloaded with gradients, shadows, animations, or decorative effects

---

## 1. Inspect before editing

Before changing anything:

1. Run `git status --short`.
2. Inspect the relevant implementation.
3. Inspect `git diff` for existing uncommitted work.
4. Identify the actual root cause.
5. State which files need changing and why.
6. Make the smallest safe change.

Do not redesign based on assumptions.

When the user reports a visual issue, investigate the actual Horizon markup/CSS/configuration first.

---

## 2. Protect existing work

There are intentional uncommitted Shopperz Point modifications.

NEVER:
- `git reset --hard`
- `git restore`
- `git checkout -- <file>`
- delete unrelated modifications
- overwrite existing customizations
- stash existing work without permission
- revert previous Shopperz Point work because it looks unfamiliar

Existing modifications are the baseline unless the user explicitly asks to undo them.

---

## 3. One task at a time

Do not combine unrelated redesigns.

If asked to fix product tiles, fix product tiles.

Do not simultaneously redesign:
- header
- footer
- cart
- product page
- homepage
- global typography
- global colors

unless explicitly requested.

Preferred workflow:

INSPECT → ROOT CAUSE → SMALL IMPLEMENTATION → VALIDATE → BROWSER REVIEW → STOP

---

## 4. Design philosophy

Every visual decision must have a reason.

Prefer:
- strong hierarchy
- consistent spacing
- restrained borders
- warm neutrals
- charcoal text
- subtle champagne/gold accents
- natural product imagery
- consistent grid geometry
- deliberate whitespace
- subtle interaction states

Avoid:
- gradients unless explicitly requested
- glassmorphism
- excessive shadows
- floating cards everywhere
- excessive pill shapes
- oversized rounded corners
- decorative blobs
- random accent colors
- excessive animation
- huge empty areas
- arbitrary repeated CSS values

Premium should come from composition, proportion, consistency, typography, imagery, and restraint.

---

## 5. Shopperz Point visual language

The intended visual direction is:
- warm ivory / cream
- charcoal
- muted champagne/gold
- warm neutral borders

Known Shopperz Point values include:
- `#FAF8F3` — warm ivory
- `#282624` — charcoal
- `#C6A15B` — champagne/gold
- `#DED7CA` — warm neutral border

IMPORTANT:
These values do not authorize global palette replacement.

First inspect existing semantic Horizon/theme tokens and settings.

Prefer existing variables over hardcoded values.

A component-specific problem should normally use component/section-scoped CSS.

---

## 6. Typography

Keep the current Shopperz Point typography coherent.

Current direction uses Inter variants.

Do NOT:
- install another font
- import Google Fonts
- randomly replace Inter
- mix unrelated font families
- change global heading sizes for local issues

Use Horizon typography tokens wherever possible.

Hierarchy:
- eyebrow: small and restrained
- heading: strong but controlled
- supporting text: readable and quiet
- product title: clean, medium/regular
- price: slightly stronger than metadata
- secondary information: muted

Do not make every heading huge.

---

## 7. Spacing

Whitespace should feel intentional, not empty.

Use spacing to establish:
- hierarchy
- grouping
- image/content separation
- card rhythm
- page rhythm

Prefer Horizon spacing tokens.

Do not add large blank areas merely because "premium brands use whitespace."

---

## 8. Product imagery

Unless a section specifically requires another treatment:

- preserve the complete product
- avoid unwanted cropping
- avoid stretching
- use `object-fit: contain` where appropriate
- use consistent image viewports in product grids
- preserve Shopify responsive image generation
- preserve lazy/eager loading
- preserve image URLs and product links

Do not blindly use `object-fit: cover` to solve inconsistent source images.

Portrait, landscape, and square product images must all be handled gracefully.

---

## 9. Product cards

Product cards should feel like a premium catalog, not UI widgets.

Preferred rhythm:

IMAGE
↓
consistent gap
PRODUCT TITLE
↓
consistent gap
PRICE
↓
optional compare-at / metadata / quick add

For product grids:
- image viewport should be consistent
- title rhythm should be consistent
- prices should align where practical
- cards should have consistent visual rhythm
- long titles should wrap naturally
- do not aggressively truncate product names
- avoid heavy shadows
- avoid heavy card panels

Preserve native Horizon product-card architecture and:
- product links
- pricing
- compare-at pricing
- sale badges
- quick add
- variants
- selling plans
- inventory behavior
- accessibility
- loading states
- responsive behavior

---

## 10. Collection pages

Collection pages should feel like professional ecommerce catalogs.

Preserve:
- Horizon resource-list architecture
- filtering
- sorting
- pagination
- mobile grid
- existing Shopperz Point collection refinements

Do not replace Horizon's resource-list with a custom grid unless inspection proves the native implementation cannot satisfy the requirement.

Product tile consistency is more important than decorative styling.

---

## 11. Homepage

The homepage contains existing Shopperz Point work.

Do not redesign homepage sections casually.

The homepage category section was specifically corrected to avoid an empty fourth column when only three collections are configured.

Preserve:
- section configuration
- category cards
- hero
- product sections
- responsive behavior

Scope homepage changes to the requested section.

---

## 12. Header

The header is Horizon-native infrastructure as well as UI.

Relevant architecture includes:
- `sections/header.liquid`
- `sections/header-group.json`
- `sections/header-announcements.liquid`
- `blocks/_header-logo.liquid`
- `blocks/_header-menu.liquid`
- `snippets/header-actions.liquid`
- `snippets/header-drawer.liquid`
- `snippets/header-row.liquid`
- `snippets/search.liquid`
- `snippets/search-modal.liquid`

Preserve:
- sticky behavior
- desktop navigation
- mega menus
- overflow menu
- mobile drawer
- keyboard navigation
- focus management
- search
- account
- cart
- localization
- announcement functionality

Do not modify header JavaScript for visual changes.

Changing header height can affect sticky positioning and page offsets, so inspect before doing so.

---

## 13. Footer

The footer already has Shopperz Point refinements.

Current direction:
- editorial layout
- warm ivory surface
- charcoal typography
- restrained controls
- grouped legal links
- Shopperz Point attribution
- WhatsApp channel CTA
- social links

Preserve:
- Theme Editor configurability
- policy links
- copyright
- social links
- WhatsApp external-link behavior
- accessibility
- mobile wrapping

Do not restore Shopify attribution unless explicitly requested.

---

## 14. Cart

The cart already has a visual refinement.

Preserve native Horizon cart architecture:
- cart drawer
- `/cart`
- AJAX updates
- section morphing
- quantity controls
- discounts
- notes
- selling plans
- checkout
- accelerated checkout
- accessibility
- reduced motion

Visual direction:
- warm ivory
- contained product imagery
- subtle warm borders
- restrained radius
- clear product/price hierarchy
- strong but tasteful checkout CTA
- minimal panel treatment

Do not casually modify:
- `assets/component-cart-items.js`
- `assets/component-cart-quantity-selector.js`
- `assets/cart-drawer.js`
- `assets/cart-discount.js`
- `assets/cart-note.js`
- `assets/theme-drawer.js`

Do not change global quantity-selector styles to solve a cart-only issue.

---

## 15. Wishlist

There is currently NO real wishlist implementation.

Do not invent:
- wishlist icons
- fake favorites
- localStorage wishlist
- wishlist endpoints
- customer wishlist APIs

unless explicitly requested.

---

## 16. JavaScript policy

Prefer CSS/Liquid for visual changes.

Do not modify JavaScript for styling unless genuinely necessary.

Existing Horizon JavaScript is important infrastructure for:
- sticky header
- menus
- drawers
- cart
- quantity updates
- search
- accessibility
- focus management
- animations

If JavaScript modification is truly required:
1. explain why
2. modify the smallest possible scope
3. validate the interaction
4. report exactly what changed

---

## 17. Global CSS policy

Do not modify `assets/base.css` casually.

Do not solve a component-specific issue with global selectors.

Prefer:
- component stylesheet
- section-scoped CSS
- existing Horizon variables
- existing component classes

Example of preferred scoping:
`.collection-list-shopperz-point .collection-card { ... }`

Avoid global selectors that can unintentionally affect unrelated components.

---

## 18. Design-token policy

Prefer existing Horizon variables.

Typography:
- `--font-body--family`
- `--font-heading--family`
- `--font-subheading--family`

Colors:
- `--color-background`
- `--color-foreground`
- `--color-foreground-subdued`
- `--color-border-rgb`
- `--color-primary-button-background`
- `--color-primary-button-text`

Spacing:
- `--padding-*`
- `--gap-*`
- `--margin-*`

Radius:
- `--style-border-radius-*`

Layout:
- `--page-width`
- `--page-margin`
- `--sidebar-width`
- `--theme-drawer-width`

Motion:
- `--animation-speed-*`
- `--animation-easing`

Do not create a second competing global design-token system unless explicitly requested.

---

## 19. Theme Editor safety

JSON templates and section-group files may be generated or influenced by Shopify Theme Editor.

When changing configuration:
- preserve existing blocks
- preserve existing settings
- preserve merchant configurability
- make the smallest JSON change possible

Never replace an entire JSON file just to alter one setting.

---

## 20. Accessibility

Every redesign must preserve:
- semantic HTML
- heading hierarchy
- keyboard navigation
- focus states
- focus trapping
- focus restoration
- ARIA labels
- live regions
- screen-reader text
- form labels
- button semantics
- sufficient color contrast
- reduced-motion behavior

Never remove accessibility features for visual convenience.

---

## 21. Responsive design

Consider every change at:
- desktop
- tablet
- mobile

Preserve Horizon breakpoints and responsive architecture unless there is a clear reason to change them.

Mobile must remain:
- readable
- touch-friendly
- compact
- consistent
- free of horizontal overflow

---

## 22. Animation

Shopperz Point should use subtle motion.

Good:
- opacity transitions
- restrained underline transitions
- subtle hover changes
- short ease-out transitions

Avoid:
- bouncing
- dramatic scaling
- excessive parallax
- constant motion
- long decorative animations

Every new animation must respect `prefers-reduced-motion`.

---

## 23. Screenshot analysis

When the user provides a screenshot, treat it as evidence of a visual problem.

Analyze:
1. alignment
2. spacing
3. proportions
4. typography
5. image treatment
6. card dimensions
7. color relationships
8. responsive behavior
9. likely CSS/markup cause

Do not immediately respond to a screenshot by redesigning everything.

Find the structural reason first.

---

## 24. Browser verification

Code inspection alone is not visual verification.

If browser/preview tooling is available:
- inspect the rendered page
- test the affected viewport
- test mobile
- compare before/after

If browser verification is unavailable, say so explicitly.

Never claim visual verification occurred when it did not.

---

## 25. Validation

After changes run:

```bash
git diff --check
shopify theme check
git status --short
git diff --stat
git diff
```

If Theme Check fails because of a Shopify CLI/tooling error, distinguish that from actual theme errors.

Confirm:
- only intended files changed
- existing unrelated work is preserved
- no functional regressions were introduced

---

## 26. Git policy

NEVER automatically:
- commit
- push
- merge
- rebase
- force push

Leave changes uncommitted unless the user explicitly asks for repository operations.

---

## 27. Known existing work

Existing Shopperz Point modifications include work across:
- homepage
- collection pages
- product cards
- cart
- footer
- product pages
- templates
- configuration

Do not assume unfamiliar modifications are accidental.

Inspect and preserve them.

---

## 28. Preferred implementation hierarchy

For visual issues, use this order:

1. Existing Horizon setting
2. Existing Horizon design token
3. Component/section-scoped CSS
4. Small Liquid markup adjustment
5. Template configuration adjustment
6. New scoped CSS when justified
7. JavaScript only as a last resort

Never jump directly to global CSS or JavaScript.

---

## 29. Definition of "premium"

A successful change should feel:
- intentional
- calm
- trustworthy
- commercially polished
- consistent
- editorial
- brand-specific

Premium does NOT mean:
- more shadows
- more gold
- more rounded corners
- bigger headings
- more whitespace
- more animation
- more CSS
- more decoration

When in doubt, choose restraint.

---

## 30. Standard design-task workflow

### Phase A — Inspect
Run:
```bash
git status --short
git diff
```

Inspect the relevant Horizon implementation.

### Phase B — Diagnose
Report:
- actual issue
- root cause
- relevant files
- safest solution
- files that will remain untouched

### Phase C — Implement
Make the smallest scoped change.

### Phase D — Validate
Run:
```bash
git diff --check
shopify theme check
git status --short
```

### Phase E — Review
Use browser preview if available. Otherwise clearly state that visual verification was unavailable.

### Phase F — Stop
Do not continue redesigning unrelated areas.

---

## Final instruction

The goal is NOT to make Shopperz Point "fancy."

The goal is to make it look like a **carefully designed, trustworthy, premium ecommerce brand that happens to be built on Shopify Horizon**.

Preserve Horizon's strengths.

Fix structural problems before styling symptoms.

Use restraint.

Never trade functionality for appearance.

Never overwrite existing Shopperz Point work.

Always inspect first.

Always make the smallest safe change.

Always validate.

Never commit or push without explicit instruction.
