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
- `/attentive/` — Attentive case study, "Analytics Dashboard". Same
  three-column layout as `/level/`: sticky section nav on the left, case
  study in the centre, project details on the right (Role: Product
  Designer, Team: PM, Eng, Design Systems, Timeline: 4 months, Skills:
  User research, Data visualization). Content comes from Karl's 2021
  portfolio presentation doc, written up concise, with the homepage
  dashboard screenshot reused as the hero for now.
- `/wats/`, `/greenhouse/`, `/quil/` — Empty placeholder pages for the
  other case studies, in the same three-column layout as `/level/` with
  blank middle and right columns for now. They will be filled in
  following the `/level/` example.
- Back and Next: every case study page has Back to the homepage and Next
  to the next case study in homepage order (WATS, Greenhouse, Level,
  Attentive, Quil), landing on placeholders too, and wrapping from Quil
  back to WATS. Next stays plain "Next", no company name.
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

Everything below was done in one working session on Nov 13, 2026,
rebuilding the site from Framer `karls.design` as static HTML on GitHub
Pages. All commits are on `main` in `karlyitianli.github.io`, newest first.

- Root-relative links: every internal link on the site changed from
  `./slug` to `/slug` and Back from `./` to `/`. The relative links
  broke on the case study pages because they live in subdirectories:
  Next on `/greenhouse/` resolved to `/greenhouse/level` (404) and Back
  resolved to the same page. Root-relative links always resolve from
  the domain root, so Back always lands on the homepage and Next always
  lands on the next case study. The section pills on `/level/` and
  `/attentive/` (`/level#problem` etc.) and the Design System breadcrumb
  were fixed the same way.
- `c909fe9` — Back and Next wired on all case study pages. Back goes
  to the homepage. Next follows homepage order (WATS, Greenhouse, Level,
  Attentive, Quil), lands on placeholders too, and wraps from Quil back
  to WATS. Next stays plain "Next". The three placeholder pages now use
  the same three-column layout as `/level/`, with blank middle and right
  columns for now.
- `60369c9` — `/attentive/` case study page added, "Analytics
  Dashboard", in the same layout as `/level/`, with concise copy written
  from Karl's 2021 portfolio presentation doc (Google Doc
  12cBcqKUov3rqaenvKNEiURhKeKQC41LFkjjZ1LcY_lw). Hero is the homepage
  dashboard screenshot reused for now. Project details: Product
  Designer, PM / Eng / Design Systems, 4 months, User research and Data
  visualization. Salary, leaving reasons, and interview prep from the
  doc were left out.
- `9426ccb` — Small Phone breakpoint: the About text collapses into one
  flowing paragraph too, matching Framer's Small Phone frame.
- `ddb158f` — Phone breakpoint (768–1023.98px): the About text collapses
  into one flowing paragraph with no line breaks. Framer's Phone frame
  already holds it as a single text node; the copy had split it into
  three paragraphs.
- `38d9425` — Pill hover states on `/level/` use `--border` instead of
  `--tan`.
- `5a55d30` — README notes the four empty case study placeholder pages.
- `c11a367` — Empty placeholder pages for WATS, Greenhouse, Attentive,
  and Quil (`/wats/`, `/greenhouse/`, `/attentive/`, `/quil/`), each the
  company name, "Coming soon.", and a Back link, and their homepage cards
  are now links to them.
- `0eeeb96` — Page background changed to a new 15x15px `grid.svg` in the
  repo root (stroke `#121212` at 0.07 opacity), tiled over Surface on
  every page, replacing the 21x21px Framer Grid.svg.
- `574a639` — Circular portrait `favicon.ico` uploaded (binary, 155 KB,
  16–256px sizes inside one ICO file) through the GitHub website, after
  Karl signed in and completed 2FA himself. Verified live 200.
- `8b61af5` — README rewritten as a summary of the whole site as rebuilt
  (pages, tokens, typography, interactive bits, stack, history),
  replacing the stale "based in Philly / currently at Greenhouse" text.
- `16fd72e` — `/level/` case study page added, copied from the Framer
  Level page (`/level`, node `QCxVJJyTA`): "Receipt review", hero
  level.png 2160x1350 radius 16, Problem, Solution, Outcomes, and
  Reflection sections with exact copy and numbered lists, sticky left
  nav 128px and right project details 256px, white panels with 1px
  Border, radius 8, stacking on Phone and Small Phone.
- `20db197` — Live sample cards on `/design-system/` changed from tan to
  a white fill with the Border token border, matching the tables.
- `653cba2` — Table outer border fixed: `border-collapse: separate` with
  `border-spacing: 0`, so the 1px Border shows all around. The first push
  timed out in the tool result but had actually landed.
- `36c6d61` — Tables changed to a white fill with the Border token
  border, and the Stack section now names Muse AI as the editor and
  agent of choice.
- `d210cf6` — Stack section on `/design-system/` expanded with the exact
  HTML, CSS, JS, fonts, icons, images, favicon, hosting, and editing
  details.
- `7c1ead9`, `fbfc991` — `<link rel="icon" href="/favicon.ico">` added
  to the homepage and the design system page.
- `c9a69cf` — `/design-system/` page added, with tabs Overview, Colours,
  Typography, Components, and Layout, keyboard arrow navigation, hash
  routing, and live samples.
- `59517b5` — Cursor tooltip added: a shared pill follows the mouse
  (+16px offset, clamped to the viewport), native pointer cursor kept,
  "Open tab" for Resume and LinkedIn, "Copy" switching to "Copied!" for
  1 second on Email, rows dim to 0.5 opacity on hover, nothing special
  on touch devices.
- `acdf381` — Extra 24px removed from the sidebar: Framer's Sidebar gap
  is 0, the 24px before the Download button comes from Contact
  padding-bottom alone. All three contact rows now have the 1px
  `rgba(18, 18, 18, 0.07)` bottom border with 4px 0 padding.
- `7e8447a` — Typography root cause fixed: Framer serves full Inter 4.000
  with all character variant features, Google Fonts' static Inter strips
  them, so the site now loads Framer's Inter 4.000 latin files (weights
  400/500/600). In Inter 4 the single-storey "a" is `cv11`, not `cv03`.
- `23df0ea` — Case study cards got the 1px Border token, icons switched
  from hand-drawn SVGs to Phosphor (`@phosphor-icons/web 2.1.1`, Framer's
  icon set is literally named "Phosphor"), and the clock colon blinks via
  a CSS 1s steps animation.
- `d028006` — First attempt at the single-storey "a": `font-feature-settings`
  `cv03/cv04/cv09/cv11/blwf` added. Later found insufficient, fixed properly
  in `7e8447a`.
- `4cbf3d1` — Homepage replaced with the exact Framer copy: sticky tan
  sidebar, portrait, live Vancouver clock, Resume/LinkedIn/Email,
  Download resume button, and the five case study cards (WATS,
  Greenhouse, Level, Attentive, Quil), with images via public
  Framer URLs.
- `b6444e0` — GitHub connected as karlyitianli and a hello world page
  pushed, live at https://karlyitianli.github.io/.

## Old content

- `test-storybook/` — an earlier Storybook experiment, left as is.
