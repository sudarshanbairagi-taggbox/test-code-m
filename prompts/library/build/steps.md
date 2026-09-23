# Social widget - the build, step by step

Links written BASE/<path> are files in this repo. BASE is the one my prompt gave; if it gave none, BASE is where you got this file: the URL up to and including the branch name, or the local repo folder.

A short guided build. Each step is ONE reply, then you stop and wait
for my answer. Keep every question short, as a numbered list I can
answer with one number or word. Fetch a step's link only when that
step starts - never fetch ahead.

## Step 1 - pick a theme (this reply, fetch nothing else)

Ask me which theme I want, with this list, and say that "skip" (or
any reply that is not a number or name) uses 1. Modern Card:

Social feeds
1. Modern Card (default)   2. Classic Card   3. Social Card
4. Square Photo            5. Classic Photo  6. Collage
7. Horizontal Columns      8. Horizontal Slider
9. Gallery Slider          10. Highlight Slider
11. Reels                  12. Vivid         13. Widget Theme
Reviews
14. Review Carousel        15. Review List   16. Review Box

Then stop.

## Step 2 - preview.html (after my theme answer)

Fetch RAW and follow:
BASE/prompts/library/build/preview.md

## Step 3 - customise (optional, repeat as often as I ask)

If my answer asks for a change to the preview (colours, font, columns,
card shape, hide author or date, header text, anything), apply it to
preview.html, give me the complete file again, and ask once more:
"Anything else to change, or which stack?" Do not fetch anything for
this step. It ends when I name a stack.

## Step 4 - the files for my stack (once I name one)

Fetch RAW the ONE link for the stack I chose, and follow it:
- PHP:
  BASE/prompts/library/build/php.md
- Node.js:
  BASE/prompts/library/build/nodejs.md
- React:
  BASE/prompts/library/build/react.md
- Simple HTML:
  BASE/prompts/library/build/html.md

Every stack reuses the markup, CSS and theme of the final preview.html,
including every change from step 3.

## Step 5 - README and suggestions (same reply as step 4)

Right after the stack files, in the same reply, fetch RAW and follow:
BASE/prompts/library/build/readme-file.md

If you cannot open a link, say so in one line - do not build from
memory.
