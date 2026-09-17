# Motion Notes website

Twelve interactive, original motion studies with practical editing directions. This is the same Canvas library demonstrated in the tutorial, packaged as a standalone static site. No installation, API key, paid account or generation credits are needed to browse it.

## Use the library

Search or filter the techniques, open a card, scrub the six-second preview, then copy its prompt. Replace the example wording with your own assets and measured timestamps. The global pause button stops the previews; reduced-motion preferences start them paused. The previews illustrate a technique, not a promised video-model output.

Use the site's **Start here** link for the complete Video Analyzer skill and the Codex, OpenArt MCP, Remotion and Blender setup guides. The **Video Analyzer** download is a short starter prompt that points to that complete kit.

## Hosting

Serve this directory as a static site. On GitHub Pages choose `main` and `/docs` as the source. Every local asset URL is relative, so both a project URL such as `/astra-video-workflow/` and a custom domain work. No build command or package installation is required. `.nojekyll` disables Jekyll processing.

For a local preview, serve the repository from any static HTTP server and open `/docs/`. Opening `index.html` directly also works; clipboard availability depends on the browser. The copy button includes a fallback.

## Files

- `index.html`, `style.css`: responsive, keyboard-accessible page.
- `app.js`: Canvas studies, search/filter, copy/download and playback controls.
- `library.js`: the twelve names, directions and checks.
- `motion-notes-12-prompts.txt`: all twelve directions in plain text.
- `video-analyzer.txt`: the workflow starter prompt.

The demo graphics are original code studies. No source-video frames, private portraits, voice recordings, music, credentials or third-party video are bundled. The mock phone interface is invented. Links to tools are provided in the workflow kit; this website is an independent learning resource.
