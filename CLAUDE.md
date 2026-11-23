# How to help me

## How I work
- I do the work. You guide me. Don't write code or edit my files
  unless I explicitly ask. Reading files to diagnose problems is fine.
- One step at a time, then stop so I can check it works.
- I have ADHD: keep it visual and scannable. Short numbered steps,
  small tables, checklists. No walls of text.
- Explain WHY something broke, and what each property does.
  Small examples are fine when I'm confused.
- If something I send looks cut off, ask before guessing.
- Remind me to check the line above for a missing ; or }.
- Tell me honestly when I'm wrong. I don't want an echo chamber.
- When I ask what I broke: hint first, don't give the answer.
  Point me to the file/section and ask a guiding question so I
  can find it myself. If my guess is close, tell me which part is
  right and which part is off, then explain why. Give the full fix
  only if I'm still stuck or ask for it. (Not every time; skip it
  for tiny typos or when I'm clearly in a hurry.)

## Class rules (DESN 368)
- No full systems we haven't covered (e.g. grid, JavaScript).
  Single new properties are OK. I'll tell you when something is new.
- Remind me to use em (and unitless line-height) so sizes stay
  proportional, until I do it on my own.
- Use relative paths only (assets/images/...), never C:\ paths.

## Ending a session
When I say "I'm done for now", "stopping here", "calling it", or anything
similar:
1. Update the "Where I left off" section at the bottom of this file
   (you have permission to edit THIS file for that): what I finished,
   what's next, and anything that's half-done or broken.
2. Remind me to commit and push.

## Starting a session
When I say "starting up" or "back to work":
1. Remind me to pull first.
2. Read "Where I left off" and tell me what's next.

## Where I left off
**Session 2 (2026-11-22 → 23, overnight)**

Finished:
- HTML DONE for index, survivor-home, killer-home, killer-trapper
  (all checked: tags nest correctly, every image/video path exists).
- Footer on every page: Case Study + Portfolio links, visible text
  labels, alt="".
- Sidebar: <div class="sidebar"> holds hero <img class="hero"> +
  <nav>. Killer pages have the nested <ul class="killer-select">
  flyout (Trapper link, Mastermind locked, no href).
- Trapper page: 6 sections, <div> per <h4> subtopic, 6 looping
  videos (autoplay muted loop playsinline).
- CSS: variables + per-side colors via body class (.survivor /
  .killer set --bg and --nav-bg); Roboto Condensed, -0.05em
  spacing; orbs in a flex row; desktop media query (64em): fixed
  sidebar, hero 100vh (max 30vw), nav pill centered vertically
  (top 50% + translateY(-50%)), content z-index above hero;
  120em query bumps body to 1.75em.

NOT committed yet: style.css + 3 HTML files + 2 new images in
shared/nav/ (trapper-select, wesker-select; duplicates of
killer/nav/ ones? delete one set).

Next (in order):
1. Commit + push first.
2. Quick fixes: alt="Wesker" → "Mastermind (coming soon)" on
   killer-home + killer-trapper (line 58). Merge the two
   `.sidebar .hero` rules in the media query.
3. Section bars: style <summary> + section backgrounds
   (background-image in CSS, remember ../ paths).
4. Flyout: position .killer-select beside the machete, show on
   :hover / :focus-within (desktop only; hidden on phones).
5. Mobile pass: nav icons are huge on phones (no phone CSS for
   the sidebar yet); hero = fixed dimmed background behind content.
6. Orb labels: center under orbs, small + light (0.75em, 300).
7. case-study.html. Check live on Pages.

Decisions / notes:
- Cocogoose font: images ONLY (license forbids sharing the font
  file). Never put the font file in the repo.
- Nav slots are ordered by JOB, not by side: 1 = this side's home,
  2 = advanced/killer select, 3 = other side, 4 = exit to index.
  (Survivor slot 3 → killer-home.html TEMP; later
  survivor-killer-counter.html.)
- Unfinished pages: no href + baked-in "-locked" image + "(coming
  soon)" in alt. Don't make a page file until it has content.
- Flat file names with prefixes (killer-*, survivor-*), no page
  subfolders yet.
- Images: content = HTML <img> with alt; decoration = CSS
  background. Icon next to visible text = alt="".
- VS Code preview can't play mp4: test videos in a real browser.
- Teacher OK'd: landing page as index.html, smaller icon nav.
- <pre><code> requirement is probably a leftover; confirm with
  teacher or use it for stats.
- Still to confirm with teacher: <details>/<summary> and <video>.
- Case study ideas: nav ordered by function; CSS drop-shadow
  instead of baked shadows; killer select hub page; nested page
  folders once there are 15+ pages.

Cheat sheet (user asked me to keep this; give a rundown at the
end of each session and add new items):
- Ctrl+H: find & replace (one or all)
- Shift+Alt+F: format file / fix indents
- Ctrl+, : settings
- Esc: dismiss a suggestion
- Type a tag, then Enter right away: cursor lands between open
  and close tags