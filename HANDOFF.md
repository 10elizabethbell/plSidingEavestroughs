# PL Siding and Eaves — handoff at ~60%

**Live:** https://10elizabethbell.github.io/plSidingEavestroughs/ · **Repo:** https://github.com/10elizabethbell/plSidingEavestroughs · **Built:** 2026-10-21 from Muse brief (run 2026-10-21, found in "Essex County Contractor Referrals")

On the Call Sheet: yes (`site` set; the prospect wasn't on the sheet, so the script added a minimal entry `plSidingEavestroughs`).

## Check first
- **Fall special end date.** The page shows "Save $50 on fall service packages" (hero eyebrow + card) and hides both itself after `CONFIG.PROMO_END = '2026-11-30'`. That date is a guess: the flyer OCR only says "Offer [expires] 30th", so it could be **Oct 30**. Confirm with the owner, or set it to `2026-10-30` to be safe. After it ends the hero eyebrow reverts to "Proudly Canadian".
- **Texts.** If 519-996-1924 doesn't take texts, set `CONFIG.TEXTS = false`: the hero's "Text us" disappears and the floating circle calls instead. The quote form still opens a text, so it would also need rewording or replacing.

## What's built
- One page, calm band style: paper header (maple-and-house mark traced from their logo, "PL Siding / and Eaves", tap-to-call (519) 996-1924 top right) → plain textured navy hero ("Save $50 on fall service" eyebrow, **Get your Windsor home ready for winter.**, promise, Get a quote + Text us) → Fall cleaning (the $50 fall special card + four things a cleaning includes) → navy services band (four 4:5 photo cards: eavestrough cleaning, gutter guards, seamless eavestroughs, siding repair; each pre-selects its job in the form) + "See our work on Facebook" → How it works (3 steps, deep navy) → quote form → navy close ("Proudly Canadian.", area, big phone number) → footer (name, area, email, Facebook; the phone number was left out of the footer because the close band directly above it shows it, and a number may appear only once per screen).
- Palette: the logo is black and white, so black became navy (#1d3b60 / deep #10223a) and the one accent is fall-maple amber (#f2a33a, text on it navy; #8a4a00 when amber is text on paper, 6.3:1).
- Motion: hero H1 letter bounce-in, `.rise` fade-up, floating text circle (`CONFIG.FLOAT`). All off under reduced motion; everything shows without JS.
- Contact: the form composes a text to (519) 996-1924 (`CONFIG.SMS`) that starts "I found your website" so form leads can claim the special. Under the button: "Rather call? (519) 996-1924"; if Messages doesn't open, a "Copy the message" fallback appears. Email only in the footer.
- Card images ship at 400w and 800w (`srcset`); the bounce-in waits up to 600ms for Cal Sans so letters don't reflow mid-animation.
- Favicon, iPhone icon and og image (1200x630) from the traced logo mark.

## Assumptions I made
- **Name:** "PL Siding and Eaves" (what the logo and flyer say) everywhere visible; "PL Siding Eavestroughs" (the Facebook page name) isn't used on the page. Ask which they prefer.
- **"We", not "I":** no owner name and they advertise residential and commercial, so I wrote as a crew.
- **Colours:** inferred from the black logo; amber picked for fall maple leaves (gutter season) and because the house style needs a warm fill accent with navy text. Canadian red was the other option but fails contrast as a fill with navy text.
- **The phone takes texts:** unknown in the brief. The hero "Text us", the floating circle and the form all open a text; the number in the header and the close is tap-to-call. If they don't text, switch those to call.
- **How it works:** the three steps ("Text or call us", "Get your price", "We do the job and clean up") are inferred from a normal quote flow, not stated by them.
- **"Eavestroughs inspected":** the flyer OCR was garbled ("structural inspection of [gutter joints]"); I kept it general.
- **Fall special:** "Save $50 on fall service packages" is from Muse's OCR of their flyer (not re-verified: I couldn't fetch the flyer). The card says "Ask about it when you text or call" rather than inventing a way to claim it. No end date is shown; it auto-hides after `CONFIG.PROMO_END`.

## Placeholders and gaps
- **No real job photos.** The four service-card photos are **generated** (see table). They're labelled by service only and never claim to be PL's jobs, but swap in real photos as soon as the owner sends any.
- The flyer image itself couldn't be fetched: the group post's image is their logo, not the flyer. Nothing on the page depends on unverified flyer text except the special and the service list.
- Hero is the plain textured navy band because there are no client photos to put behind it.
- No hours, owner name, years, licence/insurance, reviews or prices: none shown.

| Image | Where | Source |
|---|---|---|
| img/cleaning.webp | Eavestrough cleaning card | Generated 2026-10-21 with gpt-image-1 (`genimg`): iPhone-style photo looking into a white eavestrough half cleared of wet maple leaves |
| img/guard.webp | Gutter guards card | Generated 2026-10-21 with gpt-image-1: dark brown eavestrough with micro-mesh guard, maple leaves on top, low afternoon sun |
| img/eaves.webp | Seamless eavestroughs card | Generated 2026-10-21 with gpt-image-1: white seamless eavestrough and downspout on a red-brown brick bungalow, fall leaves on lawn |
| img/siding.webp | Siding repair card | Generated 2026-10-21 with gpt-image-1: side wall of a two-storey house in pale grey vinyl siding |
| favicon.svg, apple-touch-icon.png, og.png | icons, link preview | Logo mark hand-traced from their Facebook logo (1818px og:image) |

Full prompts are in `~/.local/share/genimg/log.jsonl` and each image's `.json` sidecar.

## Questions for the owner
1. Can customers text 519-996-1924?
2. "PL Siding and Eaves" or "PL Siding Eavestroughs" on the site?
3. When does the fall $50 special end, and what's in a "fall service package"?
4. Photos of real jobs (before/after eavestroughs especially) to replace the generated ones.
5. Your first name, and are you insured? (Both build trust; only if true.)
6. Hours, and which towns you go to most (Tecumseh, LaSalle, Amherstburg, Lakeshore...)?
7. Do you do soffit and fascia too? (Common with eavestroughs; not on the flyer, so not on the site.)

## Ideas not built (yours to pick)
- **Signature world, runner-up:** leaves that drift down across the hero and pile in a gutter line along its bottom edge; drag a finger along it to scoop them out (the job, played on the page). Other worlds considered: rain running off a roof edge into a clean downspout; snow settling on a clean eave; siding panels clicking into place; maple leaves turning colour as you scroll.
- A before/after slider as soon as the owner sends a pair.
- A seasonal swap: fall cleaning section → spring cleaning / "winter-proof your eaves" copy with a `CONFIG.SEASON` switch.
- Commercial section (plazas, rentals) if commercial work is a real share of their business.
- Impeccable conflicts (kept on purpose, Ellie's calm-style choices): its detector flags the repeating-gradient band texture, and its craft floor bans eyebrow pills. Both stay.
- Impeccable sweep (16 modes) and finish review: applied the offer-on-first-screen eyebrow, auto-expiry, TEXTS switch, call fallback, copy-message fallback, website mention in the text, tablet 2-column cards, srcset, font-gated bounce-in, card aria-labels, no-JS floating circle hidden, type sizes consolidated, one eyebrow reworded ("Windsor and Essex County"), the cleanup icon redrawn as a rake, the footer phone removed, two-tone logo in the header.
- Not applied, on purpose: reviewers asked for trust signals (reviews, years, licence, owner name), which would be invented, and a hero photo, but there are no client photos. They also flagged as anti-patterns the eyebrow pills, the bounce/overshoot easing, the band texture (suppressed in `.impeccable/config.json`, scoped to index.html) and the fade-up on most blocks; all are calm-style choices. Detector still reports "flat type hierarchy": it only counts fixed px sizes (11–20px); headings are fluid clamp() sizes from 30 to 80px.
- Desktop: the left column of the quote section is fairly empty under its heading; the right half of the hero holds only the faint mark. Phone is unaffected.

## Not verified
- Real-device touch, and the real SMS handoff on iOS and Android (tested in headless Chromium and WebKit: the composed text decodes correctly; the `sms:` app opening isn't testable headlessly).
- Inside Facebook's in-app browser.
- Frame rate of the bounce-in on old phones.
- Landscape phones (844×390): the hero buttons fall just below the first screen.
- Form fields on the white card are #e6ecf5 (about 1.2:1 against white, below WCAG 1.4.11's 3:1 for field boundaries); the house style accepts this because every field has a visible label. A 1px border would fix it if Ellie wants.
