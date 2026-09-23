# Social widget - the build, step by step

Links written BASE/<path> are files in this repo. BASE is the one my prompt gave; if it gave none, BASE is where you got this file: the URL up to and including the branch name, or the local repo folder.

A short guided build. Each step is ONE reply, then you stop and wait
for my answer. Keep every question short, as a numbered list I can
answer with one number or word.

Speed matters on every step. Everything is already built - the
previews, the code for every stack, the READMEs - so besides this file
you fetch only what step 2 and step 4 name. Write no new code, and run no tests, audits, scripts or
checks. No plan, no recap, no "here is what I will do". Write every
link as a full URL: BASE followed by the path.

If you can write files in my project (Claude Code, Cursor, Copilot,
Codex, Windsurf, Gemini CLI...), save the files yourself instead of
showing them to me - same content, same paths.

## Step 1 - pick a theme (fetch nothing)

Show me this table. After the table, one line with the theme
gallery - every picture large, click one to see its preview: <host>/guides/theme-gallery.html, where
<host> is BASE with "https://raw.githubusercontent.com/" swapped for
"https://raw.githack.com/" (raw GitHub would show the page as code; if
BASE is a local folder, give the file path). Then ask which one I
want - "skip", or any reply that is not a number or name, means
3. Modern Card.

| # | Theme | For |
|---|---|---|
| 1 | Classic Card | social |
| 2 | Social Card | social |
| 3 | Modern Card | social |
| 4 | Classic Photo | social |
| 5 | Square Photo | social |
| 6 | Collage | social |
| 7 | Vivid | social |
| 8 | Horizontal Slider | social |
| 9 | Horizontal Columns | social |
| 10 | Slider | social |
| 11 | Reels | social |
| 12 | Story Theme | social |
| 13 | Single Post | social |
| 14 | Widget Theme | social |
| 15 | Review Box | reviews |
| 16 | Review Carousel | reviews |
| 17 | Review List | reviews |
| 18 | Rating Badge | reviews |
| 19 | Badge | reviews |

Then stop.

## Step 2 - the preview (fetch ONE file, write no code)

Each theme's preview is a finished file. Its name (the "slug") is the
theme name in lower case with dashes: 1 classic-card, 2 social-card, 3 modern-card, 4 classic-photo, 5 square-photo, 6 collage, 7 vivid, 8 horizontal-slider, 9 horizontal-columns, 10 slider, 11 reels, 12 story-theme, 13 single-post, 14 widget-theme, 15 review-box, 16 review-carousel, 17 review-list, 18 rating-badge, 19 badge.

Fetch RAW BASE/guides/previews/<slug>.html and give it back to me as
preview.html, exactly as it is, character for character - same CSS,
markup, sample posts, image URLs and base64 "data:image" thumbnails -
so this chat shows it (as an artifact, canvas or preview pane). Do not
redesign, shorten or rewrite it, and fetch nothing else.

Then reply with only this:
- one line: images show blurred inside this chat's preview; the full
  images load in a browser - open <link> or save preview.html and
  double-click it. Build <link> from BASE with
  "https://raw.githubusercontent.com/" swapped for
  "https://raw.githack.com/" (the rest of the path, branch included,
  stays the same) + /guides/previews/<slug>.html; raw GitHub would
  show it as code. If BASE is a local folder, give the file path.
- these two questions:
  1. Want to change anything? (colours, font, columns, corners,
     spacing...) - or say "no".
  2. Which stack should I build it in? PHP / Node.js / React / Simple HTML

## Step 3 - customise (optional, repeat as often as I ask)

Do not redesign the preview. Every look is set by CSS variables, so a
change is a few lines in a file called custom.css. The variables:
--tbx-bg (page), --tbx-surface (card), --tbx-text, --tbx-author,
--tbx-font, --tbx-weight, --tbx-size (text size), --tbx-radius (card
corners), --tbx-img-radius (image corners), --tbx-gap (space between
cards), --tbx-pad (space inside a card), --tbx-cols (columns, or cards
per view on sliders), --tbx-align, --tbx-lines (text lines shown).
Class names, for anything else: .tbx-card, .tbx-media, .tbx-head,
.tbx-author, .tbx-date, .tbx-net, .tbx-text, .tbx-stars, .tbx-header.

Write custom.css - only what changes, mostly one `:root { ... }` block,
adding to any custom.css from earlier in this chat. Then reply with:
1. preview.html again, so this chat shows the change: the step 2 file
   exactly as it was, with the whole custom.css pasted in just before
   its </style>, under a /* custom.css */ comment. Change nothing else
   in the file.
2. custom.css in one short code block, with one line: keep it - it
   goes into the build in step 4.
Then ask: "Anything else to change, or which stack?"
Fetch nothing. It ends when I name a stack.

## Step 4 - the files for my stack (fetch 3 files, write no new code)

The code for every stack is finished. Fetch RAW these three
- nothing else:
1. My stack's files, all in one text file - each file starts with a
   line "===== FILE: <path> =====":
   - PHP:         BASE/templates/dist/social-widget-php.txt
   - Node.js:     BASE/templates/dist/social-widget-nodejs.txt
   - React:       BASE/templates/dist/social-widget-react.txt
   - Simple HTML: BASE/templates/dist/social-widget-html.txt
2. BASE/templates/themes/<slug>.css
3. BASE/templates/themes/<slug>.json

Hand every file over here in the chat, each as its own code block
headed with its path, ready to save - exactly as fetched, character for
character. Do not rewrite, shorten, "improve" or merge any of them, and
write no "rest stays the same". The files, in this order:
- every file from the stack text file, except .env.example and
  except the sample file I do not need: samples/social.json for a
  social theme, samples/reviews.json for a review theme (15-19) - give
  only that one;
- themes/<slug>.css and themes/<slug>.json (keep the themes/ folder);
- custom.css, only if step 3 made one - the final version, with every
  change from step 3 (the code adds it after the theme, so my changes
  show);
- .env - the .env.example text with WIDGET_THEME=<slug> filled in and
  ACCESS_TOKEN left empty (it shows the sample posts until I add it).

After the files, short:
- one line: save them all in one folder, keeping the paths (themes/,
  samples/, and src/ for React).
- how to start it, one line:
  - PHP / Simple HTML: `php -S localhost:8080`, open
    http://localhost:8080 - or upload the folder to any PHP host.
  - Node.js: `npm install`, then `npm start`, open http://localhost:3000
  - React: `npm install`, then `npm run dev`, open http://localhost:5173
- "README.md has every step, for someone who has never used a terminal."
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
