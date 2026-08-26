# Shopperz Point Theme Development Rules

## Project

This is a Shopify Horizon 4.1.4 theme.

Repository:
- Shopify theme
- Git-controlled
- Current development branch: `develop`

## Core Development Rules

Never replace Horizon architecture with custom implementations.

Before modifying any feature:

1. Inspect the existing Horizon implementation.
2. Understand its Liquid, blocks, schema, snippets, CSS and JavaScript architecture.
3. Identify the smallest set of files that need to change.
4. Preserve existing functionality.
5. Prefer minimal modifications.
6. Never remove existing schema settings unless explicitly requested.
7. Never replace native Shopify/Horizon components unnecessarily.
8. Never introduce a new carousel when Horizon already provides one.
9. Reuse existing Horizon JavaScript and components whenever possible.
10. Preserve Shopify Theme Editor configurability.
11. Run `git diff --check` after modifications.
12. Run Shopify Theme Check after modifications.
13. Report all warnings/errors from validation.
14. Never commit or push unless explicitly instructed.

## Git Safety

The repository is Git-controlled.

Never perform destructive Git operations without explicit permission.

Do NOT run:

- `git reset --hard`
- `git clean`
- `git checkout -- <file>`
- `git restore <file>`
- force pushes
- history rewriting

unless explicitly instructed.

Before making substantial changes:

- inspect `git status`
- inspect relevant existing code
- inspect the current diff if the working tree is already dirty

Never overwrite unrelated user changes.

## UI Development

For UI work:

- Prefer existing design tokens.
- Reuse existing Horizon classes/components.
- Keep responsive behavior.
- Preserve accessibility.
- Preserve keyboard navigation.
- Preserve focus-visible states.
- Preserve reduced-motion behavior.
- Preserve mobile behavior.
- Preserve desktop behavior.
- Keep merchant configurability through Shopify Theme Editor settings.
- Avoid unnecessary JavaScript.
- Avoid unnecessary dependencies.
- Avoid duplicating existing Horizon functionality.

## Shopify Architecture

Prefer the existing Horizon architecture:

- Sections
- Blocks
- Snippets
- Theme settings
- JSON templates
- Section groups
- Horizon custom elements
- Horizon JavaScript modules
- Existing responsive patterns
- Existing CSS architecture

Before creating a new implementation, search the repository for an existing Horizon implementation that can be extended.

Do not replace a native Horizon feature merely to achieve a visual change.

## Carousel Rule

If Horizon already provides carousel/slider functionality:

- Preserve it.
- Extend its existing implementation when necessary.
- Do not create a second carousel system.
- Do not remove existing carousel controls.
- Preserve swipe/scroll behavior.
- Preserve keyboard interaction.
- Preserve arrows/dots where configured.
- Preserve pause/play behavior where applicable.
- Preserve reduced-motion behavior.

## Shopperz Point Brand

The visual identity should feel:

- Premium
- Warm
- Modern
- Elegant
- Approachable

Primary visual direction:

- Ivory
- Charcoal
- Restrained champagne/gold
- Generous whitespace
- Subtle borders
- Soft shadows
- Refined typography

Avoid:

- Excessive gradients
- Excessive gold
- Heavy shadows
- Excessive rounded cards
- Generic SaaS styling
- Visually noisy layouts
- Unnecessary animations

## Code Quality

Prefer:

- Small focused changes
- Existing variables/tokens
- Existing components
- Existing classes
- Semantic Liquid
- Accessible HTML
- Responsive CSS
- Progressive enhancement

Avoid:

- Large rewrites
- Duplicated logic
- Hardcoded values when a theme setting/token already exists
- Breaking merchant customization
- Unnecessary dependencies

## Validation

After modifying files:

1. Run:

```bash
git diff --check
