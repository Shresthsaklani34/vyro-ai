# VYRO AI — Installable PWA starter

This package turns the VYRO AI browser editor into an installable Progressive Web App (PWA).

## Included
- Responsive editor interface with Manual Edit and AI Edit modes
- Manual trim controls, text overlays, preview speed, volume and visual filters
- Local AI-style edit planner with platform, niche and goal presets
- Adaptive lower-resolution preview on lower-powered devices, decoded-frame-synchronized canvas drawing, and reduced redundant preview work
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
This is an early browser-based editor, not complete CapCut parity. The AI Edit mode currently builds a rule-based plan from your selected platform, niche, goal and clip duration. It does not yet understand the actual video frames, transcribe speech, find semantic highlights or call a real generative AI model. Those features require an AI backend/service and may have usage costs.

Manual editing currently includes single-clip trimming, text overlays, aspect ratios and basic visual looks; it is not yet a full multi-track editor. Export is browser-based WebM at preview-canvas resolution, and browser codec support varies. Preview optimizations reduce avoidable work but cannot guarantee zero lag on every device or with every codec/resolution. This is a PWA, not separate native App Store / Google Play packages; background rendering, full native file-system integration and cloud sync are not included.

Publishing native store apps later may require Apple/Google developer accounts, platform-specific builds, signing and review. A PWA is the most practical zero-cost first release.

## Run locally
For a quick UI preview, open `index.html` in a browser. For PWA install/offline testing, serve the folder from localhost, for example:
`python -m http.server 8000`
Then visit `http://localhost:8000` (localhost is treated as a secure development context by browsers).


## Preview performance update
The preview now draws on decoded video-frame callbacks when supported, with a throttled fallback on older browsers. Lower-powered devices use a smaller preview canvas to reduce per-frame canvas work. The source video is kept as a tiny off-screen element and metadata is loaded first. The service-worker cache version is bumped so the updated files can replace older cached assets. Actual playback still depends on the device decoder, browser, video codec, resolution, and frame rate.
