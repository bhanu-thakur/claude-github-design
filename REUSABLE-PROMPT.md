# Reusable build prompt — "Card Atlas" sites

Paste this whenever you want a new card-based site (travel atlas, physio plan, course, recipe index, anything).
**Attach `design-system.html` to the message** — it is the design source of truth.
Fill in the `{...}` placeholders and delete this top line before sending.

---

Build me a multi-page, card-based static website that I will vet offline and then host on GitHub Pages. Ask me clarifying questions (multiple-choice where possible) before doing real work, and again if scope is ambiguous.

## Design language — non-negotiable
Use the attached `design-system.html` as the single source of truth.
- Copy its **entire `<style>` block and the icon `<svg>` sprite verbatim** into every page. They must be byte-identical across all pages.
- Use **only** the existing tokens (CSS variables), fonts (Fraunces / Inter / JetBrains Mono), `--radius`, `--shadow`, the spacing scale, and the documented component classes (`.card`, `.card.cat`, `.stat`, `.pill`, `.note`, `.steps`, `.list`, `.minigrid`, `.track`, `.cardgrid`/`.tile`, `.pagenav`, `.topbar`, `.closing`, etc.).
- Do **not** invent new colours, fonts, radii, shadows, or arbitrary px spacing. If a new component is truly needed, derive it from existing variables and match the existing class-naming + scale.
- **Lead with components, not prose.** Short paragraphs; let cards/stats/notes/grids carry the information.

## Re-theme for this project
Change **only** the `[THEME]` block in `:root` (see the "Re-theme" section of the reference). Pick one:
- Keep sage green (default), **or** Travel terracotta, **or** Physio teal (snippets are in the reference), **or** a custom `--primary` I give you. Everything else stays identical.

## Project specifics  ← fill these in
- **Project / brand name:** {e.g. "Italy in 100 Stops"}
- **Topic & goal:** {what it's for, who reads it}
- **Item noun & count:** {e.g. 100 "stops" / 30 "sessions"} → pages `item-1.html` … `item-N.html` (use your own noun, e.g. `stop-1.html`)
- **Grouping:** {e.g. by region / week / body-area} → use the category accents `--c1..--c6`
- **What each item page contains:** {the sections each page should have}
- **Header "companion" button (optional):** {an unrelated reference that deserves its own sticky-header button, like the B-roll plan was}
- **Theme:** {sage / travel / physio / custom}
- **GitHub repo name:** {e.g. italy-100-stops} → site will be `username.github.io/REPO/`

## Structure
- `index.html` = the overview / home page. Near the top (**section 2**, right after a short intro) put a responsive **`.cardgrid`** of all items. Built items are live `.tile` linking to their page; not-yet-built items are `.tile.lock` (greyed, lock icon, "coming soon").
- **Sticky header (`.topbar`) on every page:** brand → `index.html`, the main nav link(s), and any companion reference as a `.btn` button.
- Each **item page:** hero (`.eyebrow` + `h1` + `.lede` + `.chips`), the content built from components, and a **`.pagenav`** (prev / index / next) at the bottom.
- **Relative links only** (`item-2.html`, never `/item-2.html`) so it works under `username.github.io/REPO/`.
- A clickable card grid is the navigation spine — make tiles responsive (`auto-fill, minmax`).

## Build & verify — offline first
1. Research / gather the real content **before** building (use web search / connectors as needed).
2. Build the pages locally.
3. Verify each page programmatically: HTML parses, tags balanced, **every `<use href="#x">` has a matching `<symbol id="x">`**, and all internal links are relative.
4. **Show me the files to vet before any upload.** Pause for my OK.

## Deploy — only after I approve
- Drive my logged-in GitHub via the Chrome extension: create a **public** repo `{REPO}`, upload the vetted files, enable **Pages → Deploy from a branch → main / root**.
- Confirm the live URL `username.github.io/{REPO}/` renders.
- **Growth:** to add an item later, create its page and flip its tile from `.lock` → live in `index.html`; push both. The card "unlocks" automatically.

## Hosting note
Keep the Google Fonts `<link>` and any `color-mix()` for hosted sites — GitHub Pages has internet, and offline vetting on a laptop with internet renders the real fonts. **Only** strip the fonts link + swap `color-mix()` for fixed hex if you specifically need a single `.html` that opens **offline on a phone**.
