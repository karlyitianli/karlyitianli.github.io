# Karl Li — Personal Site

Personal portfolio site for Karl Li, Product Designer based in Vancouver, BC.
Live at https://karlyitianli.github.io/, hosted on GitHub Pages.

This site is an exact copy of the Framer project `karls.design`
(https://karlli.framer.website/), rebuilt as static HTML, CSS, and JavaScript
on Nov 13, 2026. No framework, no build step, no bundler. Edit a file, push
to `main`, GitHub Pages serves it.

## Pages

- `/` — Homepage. Sticky sidebar (portrait, Vancouver clock, Resume,
  LinkedIn, Email, Download resume button) and five case study cards:
  WATS 2025–2026, Greenhouse 2024–2025, Level 2022–2023, Attentive
  2021–2022, Quil 2020–2021.
- `/level/` — Level case study, "Receipt review". Three-column layout: a
  sticky section nav on the left (Back, Problem, Solution, Outcomes,
  Reflection, Next), the case study in the centre, and project details on
  the right (Role: Senior Product Designer, Team: Eng, Data, Ops, Timeline:
  3 weeks, Skills: Product strategy, Systems thinking). Stacks to one
  column on Phone and Small Phone, where the right details panel is hidden.
- `/design-system/` — Design system reference for this site: colour tokens,
  typography, components, and layout breakpoints, with live samples.
  Tappable tabs (Overview, Colours, Typography, Components, Layout) with
  keyboard arrow navigation and `#hash` routing.

## Design tokens

- Surface `#fcfcfc`, Tan `#f9f3e6`, Beige `#f5f2eb`, Ink `#292929`,
  Muted `#7e7e7e`, Gold `#b58900`, Gold hover `#806000`,
  Border `rgba(18, 18, 18, 0.07)`, White `#ffffff`, Icon grey `#707070`.
- Page background is a 15x15px grid SVG (`grid.svg`, stroke `#121212` at 0.07 opacity) tiled over Surface.
- Breakpoints: Desktop 1440px+, Laptop 1280–1439px, Tablet 1024–1279px,
  Phone 768–1023px, Small Phone under 768px.

## Typography and icons

- Inter 4.000, loaded from Framer's own `.woff2` files (weights 400, 500,
  600), not Google Fonts, because Google's static Inter strips the
  character variant features. OpenType features `cv03, cv04, cv09, cv11,
  blwf` are on everywhere; in Inter 4 the single-storey "a" is `cv11`.
- DM Mono (weight 400, from Google Fonts) for the small location, clock,
  and label text.
- Phosphor Icons, `@phosphor-icons/web 2.1.1`, regular weight.

## Interactive bits

- Live Vancouver clock, updating every second via
  `Intl.DateTimeFormat` with `timeZone: "America/Vancouver"`, with a
  blinking colon (CSS `1s steps(1)` animation).
- Copy-email button: copies `karl.yitian.li@gmail.com` via
  `navigator.clipboard.writeText` and shows "Copied!" for 1 second.
- Cursor tooltip: a shared pill follows the mouse (+16px offset, clamped
  to the viewport). Resume and LinkedIn show "Open tab" with a Phosphor
  Arrow Square Out icon, Email shows "Copy" with a Copy icon. The native
  pointer cursor stays visible; touch devices show no tooltip. Contact
  rows dim to 0.5 opacity on hover.
- All JavaScript is vanilla, one inline `<script>` block per page.

## Images and favicon

- Images are public Framer URLs (`framerusercontent.com/images/`), not
  committed to the repo. Case study previews keep a 2160x1350 aspect ratio.
- `favicon.ico` at the repository root: the portrait photo, square cropped
  with a circular (999px radius) mask, in 16, 32, 48, 64, 128, and 256px
  sizes inside one ICO file. It is a binary file, so it was uploaded
  through the GitHub website rather than the API. Every page links it with
  `<link rel="icon" href="/favicon.ico" type="image/x-icon">`.

## Stack

- HTML5, one file per page (`index.html`, `level/index.html`,
  `design-system/index.html`), semantic tags, no templates.
- Hand-written CSS in a single `<style>` block per page, tokens as CSS
  custom properties in `:root`, Flexbox layout, no preprocessor or
  framework.
- Vanilla JavaScript, no libraries or modules.
- Hosting: GitHub Pages, free static hosting, branch `main`, no custom
  domain, HTTPS by default. Deploys automatically on every push, usually
  live in about a minute, with `Cache-Control: max-age=600`, so hard
  refresh or add `?v=N` to see a fresh copy. No Vercel, no Cloudflare, no
  server, no database, no analytics.
- Source of truth for the design is Framer, project `karls.design`,
  inspected through Framer MCP.
- Muse AI is the editor and agent of choice for this site: pages are
  built, edited, and pushed through Muse, Meta's personal AI agent,
  working over WhatsApp.

## History

- Nov 13, 2026: homepage copied from Framer and pushed, replacing the
  earlier "Hello world" page. Fixes the same day: Inter single-storey "a"
  (Framer Inter 4.000 files, `cv11`), 1px Border token on case study
  cards, Phosphor icons, blinking clock colon, sidebar gap and contact
  row dividers corrected to match Framer, cursor tooltip added.
- Nov 13, 2026: `/design-system/` page added, with the full Stack section
  (HTML, CSS, JS, fonts, icons, images, favicon, hosting, editing).
  Tables and live sample cards use a white fill with the Border token
  border, including the outer table border.
- Nov 13, 2026: circular portrait `favicon.ico` added.
- Nov 13, 2026: `/level/` case study page added, copied from the Framer
  Level page (`/level`, node `QCxVJJyTA`).

## Old content

- `test-storybook/` — an earlier Storybook experiment, left as is.
