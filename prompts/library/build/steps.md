# Social widget - the build, step by step

Links written BASE/<path> are files in this repo. BASE is the one my prompt gave; if it gave none, BASE is where you got this file: the URL up to and including the branch name, or the local repo folder.

A short guided build. Each step is ONE reply, then you stop and wait
for my answer. Keep every question short, as a numbered list I can
answer with one number or word.

Speed matters on every step. Everything is already built - the
previews, the code for every stack, the READMEs - so this file is the
only one you need: fetch nothing else unless a step says so, write no
code unless a step says so, and run no tests, audits, scripts or
checks. No plan, no recap, no "here is what I will do". Write every
link as a full URL: BASE followed by the path.

If you can write files and run commands in my project (Claude Code,
Cursor, Copilot, Codex, Windsurf, Gemini CLI...), do the downloading,
unzipping and saving yourself instead of asking me to.

## Step 1 - pick a theme (fetch nothing)

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

## Step 2 - the preview (fetch nothing, write no code)

Each theme's preview is a finished file. Its name (the "slug") is the
theme name in lower case with dashes: 1 modern-card, 2 classic-card,
3 social-card, 4 square-photo, 5 classic-photo, 6 collage,
7 horizontal-columns, 8 horizontal-slider, 9 gallery-slider,
10 highlight-slider, 11 reels, 12 vivid, 13 widget-theme,
14 review-carousel, 15 review-list, 16 review-box.

Reply with only this:
- "Your preview (<theme name>):" and the link
  BASE/guides/previews/<slug>.html
- one line: open the link, save the page as preview.html
  (right-click > Save as, or Ctrl/Cmd+S), then double-click the file -
  it opens in the browser with sample posts, no token needed.
- these two questions:
  1. Want to change anything? (colours, font, columns, corners,
     spacing...) - or say "no".
  2. Which stack should I build it in? PHP / Node.js / React / Simple HTML

If I say I cannot open or save the link and want the file here, fetch
BASE/prompts/library/build/preview.md and follow it instead.

## Step 3 - customise (optional, repeat as often as I ask)

Do not rewrite the preview. Every look is set by CSS variables, so a
change is a few lines in a file called custom.css. The variables:
--tbx-bg (page), --tbx-surface (card), --tbx-text, --tbx-author,
--tbx-font, --tbx-weight, --tbx-size (text size), --tbx-radius (card
corners), --tbx-img-radius (image corners), --tbx-gap (space between
cards), --tbx-pad (space inside a card), --tbx-cols (columns, or cards
per view on sliders), --tbx-align, --tbx-lines (text lines shown).
Class names, for anything else: .tbx-card, .tbx-media, .tbx-head,
.tbx-author, .tbx-date, .tbx-net, .tbx-text, .tbx-stars, .tbx-header.

Reply with custom.css in one short code block - only what changes,
mostly one `:root { ... }` block, adding to any custom.css from
earlier in this chat - then one line: to see it now, paste it just
before </style> in preview.html and reopen it; keep it as custom.css
for the build. Then ask: "Anything else to change, or which stack?"
Fetch nothing. It ends when I name a stack.

## Step 4 - the code for my stack (fetch nothing, write no code)

The code for every stack is ready in one zip, with all 16 themes, the
sample posts and a README inside:
- PHP:         BASE/templates/dist/social-widget-php.zip
- Node.js:     BASE/templates/dist/social-widget-nodejs.zip
- React:       BASE/templates/dist/social-widget-react.zip
- Simple HTML: BASE/templates/dist/social-widget-html.zip

Reply with only this, short:
1. The download link for my stack; unzip it.
2. In that folder, copy .env.example to .env and set
   WIDGET_THEME=<slug> (my theme from step 2). ACCESS_TOKEN can stay
   empty for now - it shows the sample posts.
3. Only if step 3 made a custom.css: save it in the same folder.
4. How to start it, one line:
   - PHP / Simple HTML: `php -S localhost:8080`, open
     http://localhost:8080 - or upload the folder to any PHP host.
   - Node.js: `npm install`, then `npm start`, open
     http://localhost:3000
   - React: `npm install`, then `npm run dev`, open
     http://localhost:5173
5. "README.md in the zip has every step, for someone who has never
   used a terminal."
Then a short "What you can add next" list - 4 to 6 one-line ideas I
could send back as my next request, picked from: a network filter bar,
a "Load more" / next-page link, auto-refresh, a lightbox for images and
videos, shopping tags on posts, dropping the widget into a section of
my existing site, Redis or another cache.

End by asking for my access token - Taggbox dashboard, the gallery's
card, its three-dot menu, "Access Token" - and offer to put it in the
.env for me.

If you cannot open a link, say so in one line - do not build from
memory.
