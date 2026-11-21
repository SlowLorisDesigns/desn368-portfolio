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
**Session 1 (2026-11-21)**

Finished:
- Tribute + Handmade: CSS image paths fixed (../), Handmade page
  links fixed, favicon/badge leading "/" removed. Live on Pages.
- Homepage: #first-quarter link, project links now relative.
- Field Guide set up: assets/images/{shared,survivor,killer,icons},
  reset.css linked before style.css.
- Field Guide landing page (index.html) HTML is DONE: header with
  h1 title image, nav with Survivor/Killer image links, footer
  with Behaviour + Zetafonts credits.

Next:
- Survivor side HTML (survivor-home.html), HTML only, no CSS yet.
  Plan: sticky sidebar with 2 navs (main category icons + sub nav
  icons linking to #section ids), divider between them.
  Sections use <section id> > <details> > <summary><h2>.
- Then killer-home.html, Trapper page, case-study.html.

Decisions / notes:
- Cocogoose font: images ONLY (license forbids sharing the font
  file). Never put the font file in the repo.
- Nav icon order must be the same on every page (mockups differ
  by mistake).
- Teacher OK'd: landing page as index.html, smaller icon nav.
- <pre><code> requirement is probably a leftover; confirm with
  teacher or use it for stats.
- Still to confirm with teacher: <details>/<summary> and <video>.
- Footer still needs the two buttons (View Portfolio, Read Case
  Study) once images are picked.