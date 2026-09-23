# Social widget - rules every stack follows

Links written BASE/<path> are files in this repo. BASE is the one my prompt gave; if it gave none, BASE is where you got this file: the URL up to and including the branch name, or the local repo folder.

Shared by the stack steps (php.md, nodejs.md, react.md, html.md) and
the README step. It carries no deliverable of its own.

Read this first - the exact field names are specified there:
BASE/llms.txt
Already read it earlier in this chat? Do not fetch it again. Do NOT
fetch the design spec - the looks are already fixed by preview.html.

What it is: a social widget - a page my own server renders, showing
the live posts from my Taggbox gallery. Every stack renders the SAME
markup with the SAME CSS as the final preview.html from this chat
(including every change I asked for), so a later restyle applies
everywhere. Do not re-pick or change the theme.

Name: it is a Social Widget. Use that name in the page title, the
header, the README and the code comments - never "social wall".

Data: GET https://api.taggbox.com/api/v3/posts?limit=24, header Authorization:
Bearer <token>; token from ACCESS_TOKEN, base URL from API_BASE_URL,
neither in the code. Posts are at body.posts and paging at
body.paging, never the top level, and `status` can be false on an HTTP
200. No "fields" param exists. Leave `sort` alone. Page 2 =
body.paging.next_cursor sent back as `after` verbatim, never a post id.

Sample posts: reuse the ones baked into preview.html. An empty
ACCESS_TOKEN renders them instead of calling the API; a real one
switches to live by itself.

Per post: author.name falling back to author.handle (either can be
null - never print "null"), network.name, content.text, created_at,
source.permalink with rel="noopener noreferrer". The image is the
FIRST media entry of type "image" via cdn_url, NOT media[0], which can
be a video. rating 0-5 marks a review post and is null on social ones
- same card, plus stars. Other missing values are null, never "" or 0.

Non-negotiable: every call runs server-side and the token never
reaches the browser. Escape everything you print; allow only
http/https links.

No tests: do not write or run tests, audits or checks - no
accessibility or contrast scripts, no auth or 401 flow tests, no curl
calls, no test files. Keep preview.html's colours as they are. I run
and check the build myself.

Every file complete - no placeholders, no "rest stays the same", no
truncation - with brief comments through the code.
