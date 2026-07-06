# Changelog

## 2026-07-06

### Added
- Duplicate (⧉) now opens an inline group picker so a copy can land in a different group than the original, instead of always copying in place. Defaults to Ungrouped.
- Counter tallies now group visually instead of drawing an ever-longer row of ticks: every 5 ticks absorb into one solid block, and every 10 (two blocks) absorb into one hollow, outline-only square, both colored by the prediction's status.
- Web app manifest (`manifest.json`) and a service worker (`sw.js`, stale-while-revalidate) so the app can be installed and used offline when served over http(s). No-ops harmlessly under Electron's `file://` origin.
- Desktop-web layout now caps at 520px wide and centers with a subtle border, instead of stretching edge-to-edge in a wide browser window.

### Changed
- Self-hosted the Inter and JetBrains Mono fonts instead of pulling them from Google Fonts on every launch — removes the app's only network dependency and fixes the flash-of-fallback-font when offline.
- Native browser/OS `confirm()` popups (delete group, delete moment, clear all data) replaced with a custom in-app confirm dialog matching the rest of the UI.
- Import now asks for confirmation before it replaces all existing predictions/groups/moments, instead of overwriting silently.
- Electron window position and size now persist across launches.
- Added a Content-Security-Policy locking the app to its own bundled assets (fonts, manifest, service worker, same-origin fetches only — no third-party hosts).

### Earlier (this batch, not yet released)
- Moments accordion with group state dots, centered title, raw-aware win/loss stats, drawer padding cleanup.
- Slim top bar, uniform icon buttons, larger prediction text, check/cross yes-no, settings additions.
- Compact view rows, 4-state status dots, top-right settings cog, generalized red-glow.
- Win/void glow on group cards; removed the blinking title cursor.
