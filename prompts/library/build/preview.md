# Step 2 - preview.html in the chat (only when asked)

steps.md normally answers step 2 with a link to the finished preview. Use
this file only when I asked for the file itself here in the chat.

Links written BASE/<path> are files in this repo. BASE is the one my prompt gave; if it gave none, BASE is where you got this file: the URL up to and including the branch name, or the local repo folder.

The preview for every theme is already built. Fetch ONLY the one file
for my theme below and give it back to me as preview.html, exactly as
it is - same CSS, same markup, same sample posts, same image URLs and
the same base64 "data:image" thumbnails, character for character. Do
not redesign it, restyle it or rewrite it from the theme values, and do
not fetch anything else (no themes JSON, no sample posts, no llms.txt,
no guide). Run no checks, audits or scripts.

My theme ("skip" or anything that is not a number or name = 1):
1. Modern Card        BASE/guides/previews/modern-card.html
2. Classic Card       BASE/guides/previews/classic-card.html
3. Social Card        BASE/guides/previews/social-card.html
4. Square Photo       BASE/guides/previews/square-photo.html
5. Classic Photo      BASE/guides/previews/classic-photo.html
6. Collage            BASE/guides/previews/collage.html
7. Horizontal Columns BASE/guides/previews/horizontal-columns.html
8. Horizontal Slider  BASE/guides/previews/horizontal-slider.html
9. Gallery Slider     BASE/guides/previews/gallery-slider.html
10. Highlight Slider  BASE/guides/previews/highlight-slider.html
11. Reels             BASE/guides/previews/reels.html
12. Vivid             BASE/guides/previews/vivid.html
13. Widget Theme      BASE/guides/previews/widget-theme.html
14. Review Carousel   BASE/guides/previews/review-carousel.html
15. Review List       BASE/guides/previews/review-list.html
16. Review Box        BASE/guides/previews/review-box.html

Cannot open it? Say so in one line and stop - do not build one from
memory.

The file already follows every rule: static, calls no API, "Social
Widget" title, the first image of each post (never a video), escaped
text, rel="noopener noreferrer" links, and a blurred base64 thumbnail
behind each image where a chat pane blocks outside images (the live API
sends no thumbnail - live cards fall back to the plain tile). The later stack files reuse its markup and
CSS as is.

Reply with: the file as preview.html, then one line - images show
blurred inside this chat's preview pane; save preview.html and
double-click it to open it in a browser, where the full images load. Then exactly
these two questions, short:
1. Want to change anything in this preview? (colours, font, columns,
   card style, hide author/date...) - or say "no".
2. Which stack should I build it in? PHP / Node.js / React / Simple HTML
