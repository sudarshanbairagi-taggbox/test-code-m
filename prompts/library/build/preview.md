# Step 2 - preview.html (fast)

Links written BASE/<path> are files in this repo. BASE is the one my prompt gave; if it gave none, BASE is where you got this file: the URL up to and including the branch name, or the local repo folder.

Speed matters here: fetch ONLY the two files below - do NOT fetch
llms.txt, the design spec, common.md or any other guide, and run no
checks, audits or scripts. Everything you need is on this page.

1. My theme's values (find it by name; "skip" = Modern Card):
BASE/guides/themes-lite.json
2. The sample posts - social themes use the first, review themes the
second. Bake in 10-12 of them as they are:
BASE/guides/sample-posts-social.json
BASE/guides/sample-posts-reviews.json
Cannot open one? Invent 10 posts in the same shape and say so in one line.

Deliver preview.html: one static file, the sample posts written into
the markup, CSS in one <style> block inside it. It calls NOTHING - no
fetch, no token, no API - so I can double-click it. Title and header
say "Social Widget" (never "social wall"). Name it preview.html, not
index.html. The later stack files reuse this markup and CSS as is.

Theme to CSS (every class .tbx-*, every variable --tbx-*):
- backgroundColor -> page --tbx-bg; cardColor -> --tbx-surface (empty:
  use the page colour); fontColor -> text; authorColor -> author name
  (empty: fontColor).
- css_font / font_varient / fontSize -> font, weight, text size; load
  link_font from Google Fonts behind a system-font fallback.
- roundEdge -> card radius; borderRadius -> image radius; spacing ->
  grid gap; padding -> card padding.
- numberOfColumn -> columns (0 = 4), dropping to 2 on tablet, 1 on phone.
- textAlignment -> text-align; lineTrim -> line-clamp (0 = none);
  postAuthor / postTime 0 -> hide author / date; hideContent 1 -> hide
  the text; aspectImageRatio 0 natural, 100 square, 56.25 16:9.
- A white-on-near-white colour pair: darken it so it reads, and note
  it in a CSS comment. One skin only - no dark mode, no toggle.

Each card: image = the FIRST media entry of type "image" via cdn_url
(not media[0], which can be a video; none = no image); author.name,
else author.handle, else nothing (never print "null"); network.name;
content.text; created_at as a short date; rating 1-5 as stars on
review posts; the card links to source.permalink with
rel="noopener noreferrer". Brief comments in the code.

End the reply with exactly these two questions, short:
1. Want to change anything in this preview? (colours, font, columns,
   card style, hide author/date...) - or say "no".
2. Which stack should I build it in? PHP / Node.js / React / Simple HTML
