# claude-github-design

The **Card Atlas** design system + a reusable prompt for building beautiful, card-based static sites and hosting them on GitHub Pages.

**Live — the prompt:** https://bhanu-thakur.github.io/claude-github-design/
**Live — the design system:** https://bhanu-thakur.github.io/claude-github-design/design-system.html

- `index.html` — the prompt landing page: use cases, the full reusable prompt with a one-click **Copy** button, a link to the design system, and a **Download .html** of the reference.
- `design-system.html` — the design-system reference: a live gallery of every component, the palette, re-theme snippets (Travel, Physio) and the icon set. Its `<style>` block + icon sprite are the single source of truth.
- `REUSABLE-PROMPT.md` — the same prompt as plain Markdown.

## How it stays consistent
1. Copy the reference's `<style>` block + icon sprite **verbatim** into every page.
2. Use only the existing tokens (CSS variables), fonts (Fraunces / Inter / JetBrains Mono), radius, shadow, spacing scale, and component classes.
3. Re-theme a project by changing **only** the accent variables in `:root`.

Built with Claude.
