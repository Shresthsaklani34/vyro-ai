# VYRO AI — Installable PWA starter

This package turns the VYRO AI browser editor into an installable Progressive Web App (PWA).

## Included
- Responsive editor interface
- PWA web app manifest
- App icons (192px, 512px and maskable)
- Service worker for offline app-shell caching
- iOS home-screen metadata
- Original local video editing prototype

## Important: installation and sharing
A PWA must be served from HTTPS (or localhost for testing) for service workers and normal installation prompts to work. Opening `index.html` directly from a ZIP/file manager does not install it as a PWA.

### Free hosting options
Upload this folder to a static host that provides HTTPS, such as GitHub Pages or Cloudflare Pages. Then:
- iPhone/iPad: open the HTTPS site in Safari → Share → Add to Home Screen.
- Android: open in Chrome → menu → Install app / Add to Home screen.
- Windows: open in Edge or Chrome → install icon/menu → Install.
- macOS: use Chrome's install option where available; Safari users can add the site to the Dock on supported macOS versions.

## Current limitations
This is a PWA, not separate native App Store / Google Play packages. It does not yet provide native iOS/Android app-store binaries, background rendering, full native file-system integration, cloud sync, or complete CapCut feature parity. Video export is browser-based WebM and browser codec support varies.

Publishing native store apps later may require Apple/Google developer accounts, platform-specific builds, signing and review. A PWA is the most practical zero-cost first release.

## Run locally
For a quick UI preview, open `index.html` in a browser. For PWA install/offline testing, serve the folder from localhost, for example:
`python -m http.server 8000`
Then visit `http://localhost:8000` (localhost is treated as a secure development context by browsers).
