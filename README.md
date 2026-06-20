# claude-github-design

The **Card Atlas** design system — a reusable, CSS-variable-themed design language for building beautiful, card-based static sites and hosting them on GitHub Pages.

**Live reference:** https://bhanu-thakur.github.io/claude-github-design/

- `index.html` — the design-system reference guide: a live gallery of every component, the palette, ready-to-paste re-theme snippets (Travel, Physio), and the icon set. Its `<style>` block + icon sprite are the single source of truth.
- `REUSABLE-PROMPT.md` — a paste-and-fill prompt to generate a new site in this exact language, vet it offline, and deploy it to GitHub Pages.

## How it stays consistent
1. Copy the reference's `<style>` block + icon sprite **verbatim** into every page.
2. Use only the existing tokens (CSS variables), fonts (Fraunces / Inter / JetBrains Mono), radius, shadow, spacing scale, and component classes.
3. Re-theme a project by changing **only** the accent variables in `:root`.

Built with Claude.
