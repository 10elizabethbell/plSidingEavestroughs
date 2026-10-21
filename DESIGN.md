---
name: PL Siding and Eaves
description: Calm band pitch site for a proudly Canadian eavestrough and siding crew in Windsor and Essex County.
colors:
  paper: "#f4f6fb"
  card: "#ffffff"
  field: "#e6ecf5"
  ink: "#12253d"
  body: "#2a3a4c"
  soft: "#4a5868"
  navy: "#1d3b60"
  deep: "#10223a"
  on-dark: "#f4f7fb"
  on-dark-soft: "#c9d6e6"
  amber: "#f2a33a"
  amber-2: "#f7b95e"
  amber-ink: "#8a4a00"
  line: "rgba(18,37,61,.12)"
  focus: "#1f5fa8"
  error: "#b3261e"
typography:
  display:
    fontFamily: "Cal Sans, Avenir Next, Segoe UI, system-ui, sans-serif"
    fontSize: "clamp(42px, 12vw, 80px)"
    fontWeight: 400
    lineHeight: 1.02
    letterSpacing: "-.005em"
  headline:
    fontFamily: "Cal Sans, Avenir Next, Segoe UI, system-ui, sans-serif"
    fontSize: "clamp(30px, 7.6vw, 48px)"
    fontWeight: 400
    lineHeight: 1.08
    letterSpacing: "-.005em"
  title:
    fontFamily: "Cal Sans, Avenir Next, Segoe UI, system-ui, sans-serif"
    fontSize: "clamp(20px, 5.4vw, 24px)"
    fontWeight: 400
    lineHeight: 1.15
  body:
    fontFamily: "-apple-system, BlinkMacSystemFont, Segoe UI, Helvetica Neue, Arial, sans-serif"
    fontSize: "16px"
    fontWeight: 400
    lineHeight: 1.7
  lede:
    fontFamily: "-apple-system, BlinkMacSystemFont, Segoe UI, Helvetica Neue, Arial, sans-serif"
    fontSize: "clamp(17px, 4.7vw, 20px)"
    fontWeight: 400
    lineHeight: 1.5
  label:
    fontFamily: "-apple-system, BlinkMacSystemFont, Segoe UI, Helvetica Neue, Arial, sans-serif"
    fontSize: "14px"
    fontWeight: 500
    lineHeight: 1
    letterSpacing: ".02em"
  button:
    fontFamily: "Cal Sans, Avenir Next, Segoe UI, system-ui, sans-serif"
    fontSize: "18px"
    fontWeight: 400
    lineHeight: 1
rounded:
  field: "10px"
  photo: "20px"
  card: "24px"
  pill: "999px"
spacing:
  gutter: "20px"
  gutter-desktop: "40px"
  band: "64px"
  band-desktop: "96px"
  card-pad: "24px"
  column-gap: "64px"
components:
  button-primary:
    backgroundColor: "{colors.amber}"
    textColor: "{colors.ink}"
    typography: "{typography.button}"
    rounded: "{rounded.pill}"
    padding: "0 26px"
    height: "56px"
  button-primary-hover:
    backgroundColor: "{colors.amber-2}"
    textColor: "{colors.ink}"
  button-ghost:
    backgroundColor: "transparent"
    textColor: "{colors.on-dark}"
    typography: "{typography.button}"
    rounded: "{rounded.pill}"
    padding: "0 26px"
    height: "56px"
  eyebrow:
    backgroundColor: "rgba(18,37,61,.06)"
    textColor: "{colors.ink}"
    typography: "{typography.label}"
    rounded: "{rounded.pill}"
    padding: "9px 14px"
  eyebrow-on-dark:
    backgroundColor: "rgba(255,255,255,.12)"
    textColor: "{colors.on-dark}"
  input:
    backgroundColor: "{colors.field}"
    textColor: "{colors.ink}"
    typography: "{typography.body}"
    rounded: "{rounded.field}"
    padding: "13px 14px"
    height: "52px"
  chip:
    backgroundColor: "{colors.field}"
    textColor: "{colors.ink}"
    rounded: "{rounded.pill}"
    padding: "0 18px"
    height: "48px"
  chip-selected:
    backgroundColor: "{colors.ink}"
    textColor: "{colors.card}"
  form-card:
    backgroundColor: "{colors.card}"
    rounded: "{rounded.card}"
    padding: "clamp(20px, 5vw, 32px)"
  offer-card:
    backgroundColor: "{colors.amber}"
    textColor: "{colors.ink}"
    rounded: "{rounded.card}"
    padding: "{spacing.card-pad}"
  photo-card:
    backgroundColor: "{colors.deep}"
    textColor: "{colors.card}"
    rounded: "{rounded.photo}"
  floating-text-circle:
    backgroundColor: "{colors.amber}"
    textColor: "{colors.ink}"
    rounded: "{rounded.pill}"
    size: "60px"
---

# Design System: PL Siding and Eaves

## Overview

**Creative North Star: "Fall in Essex County"**

The site is an instance of Ellie's calm band style, coloured from the client's logo: a black maple leaf behind a house. The logo's black becomes two navies, and fall-maple amber is the single warm accent. The page is a stack of full-bleed bands that alternate light and dark so each new section is obvious on a phone. Shapes are soft and borderless, type is one rounded display webfont (Cal Sans) over a quiet system body, and motion is limited to three deliberate moves: the hero H1's letter bounce-in, one 12px fade-up for content below the first screen, and a floating text circle that slides in once the hero is gone.

Density is low and phone-first. Every band has one job (claim, what a fall cleaning includes, the four services, how it works, the quote form, the closing number), and contact is always one tap away through the header number, the hero buttons, the floating circle and the form. There are no client job photos; the hero is the plain textured navy band, and the four service cards carry AI-generated illustrations of the services (gpt-image-1, provenance in `img/*.webp.json`), never presented as PL Siding and Eaves jobs.

**Key Characteristics:**
- Paper, navy and deep navy bands, with one amber accent used as a fill.
- A faint 135deg line texture on the hero, the deep navy band and the footer.
- Cal Sans at weight 400 for every heading, button, label and phone number; system stack for running text.
- Small eyebrow pills with an amber dot above the hero headline and a few section headings (deliberate house style).
- Hero H1 bounces in letter by letter; nothing else on the page does.
- One floating 60px text circle, never a bottom bar.
- Behaviour switches live in a `CONFIG` object (`FLOAT`, `SMS`, `TEXTS`, `PROMO_END`).

## Colors

Cool off-white paper and two logo-derived navies, warmed by one fall-maple amber that is almost always a fill.

### Primary
- **Fall-Maple Amber** (`amber`): primary button fill, the fall-offer card, numbered step discs, eyebrow dots, the floating circle, the hover fill of arrow circles, the dark-band focus ring and text selection. On dark bands it is also the colour of the heading's last phrase (`.accent`).
- **Light Maple** (`amber-2`): primary button hover only.
- **Maple Ink** (`amber-ink`): amber as text or line icon on light grounds (the light-band heading accent, the claim icons, the header phone icon and its hover). Exists because amber on paper fails contrast.

### Secondary
- **Logo Navy** (`navy`): the hero band, the services band and the closing band.
- **Deep Winter Navy** (`deep`): the "How it works" band and the footer, always with the line texture; also the photo-card backing while images load.

### Neutral
- **Cool Paper** (`paper`): page ground, header, light bands; also `theme-color`.
- **White Card** (`card`): the quote form card and the Facebook row.
- **Field Mist** (`field`): input and unselected chip fill on the white form card (its own token so fields don't vanish at ~1.08:1).
- **Night Ink** (`ink`): headings on light, text on amber, the selected chip fill.
- **Body Slate** (`body`): running text on light.
- **Soft Slate** (`soft`): ledes, hints, the wordmark sub-line, after-form notes.
- **Frost** (`on-dark`) and **Soft Frost** (`on-dark-soft`): headings and running text on navy bands.
- **Hairline** (`line`): the only divider, between claim rows.
- **Focus Blue** (`focus`): focus and hover outlines on light grounds and form controls, deliberately distinct from the amber fill.
- **Error Red** (`error`): inline error sentence and bad-field border.

### Named Rules
**The Fill-Only Amber Rule.** Amber is a fill. Text on amber is Night Ink; amber as text on paper is always Maple Ink. White on amber and amber on paper are never used.

**The Two Focus Colours Rule.** Focus rings are Focus Blue on light grounds and amber inside the hero, navy bands, deep bands and footer.

**The Accent Phrase Rule.** A heading's last phrase may carry the accent (`.accent`): amber on dark bands, Maple Ink on paper. One phrase per heading.

## Typography

**Display Font:** Cal Sans (Google Fonts, `display=swap`, preconnected), falling back to Avenir Next, Segoe UI, system-ui
**Body Font:** system stack (-apple-system, BlinkMacSystemFont, Segoe UI, Helvetica Neue, Arial)

**Character:** Cal Sans gives the friendly, rounded, sign-painted voice; the system body keeps everything else invisible and fast. Cal Sans is always weight 400, and it is used for anything a visitor acts on (buttons, phone numbers, form labels, card titles), not only headings.

### Hierarchy
- **Display** (400, clamp(42px, 12vw, 80px), 1.02): the hero H1 only, white, max 12ch, with the place in it ("Windsor").
- **Headline** (400, clamp(30px, 7.6vw, 48px), 1.08): every section H2, balanced wrapping.
- **Title** (400, 20-28px, 1.1-1.2): claim rows, step titles (21-22px), card titles (16-22px), the offer line, the Facebook row, form labels and legends (18px).
- **Phone** (400, clamp(30px, 9vw, 52px), 1): the closing band's big tap-to-call number; the header number is 17px (20px desktop).
- **Body** (400, 16px, 1.7): running text everywhere; inputs are 16px so iOS doesn't zoom.
- **Lede** (400, clamp(17px, 4.7vw, 20px), 1.5): the hero promise (max 32ch, 40ch desktop) and section ledes (max 38ch).
- **Label** (500, 14px, .02em): eyebrow pills. The wordmark sub-line is the only uppercase text (600, 11px, .08em).

### Named Rules
**The One Display Face Rule.** Cal Sans at 400 for display roles, the system stack for everything else; never a second body font, never a heavier Cal Sans.

**The Hero-Only Bounce Rule.** Only the hero H1 animates letter by letter; no other heading gets a letter reveal.

## Layout

A single centred column, max 1160px, with a 20px phone gutter that becomes 40px at 760px. Bands are full-bleed with 64px vertical padding (96px from 760px); the hero copy sits at 56/64px (96/112px desktop). Section heads stack eyebrow, H2 and lede in a 16px grid, max 640px wide.

Breakpoints: 760px (wider gutter and bands, hero buttons side by side at min 220px), 1024px (two-column split for fall cleaning, four photo cards in a row, sticky form intro beside the form at 1fr / 1.2fr, three steps across, closing name and big number side by side, the faint logo mark in the hero). Below 380px chips tighten their padding.

Phone-first rules: tap targets are 44px or more everywhere (buttons 56px, chips 48px, inputs 52px, links padded to 44px); the header and floating circle respect safe-area insets; the footer reserves bottom space for the floating circle.

## Elevation & Depth

The system is flat. Depth comes from band contrast (paper against navy against deep navy), white cards on paper, and the photo cards' bottom gradient, not from shadows.

### Shadow Vocabulary
- **Float lift** (`box-shadow: 0 10px 28px rgba(8,22,40,.3)`): the floating text circle only, so it reads as above the page.

### Named Rules
**The Flat Bands Rule.** Nothing on the page casts a shadow except the floating text circle.

**The Faint Texture Rule.** Dark-band texture is `repeating-linear-gradient(135deg, transparent 0 22px, rgba(255,255,255,.035) 22px 23px)`, at about 4% white or fainter so it never reads as lines through text. It goes on the hero, the deep navy band and the footer; the mid-navy content bands stay plain.

## Shapes

Soft and borderless. Cards and the form are 24px; photo cards and the Facebook row are 20px; inputs are 10px; buttons, chips, eyebrows, arrow circles, step numbers and the floating action are full circles or pills. Borders appear only as 2px transparent slots that colour on hover, focus or error, plus the single hairline between claim rows. The logo mark (maple leaf points behind a house) is the only illustrative shape; it appears in the header and, at 6% white, low in the desktop hero's right corner.

## Components

### Buttons
Big, round and plain.
- **Shape:** full pill (999px), 56px tall, 26px side padding, Cal Sans 18px, optional 20px icon.
- **Primary:** amber fill with Night Ink text; hover lightens to Light Maple. In the form it is full width and also gains a 2px Focus Blue outline on hover and focus.
- **Ghost:** transparent with a 2px 70% frost border and frost text on dark grounds; hover makes the border white over a 10% white wash.
- **Press:** scale(.98). Hover styles exist only under `(hover:hover)`.
- The hero holds at most two: "Get a quote" (primary) and "Text us" (ghost). There is no Call button in the hero; the header number covers calling.

### Eyebrow pills (deliberate)
Ellie's house choice from the calm band style, recorded as intentional despite the general anti-eyebrow guidance. A quiet 14px label pill with a 7px amber dot, on a 6% ink tint (12% white on dark bands). Used above the hero H1 and a few section heads (here: hero offer, Fall cleaning, Homes and businesses, Windsor and Essex County), never all of them. It is a label, not a button: no arrow, no hover, no shadow, no full-strength amber fill, and never marked up as a heading.

### Cards / Containers
- **Form card:** white, 24px radius, clamp(20px, 5vw, 32px) padding, max 600px.
- **Offer card:** amber fill, 24px radius, 24px padding, Night Ink text, max 520px. Hidden automatically after `CONFIG.PROMO_END`, when the hero eyebrow also switches to "Proudly Canadian".
- **Photo cards:** 4:5, 20px radius, image `object-fit: cover`, a bottom ink gradient (88% to 0 at 58%), a white Cal Sans title and a 36px arrow circle. Two columns on phones, four on desktop. The whole card links to the form and pre-selects the matching job chip. Hover and focus change only the arrow (fills amber). The four images are AI-generated service illustrations, labelled as services, never as the client's jobs.
- **Facebook row:** white 20px row on navy, Facebook logo in its brand blue, label in Cal Sans, 44px arrow circle that fills amber on hover/focus.

### Claim list
Four rows of 40px Maple Ink line icons (2.4 stroke, round caps) beside Cal Sans 20-24px text, separated by hairlines. Icons are inline SVG drawn for each claim.

### Numbered steps
Three steps, each with a 48px amber disc holding the CSS counter in Cal Sans, a Cal Sans title in Frost and a Soft Frost line. Stacked on phones, three across on desktop. Lives on the textured deep navy band.

### Inputs / Fields
- **Style:** Field Mist fill, 2px transparent border, 10px radius, 52px min height (textarea 110px), 16px text, Focus Blue caret. Labels are Cal Sans 18px tied with `for`; "(optional)" is a 14px Soft Slate aside.
- **Hover / Focus:** border turns Focus Blue.
- **Chips:** 48px pills on Field Mist with visually hidden radio inputs; selected is Night Ink with white text; keyboard focus is a 3px Focus Blue outline with offset (visible on the ink fill); hover borders Focus Blue.
- **Error:** border turns Error Red and stays red while focused; a plain-sentence error appears below. Errors clear as soon as the field has text.
- **Submit behaviour:** composes a pre-written text to `CONFIG.SMS` and opens `sms:`; after 900ms a status line offers "Copy the message" and the phone number in case no messages app opened.

### Navigation
A slim paper header, 64px (76px desktop): the logo mark (ink house, amber leaf) and two-line wordmark on the left, the tap-to-call number with a Maple Ink phone icon on the right (hover turns Maple Ink). No menu. The footer is deep navy with texture, holding the name, area, email (its only appearance) and Facebook as 44px links that turn amber on hover.

### Floating text circle (signature)
One 60px amber circle with a Night Ink chat icon, bottom right inside safe-area insets, with the float lift shadow. It opens `sms:` with a pre-filled message, slides up (`translateY(120px)` to rest, .35s `cubic-bezier(.2,.8,.2,1)`) once the hero is 85% scrolled away, and slides out while the quote form is on screen; when hidden it is `tabIndex=-1` and `aria-hidden`. `CONFIG.FLOAT=false` removes it; `CONFIG.TEXTS=false` turns it into a call link and removes the hero's Text us button.

### Motion
- **Hero H1 bounce-in (deliberate):** JS splits the H1 into letters inside nowrap word spans (keeping the `.accent` span); each letter goes from `opacity:0; translateX(50px)` to rest over 1s `cubic-bezier(.34,1.56,.64,1)`, 20ms apart. It waits up to 600ms for Cal Sans, uses an `aria-label` while split, and restores the plain H1 on the last `animationend`. Skipped without JS and under reduced motion.
- **Fade-up:** `.rise` elements that start below the first screen get `.below` (opacity 0, 12px down) and rise over .4s ease-out as they enter. Everything is visible at rest, without JS and under reduced motion.
- **State transitions:** .15-.2s colour and border changes; .12s press scale.

## Do's and Don'ts

### Do:
- **Do** keep amber a fill and use Maple Ink whenever the accent must be text or a line icon on paper.
- **Do** alternate full-bleed bands (paper, navy, paper, deep navy with texture) so every section change is obvious.
- **Do** keep the line texture at `rgba(255,255,255,.035)` or fainter and only on the hero, deep navy band and footer.
- **Do** set every heading, button, label and phone number in Cal Sans 400, and running text in the system stack at 16px / 1.7.
- **Do** keep eyebrow pills quiet (14px, amber dot, tint fill) and use them above the hero H1 and only a few section heads.
- **Do** keep tap targets at 44px or more and inputs at 16px or larger.
- **Do** put behaviour switches and contact details in `CONFIG`, and keep every motion with a reduced-motion and no-JS fallback that shows content at rest.
- **Do** label generated imagery as service illustrations and keep its provenance JSON beside each file.

### Don't:
- **Don't** put white text on amber or amber text on paper.
- **Don't** add shadows to cards, buttons or the header; the floating circle is the only lifted element.
- **Don't** give eyebrows an arrow, hover state, shadow or full amber fill, or mark them up as headings.
- **Don't** animate any heading other than the hero H1 letter by letter.
- **Don't** replace the floating circle with a bottom bar, or show it while the quote form is in view.
- **Don't** add a Call button to the hero; the header number covers calling.
- **Don't** present the generated service photos as PL Siding and Eaves jobs, or add captions, reviews, prices or credentials the client hasn't given.
- **Don't** fill fields with Cool Paper on the white card; fields use Field Mist.
