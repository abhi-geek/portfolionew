# AI Instructions: Single-Page Personal Portfolio Website

## Goal

Create a **single-page personal portfolio website** using the same visual direction as the generated sample page: a calm, centered, Substack-like personal website with retro pixel-art details, soft SaaS cards, and a refined founder/operator aesthetic.

The page should feel personal, thoughtful, technical, and premium. It should not feel like a generic portfolio template or a gaming website.

---

## Core Design Concept

Design a **center-aligned editorial portfolio page** inspired by:

- soft SaaS landing pages
- Substack-style centered reading layouts
- retro-futuristic 16-bit pixel art
- startup guidebook / founder manual aesthetics
- clean personal essays
- calm technical blogs

The page should combine:

> A narrow editorial content column, large blank side lanes, warm grid-paper background, rounded white cards, monospace labels, modern typography, and polished 16-bit pixel-art illustrations.

---

## Most Important Layout Rule

The entire page must be designed around a **single centered content column**.

### Layout Requirements

- Page background spans full width.
- Primary content sits in the center only.
- Left and right lanes remain mostly blank.
- Use a content max-width of around **680px to 760px**.
- The page should feel like a Substack essay, not a full-width SaaS landing page.
- Avoid multi-column page layouts except inside cards where a small thumbnail sits to the right of text.
- Do not use heavy navigation or a crowded hero.

Recommended structure:

```css
body {
  background: #F7F4EE;
}

.page {
  width: 100%;
  min-height: 100vh;
}

.content-column {
  max-width: 720px;
  margin: 0 auto;
  padding: 56px 24px 72px;
}
```

---

## Page Background

Use a warm off-white background with a very subtle grid.

### Background Color

Primary background:

```css
#F7F4EE
```

Alternative warm neutrals:

```css
#FAF7F1
#F6F2EA
#F8F5EF
```

### Grid Background

Use thin, low-opacity grid lines. The grid should be visible only subtly.

```css
body {
  background-color: #F7F4EE;
  background-image:
    linear-gradient(rgba(35, 35, 35, 0.035) 1px, transparent 1px),
    linear-gradient(90deg, rgba(35, 35, 35, 0.035) 1px, transparent 1px);
  background-size: 48px 48px;
}
```

The grid should feel like notebook paper, engineering paper, or a quiet technical blueprint.

Do not make the grid high-contrast.

---

## Color Scheme

The color palette should be restrained, warm, and technical.

### Core Colors

```css
--background: #F7F4EE;
--surface: #FFFDF8;
--surface-soft: #FBF8F1;
--text-primary: #2B2A28;
--text-secondary: #6F6A64;
--text-muted: #9A948C;
--border: #E2DDD4;
--border-soft: #EEE9E1;
--shadow: rgba(40, 36, 30, 0.08);
```

### Accent Colors

Accent colors should mainly come from pixel-art illustrations.

Use accents sparingly:

```css
--accent-blue: #168BD8;
--accent-rust: #B85A37;
--accent-green: #82B65B;
--accent-yellow: #E7B94F;
```

The UI itself should stay mostly neutral. Bright colors should appear primarily inside the pixel-art visuals.

---

## Typography

Use clean, modern typography with small monospace details.

### Recommended Fonts

Use a modern sans-serif for headings and body:

- Inter
- Geist Sans
- Satoshi
- Suisse Int'l
- Manrope
- Helvetica Neue

Use monospace for labels and metadata:

- Geist Mono
- IBM Plex Mono
- JetBrains Mono
- SF Mono
- Berkeley Mono

### Font Pairing

Recommended:

```css
--font-sans: "Inter", "Geist", "Helvetica Neue", Arial, sans-serif;
--font-mono: "Geist Mono", "IBM Plex Mono", "SF Mono", monospace;
```

### Typography Style

The typography should be:

- sharp
- readable
- quiet
- editorial
- not overly decorative
- not startup-flashy

### Hero Heading

Large, centered, and confident.

```css
.hero-title {
  font-family: var(--font-sans);
  font-size: clamp(52px, 7vw, 76px);
  line-height: 0.95;
  letter-spacing: -0.055em;
  font-weight: 650;
  color: var(--text-primary);
}
```

### Subtitle

```css
.hero-subtitle {
  font-size: 17px;
  line-height: 1.5;
  color: var(--text-primary);
  font-weight: 400;
}
```

### Body Text

```css
.body-text {
  font-size: 14px;
  line-height: 1.75;
  color: var(--text-secondary);
}
```

### Monospace Labels

Use small uppercase monospace labels for section markers.

```css
.section-label {
  font-family: var(--font-mono);
  font-size: 11px;
  line-height: 1;
  letter-spacing: 0.14em;
  text-transform: uppercase;
  color: var(--text-muted);
}
```

---

## Overall Page Structure

The final page should follow this section order:

1. Header / micro-logo area
2. Hero section
3. Hero portrait card
4. About section
5. Selected Work section
6. Writing / Notes section
7. Principles / Interests section
8. Contact section
9. Footer

Everything should stay aligned to the central content column.

---

## Header / Logo Area

At the top of the page, place a small mascot/logo mark above or beside the micro-label.

### Logo / Mascot

Use the pixel-art brain with black glasses as the website mascot.

Placement:

- top center
- small size, around **32px to 44px wide**
- placed above or inline with `PERSONAL PORTFOLIO / 2026`
- should feel like a tiny personal brand mark

Example layout:

```html
<header class="site-header">
  <img src="/brain-logo.png" class="site-logo" />
  <span class="section-label">Personal Portfolio / 2026</span>
</header>
```

```css
.site-header {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 10px;
  margin-bottom: 18px;
}

.site-logo {
  width: 38px;
  height: auto;
  image-rendering: pixelated;
}
```

---

## Hero Section

The hero should be text-first and centered.

### Content

Use this type of structure:

```text
PERSONAL PORTFOLIO / 2026

Hi, I’m [Name].
Founder-operator building at the frontier of AI and hardware.

I build products, write, and share what I learn about deeptech,
systems thinking, and scaling from zero to one.

[View Work] [Read Notes]
```

### Hero Rules

- Keep all text centered.
- Keep the paragraph short.
- Use no more than two CTA buttons.
- Do not add a heavy nav bar.
- Keep generous breathing room above and below.

### Hero CSS

```css
.hero {
  text-align: center;
  margin-bottom: 34px;
}

.hero-eyebrow {
  margin-bottom: 18px;
}

.hero-title {
  margin: 0 0 16px;
}

.hero-subtitle {
  margin: 0 0 10px;
}

.hero-description {
  max-width: 520px;
  margin: 0 auto 24px;
  font-family: var(--font-mono);
  font-size: 12px;
  line-height: 1.65;
  color: var(--text-muted);
}
```

---

## Buttons

Use soft rounded buttons with subtle hover states.

### Primary Button

```css
.button-primary {
  background: #2B2A28;
  color: #FFFDF8;
  border: 1px solid #2B2A28;
  border-radius: 10px;
  padding: 10px 18px;
  font-size: 13px;
  font-weight: 500;
  box-shadow: 0 8px 18px rgba(43, 42, 40, 0.12);
}
```

### Secondary Button

```css
.button-secondary {
  background: rgba(255, 253, 248, 0.72);
  color: #2B2A28;
  border: 1px solid #DDD7CE;
  border-radius: 10px;
  padding: 10px 18px;
  font-size: 13px;
  font-weight: 500;
}
```

### Hover

```css
.button-primary:hover,
.button-secondary:hover {
  transform: translateY(-1px);
}
```

Use transitions:

```css
transition: transform 180ms ease, box-shadow 180ms ease, border-color 180ms ease;
```

---

## Hero Portrait Card

The main visual card should feature the person in pixel-art style.

### Image Style

Use the attached portrait reference as the basis.

The person should have:

- warm smile
- black glasses
- short dark hair
- rust / burnt orange sweater
- friendly founder/operator energy
- polished 16-bit pixel-art rendering

### Portrait Card Scene

Place the portrait inside a rounded landscape card.

Suggested background elements:

- bookshelf
- small plant
- laptop with code
- window with blue sky and clouds
- the brain-with-glasses mascot as a tiny object on shelf or mug

The card should feel like a calm personal workspace.

### Card CSS

```css
.hero-card {
  width: 100%;
  overflow: hidden;
  border-radius: 18px;
  border: 1px solid var(--border);
  background: var(--surface);
  box-shadow:
    0 20px 45px rgba(40, 36, 30, 0.08),
    0 2px 8px rgba(40, 36, 30, 0.06);
  padding: 8px;
  margin: 0 auto 34px;
}

.hero-card img {
  width: 100%;
  display: block;
  border-radius: 12px;
  image-rendering: pixelated;
}
```

---

## Pixel Art Direction

All illustrations should use the same pixel-art language.

### Style Keywords

Use this description for generated assets:

> polished 16-bit pixel art, retro-futuristic editorial illustration, crisp pixel edges, bright but controlled colors, clean silhouettes, subtle dithering, simple shading, optimistic sci-fi tone, indie-game chapter-card style, no cartoon exaggeration, no childish gaming UI.

### Pixel Art Rules

- Use pixel art as editorial accents.
- Keep visuals clean and polished.
- Use bright blues, greens, rusts, and warm yellows inside illustrations.
- Keep the UI around them neutral.
- Use rounded cards around pixel art.
- Do not use pixel art everywhere.
- Do not make the website feel like a retro game menu.
- Do not add animated sprites or noisy pixel backgrounds.

### Image Rendering CSS

```css
.pixel-art {
  image-rendering: pixelated;
  image-rendering: crisp-edges;
}
```

---

## Mascot / Logo Usage

The mascot is a **pixel-art brain wearing black glasses**.

### Usage Rules

Use it in 3–4 subtle places only:

1. Header logo mark
2. Small object in hero portrait card, for example on a shelf or mug
3. One interest pill, such as `Long-term Impact`
4. Small footer accent

Do not overuse it.

The mascot should feel clever and memorable, not gimmicky.

### Mascot CSS

```css
.mascot-icon {
  width: 28px;
  height: auto;
  image-rendering: pixelated;
}
```

---

## Section Spacing

Use quiet, rhythmic spacing.

```css
.section {
  margin-top: 42px;
}

.section-header {
  text-align: center;
  margin-bottom: 18px;
}
```

The page should feel compact but not cramped.

Do not add huge landing-page spacing between every section.

---

## About Section

The about section should be a small centered essay paragraph.

### Layout

```html
<section class="about section">
  <div class="section-header">
    <span class="section-label">About</span>
  </div>
  <p class="about-text">
    I’m a builder at heart. Over the last decade, I’ve shipped products,
    led teams, and worked across AI, robotics, and developer tools.
    These days, I’m focused on ambitious problems with long time horizons,
    where technology can create real leverage for humanity.
  </p>
</section>
```

### Style

```css
.about-text {
  max-width: 560px;
  margin: 0 auto;
  text-align: center;
  font-family: var(--font-mono);
  font-size: 13px;
  line-height: 1.75;
  color: var(--text-secondary);
}
```

---

## Selected Work Section

Use three stacked project cards.

### Card Structure

Each card should include:

- small monospace category label
- project title
- 2-line description
- subtle CTA link
- pixel-art thumbnail on the right

### Example Content

```text
PRODUCT STRATEGY
Orion Planner
Roadmapping and GTM strategy for a B2B SaaS platform used by modern product teams to plan with confidence.
View case study →
```

```text
AI TOOLS
Signal Lab
Building developer tools that make it easier to ship reliable AI workflows in production.
View case study →
```

```text
DEEPTECH STORYTELLING
Ground Truth
Writing long-form narratives on frontier companies and the builders shaping our technological future.
Read feature →
```

### Project Card CSS

```css
.work-list {
  display: flex;
  flex-direction: column;
  gap: 14px;
}

.work-card {
  display: grid;
  grid-template-columns: 1fr 220px;
  gap: 22px;
  align-items: center;
  padding: 20px;
  border: 1px solid var(--border);
  border-radius: 18px;
  background: rgba(255, 253, 248, 0.82);
  box-shadow: 0 10px 24px rgba(40, 36, 30, 0.045);
  transition: transform 180ms ease, box-shadow 180ms ease, border-color 180ms ease;
}

.work-card:hover {
  transform: translateY(-2px);
  box-shadow: 0 16px 36px rgba(40, 36, 30, 0.075);
  border-color: #D7D0C5;
}

.work-card-label {
  font-family: var(--font-mono);
  font-size: 10px;
  letter-spacing: 0.11em;
  text-transform: uppercase;
  color: var(--text-muted);
  margin-bottom: 8px;
}

.work-card-title {
  font-size: 22px;
  line-height: 1.15;
  letter-spacing: -0.03em;
  color: var(--text-primary);
  margin: 0 0 8px;
}

.work-card-description {
  font-size: 13px;
  line-height: 1.55;
  color: var(--text-secondary);
  margin-bottom: 16px;
}

.work-card-link {
  font-family: var(--font-mono);
  font-size: 12px;
  color: var(--text-primary);
  text-decoration: none;
}

.work-card-thumb {
  width: 100%;
  aspect-ratio: 16 / 9;
  object-fit: cover;
  border-radius: 12px;
  border: 1px solid var(--border-soft);
  image-rendering: pixelated;
}
```

### Mobile Behavior

On mobile, stack the thumbnail below or above the text.

```css
@media (max-width: 680px) {
  .work-card {
    grid-template-columns: 1fr;
  }
}
```

---

## Writing / Notes Section

This section should feel like a Substack-style reading list.

### Layout

Use one rounded card containing multiple rows.

Each row includes:

- small document icon on left
- title
- one-line summary
- category and date on the right

### Example Rows

```text
The Compounding Edge of Technical Distribution
Why builder-led distribution is the new moat.
STRATEGY / MAY 18, 2026
```

```text
Lessons from Shipping AI Features at Scale
What actually breaks, and how to design for it.
AI / PRODUCT / MAY 03, 2026
```

```text
Interfaces for Intelligent Systems
Designing UIs that collaborate with models, not just display them.
DESIGN / APR 21, 2026
```

### CSS

```css
.notes-card {
  border: 1px solid var(--border);
  border-radius: 16px;
  background: rgba(255, 253, 248, 0.76);
  box-shadow: 0 10px 24px rgba(40, 36, 30, 0.04);
  overflow: hidden;
}

.note-row {
  display: grid;
  grid-template-columns: 28px 1fr auto;
  gap: 14px;
  align-items: center;
  padding: 15px 18px;
  border-bottom: 1px solid var(--border-soft);
  transition: background 160ms ease;
}

.note-row:last-child {
  border-bottom: none;
}

.note-row:hover {
  background: rgba(246, 242, 234, 0.7);
}

.note-icon {
  color: var(--text-muted);
}

.note-title {
  font-size: 13px;
  font-weight: 600;
  color: var(--text-primary);
  margin-bottom: 3px;
}

.note-summary {
  font-size: 12px;
  color: var(--text-secondary);
}

.note-meta {
  font-family: var(--font-mono);
  font-size: 10px;
  line-height: 1.45;
  letter-spacing: 0.08em;
  text-transform: uppercase;
  color: var(--text-muted);
  text-align: right;
}
```

---

## Principles / Interests Section

Use a short section with pill tags.

### Tags

Example tags:

- AI Infrastructure
- Biosignals
- Design Systems
- Deeptech
- Developer Tools
- Systems Thinking
- Long-term Impact

### Pill Style

```css
.pill-list {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  gap: 10px;
}

.pill {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  padding: 9px 13px;
  border-radius: 999px;
  border: 1px solid var(--border);
  background: rgba(255, 253, 248, 0.72);
  color: var(--text-primary);
  font-size: 12px;
  box-shadow: 0 6px 14px rgba(40, 36, 30, 0.035);
}

.pill svg,
.pill img {
  width: 15px;
  height: 15px;
}
```

Below the pills, add a short centered line:

```text
Long-term thinking. Technical depth. Clear communication.
```

Style:

```css
.principles-line {
  margin-top: 18px;
  text-align: center;
  font-family: var(--font-mono);
  font-size: 13px;
  color: var(--text-secondary);
}
```

---

## Contact Section

The contact section should be quiet and simple.

### Content

```text
LET’S CONNECT
I’m always open to thoughtful conversations and exciting projects.

Email    LinkedIn    X    Newsletter
```

### Style

```css
.contact {
  text-align: center;
  margin-top: 36px;
}

.contact-text {
  font-family: var(--font-mono);
  font-size: 12px;
  color: var(--text-secondary);
  margin: 12px 0 18px;
}

.contact-links {
  display: flex;
  justify-content: center;
  gap: 26px;
  flex-wrap: wrap;
}

.contact-link {
  display: inline-flex;
  align-items: center;
  gap: 7px;
  color: var(--text-primary);
  font-size: 12px;
  text-decoration: none;
}

.contact-link:hover {
  color: #000;
}
```

---

## Footer

Use a tiny centered footer.

```css
.footer {
  margin-top: 36px;
  text-align: center;
  font-family: var(--font-mono);
  font-size: 11px;
  color: var(--text-muted);
}
```

Example:

```text
© 2026 [Name]. All rights reserved.
```

---

## Icons

Use thin-line icons that match the minimal UI.

### Recommended Icon Style

- 1.5px stroke
- rounded caps
- minimal outlines
- monochrome charcoal/grey
- no filled colorful icons except the mascot

### Suggested Icon Set

Use Lucide icons or equivalent:

- Mail
- Linkedin
- Twitter / X
- Newspaper / Mailbox
- FileText
- Cpu
- Activity
- Layers
- Rocket
- ChartNoAxesCombined
- Brain or custom mascot image

### Icon CSS

```css
.icon {
  width: 16px;
  height: 16px;
  stroke-width: 1.6;
  color: currentColor;
}
```

---

## Scroll Style

The page should feel smooth and quiet while scrolling.

### Smooth Scroll

```css
html {
  scroll-behavior: smooth;
}
```

### Custom Scrollbar

Keep the scrollbar minimal.

```css
::-webkit-scrollbar {
  width: 10px;
}

::-webkit-scrollbar-track {
  background: #F7F4EE;
}

::-webkit-scrollbar-thumb {
  background: #D8D1C7;
  border: 3px solid #F7F4EE;
  border-radius: 999px;
}

::-webkit-scrollbar-thumb:hover {
  background: #C7BFB3;
}
```

---

## Motion and Interaction

Use subtle motion only.

### Approved Interactions

- cards lift by 1–2px on hover
- buttons lift slightly
- links darken on hover
- section content fades in gently on scroll
- pixel art can have very subtle float/parallax if used carefully

### Avoid

- aggressive animations
- large parallax effects
- animated cursors
- blinking pixels
- heavy 3D effects
- game-like transitions

### Motion CSS

```css
.fade-in {
  opacity: 0;
  transform: translateY(10px);
  transition: opacity 500ms ease, transform 500ms ease;
}

.fade-in.visible {
  opacity: 1;
  transform: translateY(0);
}
```

Respect reduced motion:

```css
@media (prefers-reduced-motion: reduce) {
  html {
    scroll-behavior: auto;
  }

  *, *::before, *::after {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
  }
}
```

---

## Component Summary

Create these components:

### `PageShell`

- full-width background
- centered content column
- subtle grid background

### `HeaderMark`

- brain-with-glasses mascot
- small portfolio label

### `Hero`

- large name heading
- subtitle
- short description
- two CTA buttons

### `HeroPortraitCard`

- rounded pixel-art portrait card
- person portrait based on reference image
- workspace scene
- subtle mascot use

### `SectionLabel`

- small uppercase monospace label

### `AboutSection`

- centered essay paragraph

### `WorkCard`

- label
- title
- description
- text link
- pixel-art thumbnail

### `NotesList`

- rounded card
- note rows
- icon, title, summary, metadata

### `InterestPill`

- rounded pill
- line icon or mascot

### `ContactSection`

- closing line
- email/social/newsletter links

### `Footer`

- copyright line

---

## Image Asset Instructions

### Hero Portrait Image Prompt

Use this prompt to generate the main hero portrait illustration:

```text
Create a polished 16-bit pixel-art portrait illustration of a young founder/operator based on the reference image. He has short dark hair, black glasses, a warm smile, and wears a rust/burnt-orange sweater. Place him in a calm personal workspace with a bookshelf, a small plant, a laptop showing code, and a window with bright blue sky and clouds. Include a tiny brain-with-glasses mascot as a subtle object on a shelf or mug. Style: refined retro pixel art, crisp pixel edges, warm shadows, bright but controlled colors, editorial website illustration, not cartoonish, not gaming UI.
```

### Project Thumbnail Prompts

#### Product Strategy Thumbnail

```text
Polished 16-bit pixel-art illustration of a calm product strategy workspace, large window with bright blue sky and clouds, desk with laptop showing charts and roadmap cards, small plant, warm light, clean retro-futuristic editorial style, crisp pixels, rounded-card friendly composition.
```

#### AI Tools Thumbnail

```text
Polished 16-bit pixel-art illustration of a developer workstation with terminal/code on screen, small hardware devices, warm desk, coffee mug, window with greenery and blue sky, clean retro-futuristic technical style, crisp pixel edges, subtle dithering.
```

#### Deeptech Storytelling Thumbnail

```text
Polished 16-bit pixel-art illustration of a large satellite dish in a desert research landscape under bright blue sky and white clouds, retro sci-fi editorial chapter-card style, crisp pixelated edges, warm desert tones, optimistic technical mood.
```

### Mascot Prompt

```text
Create a small pixel-art mascot logo of a human brain wearing black rectangular glasses. The brain should be light cream and grey with simple anatomical folds, black glasses, crisp pixel edges, subtle shading, transparent background, clever and friendly but not cartoonish.
```

---

## Accessibility

Follow basic accessibility rules:

- Use semantic HTML.
- Use sufficient text contrast.
- Add alt text to all images.
- Ensure buttons and links are keyboard accessible.
- Use focus-visible outlines.
- Do not rely only on color for meaning.

### Focus Style

```css
:focus-visible {
  outline: 2px solid rgba(43, 42, 40, 0.45);
  outline-offset: 3px;
  border-radius: 8px;
}
```

---

## Responsive Behavior

### Desktop

- max content width: 720px
- hero title large
- project cards use text left, image right
- large blank lanes on left/right

### Tablet

- content max width around 680px
- slightly smaller hero title
- project cards can remain two-column if space allows

### Mobile

- content width: full minus 20px padding on each side
- hero title around 44px
- project cards stack vertically
- contact links wrap
- image cards remain full-width

Mobile CSS:

```css
@media (max-width: 680px) {
  .content-column {
    padding: 40px 18px 56px;
  }

  .hero-title {
    font-size: 46px;
    letter-spacing: -0.045em;
  }

  .hero-description {
    font-size: 11px;
  }

  .work-card {
    grid-template-columns: 1fr;
    padding: 16px;
  }

  .note-row {
    grid-template-columns: 24px 1fr;
  }

  .note-meta {
    grid-column: 2;
    text-align: left;
    margin-top: 4px;
  }
}
```

---

## Visual Quality Checklist

Before finalizing the page, check:

- The page has a single centered content column.
- Left and right lanes are mostly blank.
- The background grid is subtle.
- The UI is warm off-white, not stark white.
- The hero is clean and centered.
- The portrait card is the main visual anchor.
- Pixel art is polished and sparse.
- The brain mascot appears subtly, not everywhere.
- Cards have rounded corners, borders, and gentle shadows.
- Text is readable and not too small.
- Section labels use monospace uppercase styling.
- Work cards are stacked vertically.
- Notes section feels like a Substack reading list.
- Motion is subtle.
- The page feels personal, premium, and technical.

---

## Things To Avoid

Do not create:

- a full-width corporate landing page
- a dense dashboard UI
- a gaming website
- a dark cyberpunk page
- a neon pixel-art page
- an over-animated portfolio
- a generic Webflow-style template
- a cluttered founder homepage
- sidebars with lots of content
- heavy navigation
- huge gradients
- glassmorphism overload
- multiple competing illustrations

---

## Final One-Shot Prompt

Use the following prompt to generate or implement the page:

```text
Create a single-page personal portfolio website with a centered Substack-style editorial layout and large blank side lanes. The visual style should combine soft SaaS minimalism, a warm off-white grid-paper background, rounded white cards, subtle shadows, modern typography, small uppercase monospace labels, and polished 16-bit pixel-art illustrations.

The content should sit inside a narrow center column around 720px wide. The left and right sides of the page should remain mostly empty. Do not create a full-width startup landing page.

At the top, place a small pixel-art brain-with-glasses mascot as the logo, followed by a tiny monospace label reading PERSONAL PORTFOLIO / 2026. The hero should be centered with a large headline, short founder/operator positioning line, one concise paragraph, and two soft CTA buttons.

Below the hero, add a large rounded portrait card using the provided person reference: a young founder/operator with short dark hair, black glasses, a warm smile, and a rust-colored sweater. Render him in polished 16-bit pixel-art style inside a calm workspace with bookshelf, laptop with code, window with blue sky and clouds, and subtle use of the brain mascot.

Continue with sections for About, Selected Work, Writing / Notes, Principles / Interests, Contact, and Footer. Use small uppercase monospace labels for each section. Selected Work should have three stacked rounded cards with left-aligned text and right-side pixel-art thumbnails. Writing / Notes should look like a Substack reading list with thin dividers, document icons, titles, summaries, dates, and categories. Principles should use rounded pill tags with thin-line icons. Contact should be quiet and centered with simple links.

Use warm neutral colors: off-white background #F7F4EE, white/cream cards #FFFDF8, charcoal text #2B2A28, muted grey text #6F6A64, light borders #E2DDD4. Pixel art can use controlled blues, greens, rust, and yellow accents. Use Inter or Geist Sans for main typography and Geist Mono or IBM Plex Mono for labels and metadata.

Add smooth scrolling, subtle hover lifts on cards and buttons, minimal custom scrollbar, and gentle fade-in-on-scroll animations. Keep the experience calm, refined, personal, technical, and premium. Avoid dark mode, neon, heavy animations, gaming UI, clutter, and full-width layouts.
```
