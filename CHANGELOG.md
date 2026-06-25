# Changelog

## v1.0.0 — 2026-06-25

Initial Chrome release. Feature-equivalent port of Converse for Firefox v1.1.0.

### Platform

- Manifest V3 — service worker background, `action` API, `host_permissions`
- Incognito support — IndexedDB works in Incognito windows; data clears automatically
  when the window closes; the drawer footer shows **· Incognito** as a reminder
- webextension-polyfill (v0.12.0) bridges `browser.*` → `chrome.*` throughout

### Features

- Full-text search across all Claude conversations — searches message bodies, not just titles
- Incremental sync — only fetches conversations that changed since last sync
- Sort results by relevance or date modified
- Highlighted snippets — shows the matching passage with search terms marked in context
- Click any result to navigate directly to that conversation
- Middle-click opens conversation in a new tab
- Right-click shows browser context menu (Open in New Tab, Copy Link, etc.)
- Keyboard shortcut: `Ctrl`+`Shift`+`F` to open/close, `Escape` to close
- Sync starts automatically in the background as soon as the page loads
- **Paste to File** — pastes above a configurable character threshold are automatically
  uploaded as `.txt` file attachments; Claude reads the file directly
- **`Ctrl`+`Shift`+`V`** — paste normally at any time, bypassing Paste to File
- **Inline settings panel** — gear icon in the drawer footer opens settings inside the drawer
- **Sort toggle pill** — compact Relevance / Recent toggle below the search input

### Design

- Drawer UI matches claude.ai's own design language — same typography, spacing, and color tokens
- Automatically follows claude.ai's light and dark mode with zero lag
- Fallback palette for `claude.ai/design/*` which uses a different CSS token system

### Privacy

- All data stored locally in browser IndexedDB — nothing ever leaves the device
- No analytics, no telemetry, no external servers
