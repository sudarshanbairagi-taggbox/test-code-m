# Step 4 - Simple HTML: index.html + posts.php

Links written BASE/<path> are files in this repo. BASE is the one my prompt gave; if it gave none, BASE is where you got this file: the URL up to and including the branch name, or the local repo folder.

Fetch RAW first and follow it - the shared rules, cache and README:
BASE/prompts/library/build/common.md
Already fetched it earlier in this chat? Do not fetch it again. Fetch
nothing else.

A plain HTML page cannot hold the token - anyone could read it in
View Source - so the live data comes through one tiny server file.
Deliver:
- index.html - the preview.html markup and CSS, plus a short inline
  script (no framework, no build step) that fetches posts.php and
  renders the same cards. Build text with textContent, never
  innerHTML with post data; allow only http/https links. If the fetch
  fails, keep showing the sample posts already in the markup.
- posts.php - ONE PHP 8 file, the only place the token lives: calls
  Taggbox with the cache (common.md) and returns { posts, paging } as
  JSON; an empty ACCESS_TOKEN returns the sample posts.

Say in one line that this runs on any PHP host (cPanel and the like);
for a host without PHP the Node.js stack is the one to pick.
