# Trapper Page CSS Rundown (in order of importance)

All of these rules go OUTSIDE the media queries.

## 1. Section title bars (`<summary>`)
```css
summary {
  background-image: url("../assets/images/____.png"); /* your bar image */
  background-size: 100% 100%;   /* stretch to fill the bar */
  background-repeat: no-repeat;
  padding: 0.5em 1em;           /* room around the h3 */
  cursor: pointer;              /* hand cursor = clickable */
  list-style: none;             /* hide the ▶ on all screens */
}
summary h3 { margin: 0; }       /* stops the bar from being extra tall */
```
WARNING: delete the old `summary { list-style: none; }` that is inside the 64em media query.
The new rule covers it.

## 2. Section bodies
```css
section {
  background-image: url("../assets/images/shared/section-bg.png");
  background-size: 100% 100%;
  margin-bottom: 1em;           /* space between sections */
}
details > div { padding: 1em; } /* keeps text off the edges */
```

## 3. Videos + power images
```css
video {
  width: 100%;       /* fluid on phones */
  max-width: 30em;   /* capped on desktop */
}
```
Same trick for images: `width: 100%` + `max-width: [cap]` = fluid, but capped.

## 4. Name + orb labels
```css
.name { font-size: 1.25em; font-weight: 300; }
.sub-nav a { font-size: 0.75em; font-weight: 300; text-align: center; }
```
NOTE: 0.75em on `.sub-nav a` also shrinks the 3em orbs inside it (em compounding).
Bump `.sub-nav img` to 4em to make up for it.

## If something breaks
1. Check the line above for a missing `;` or `}`.
2. Check for a duplicate selector further down. The later rule wins.
3. Check that every url has `../` at the start (CSS paths start from the css folder).
4. Check that the rule is outside the media query if phones need it too.
