# Case Study Notes: DBD Survival Guide & Killer Grimoire

Raw notes to turn into case-study.html. Not a page itself.

## Goal
- Fan-made guide for Dead By Daylight: a Survivor side and a Killer side.
- Look and feel borrowed from the game's HUD (orbs, pill nav, side colors).

## Design decisions (and why)
- **Landing page = "Choose Your Side."** It's neutral, so its colors and icons mix both sides.
  The teacher OK'd using it as index.html.
- **Color per side.** Neutral dark on the landing page, dark blue for Survivor, dark red for Killer.
  CSS variables are swapped by a class on `<body>`.
- **Nav ordered by JOB, not by side.** Slot 1 = this side's home, 2 = advanced/killer select,
  3 = the other side, 4 = back to Choose Your Side. A user learns the slots once, and they work on
  both sides.
- **Smaller icon nav** instead of a big text menu (teacher OK'd).
- **The Killer Select button only opens a menu; it doesn't link anywhere.**
  - At first, the machete linked to the Trapper page AND had a flyout. That was redundant.
  - I switched it to `<details>`/`<summary>`: click or tap opens the killer list, with no JavaScript.
  - It also solves mobile, because a phone has no hover.
- **Orb sub-nav** jumps to sections on the same page (`href="#id"`). Text labels sit under the
  orbs, so the orb images use `alt=""`.
- **Collapsible sections** (`<details>`) keep long pages short. Readers open only what they need.
- **Looping videos instead of GIFs**
  (`autoplay muted loop playsinline`). The files are smaller and the quality is better.
- **Unfinished pages look locked.** The link has no href, the image has a baked-in lock, and the alt
  text says "(Coming Soon)". It's honest about what isn't built, instead of linking to empty pages.
- **Alt text = what the image DOES.** Nav icon = where it goes. Hero = describe the character.
  Icon next to visible text = `alt=""`.
- **Font licensing:** Cocogoose is used in images only. Its license doesn't allow sharing the font
  file, so the font file never goes in the repo.
- **Hero character** sits in a fixed sidebar, pinned to the bottom, with text layered above it
  (z-index).
- **Matched the landing buttons by letter height, not width.** "Survivor" is a much longer word
  than "Killer," so making the images the same width looked wrong. Each button gets its own size,
  worked out from the image's real shape, so the letters look the same height.
- **Visual hierarchy on phones:** the header logo should always look bigger than the nav buttons.
  The buttons use smaller caps on phones and their full size only on desktop.

## Problems I hit (and what I learned)
- Videos looked broken. They were hidden inside closed `<details>`, and the VS Code preview can't
  play mp4. Test in a real browser.
- The hero image pushed the nav down. Fix: `position: absolute` takes it out of the flow.
- The hero covered the text. z-index only works on positioned elements, so I added
  `position: relative` to the content.
- An unclosed `/*` comment swallowed half the CSS. One missing `*/` breaks everything after it.
- A media query nested inside another one, plus a missing `}`, made rules silently stop working.
- A typo in an id (`stealthn`) broke the orb jump link. The id and the href must match exactly.
- `<p>` can't contain headings or lists. I used `<div>` for each subtopic instead.
- em compounds. Shrinking the font on the footer `ul` also shrank the em-sized icons inside it.
  I moved the text styles onto the `<a>` instead.
- Two rules with the same selector: the later one wins. I kept editing the one that was being
  overridden.
- A custom `max-width` on the header image replaced the global `max-width: 100%`, so it stopped
  shrinking on phones. Fix: `width: 100%` + `max-width: [cap]` = fluid but capped.
- A class put on the `<li>` instead of the `<img>` made the box wider, not the image.
- The landing page had no sidebar but still got the sidebar's left margin. I added a
  `.landing` body class to cancel it.
- Background `cover` vs `contain` vs exact size: I wanted the splash to fade into the dark,
  not fill the screen.
- The footer labels sat too far below their icons. The CSS was fine; the PNGs had see-through
  empty space at the bottom. Fix: a small negative `margin-bottom` (in em) on the icon, so the
  text overlaps that empty space. (Cropping the PNGs would be the cleaner fix.)
- Setting BOTH `width` and `height` on the killer button stretched it about 13% wider than its
  real shape. It was subtle, but it would have squashed on phones once the width became a %.
  Fix: set only the width and let `height: auto` keep the shape.
- `width: 70%` + `max-width: 17em` still didn't shrink the buttons on phones. The % only kicks in
  once the screen is narrower than max-width ÷ % (17 ÷ 0.7 ≈ 24em ≈ 390px), so most phones still
  hit the cap. Fix (mobile-first): a smaller max-width outside the media query for phones, and
  the full max-width inside the 64em query for desktop. Inside a query, write only what changes.
## If I had more time / next time
- **Reusable lock overlay** (CSS) instead of baking a lock into every image. Then I could lock any
  unfinished section on the fly.
- CSS `drop-shadow` instead of shadows baked into the images.
- A real Killer Select hub page once there are many killers.
- Nested page folders (killer/, survivor/) once the site has 15+ pages.
- Hand-styled killer buttons (portrait + button background in CSS) to replace the temporary images.
- Give the killer flyout its own matching pill background. Right now it slightly overlaps the main
  pill so the two feel connected.
- A full mobile pass: smaller nav, and the hero as a dimmed background.

## Process notes
- Started with Figma mockups at a 1440 frame; exported images at 2x (2160) for sharpness.
- Built the HTML for all pages first, then CSS mobile-first, with desktop at 64em and large
  screens at 120em.
- Used em units throughout so everything scales with the font size.
