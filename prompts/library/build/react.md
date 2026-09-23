# Step 4 - React: Vite app + a small Express server

Links written BASE/<path> are files in this repo. BASE is the one my prompt gave; if it gave none, BASE is where you got this file: the URL up to and including the branch name, or the local repo folder.

Fetch RAW first and follow it - the shared rules, cache and README:
BASE/prompts/library/build/common.md
Already fetched it earlier in this chat? Do not fetch it again. Fetch
nothing else.

The token must never reach the browser, so React never calls Taggbox
itself. Deliver:
- server.js - Node.js 18+ with Express. GET /api/posts calls Taggbox
  with the cache (common.md) and returns { posts, paging } as JSON; an
  empty ACCESS_TOKEN returns the sample posts. In production it also
  serves the built app from dist/.
- package.json - react, react-dom, express, dotenv, vite,
  @vitejs/plugin-react, concurrently - nothing more; scripts: "dev"
  (concurrently runs Vite + server, Vite proxying /api to the
  server), "build", "start".
- vite.config.js, and index.html (Vite's entry, loading
  /src/main.jsx).
- src/main.jsx - mounts SocialWidget and imports its CSS.
- src/SocialWidget.jsx - one drop-in component: fetches /api/posts,
  renders the same markup (same .tbx-* classes) as preview.html, with
  a loading state, an empty state and an error message. React escapes
  text itself - never use dangerouslySetInnerHTML; allow only
  http/https links.
- src/social-widget.css - the CSS from preview.html, unchanged.

Exactly these paths, src/ files inside src/:
server.js, package.json, vite.config.js, index.html, src/main.jsx,
src/SocialWidget.jsx, src/social-widget.css - with preview.html,
.env.example and README.md beside them. Nothing else.
