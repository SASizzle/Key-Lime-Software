# Changelog

## v1.1.0 - 2026-04-23

### Added
- Added an optional lime-pattern background for the main content area, with a new Appearance setting to turn it on or off.
- Added collapse/expand support for the Outreach quick-add panel, including saved panel state between sessions.

### Improved
- Refined the School List action column so Quick Review, Edit, Run, and Find Website controls align more consistently.
- Improved Quick Review and edit modal spacing with reusable modal action layouts and better summary grid behavior on smaller screens.
- Polished the current best contact card on school detail pages with clearer status labels, tighter spacing, and a narrower card layout.
- Expanded large-text mode so navigation, badges, tables, settings, and supporting copy scale more consistently.
- Tuned the lime branding treatment across the sidebar and main background for better light- and dark-mode contrast.

### Fixed
- Fixed the single-school scrape failure state so the action button returns to the shorter `Run` label.
- Fixed missing trailing newlines in contact and outreach-history model files.

## v1.0.1 - 2026-04-21

### Improved
- Refined sidebar branding so the lime logo sits more cleanly behind the “Key” wordmark and shifts hue with the selected color palette.
- Tightened the Contacts table layout so school rows waste less space and crowded status/action columns display more cleanly.
- Polished the settings modal reset area with better alignment and a clearer destructive style for the full reset action.

### Fixed
- Fixed dark-mode dropdown styling so select arrows remain visible without reintroducing the earlier repeating-background bug.
- Fixed light-mode button hover contrast so button labels stay readable on pale hover states.
- Removed the oversized header lime watermark and kept the branding treatment in the intended sidebar position only.

## v1.0.0 - 2026-04-21

### Improved
- Tightened scraper extraction so structured staff-card layouts keep names paired with the correct titles more reliably instead of drifting across nearby records.
- Expanded junk-contact cleanup to catch more obvious non-person winners such as policy links, phone labels, pantry pages, bulletin links, and similar page furniture that previously surfaced as top-scoring contacts.
- Simplified the active batch-job card so in-progress schools show cleaner status text and less duplicated timestamp information.
- Improved the Contact Review save flow with a sticky current-selection action bar so the official-contact save action stays easy to reach even on long result sets.
- Reduced dashboard recent-scrape UI churn by updating rows in place instead of constantly rebuilding the table on each refresh cycle.

### Added
- Automatic startup and post-scrape cleanup that removes disposable junk contacts and reselects the best official contact when a stronger non-junk option exists.
- A total timeout for website autodiscovery so manual site lookup no longer appears to run forever.
- Regression tests covering structured staff-block extraction, compound title/name recovery, and junk-contact cleanup behavior.

### Fixed
- Fixed cases where strings such as `Principal: Ty H.` were being preserved poorly instead of recovering the person and role cleanly.
- Fixed recent dashboard scrape polling so it no longer behaves like a page refresh every few seconds.
- Fixed stuck `Finding...` website-discovery buttons by aborting long-running lookups on the client and returning a clear timeout result from the server.

## v0.7.0 - 2026-04-20

### Improved
- Refined the School List batch scrape panel with smoother collapse motion, clearer scope actions, and more polished cross-page monitoring behavior.
- Tightened the Contacts table so key fields fit more cleanly on standard screens, with better truncation behavior and less horizontal scrolling pressure.
- Simplified settings guidance around reset actions so section-level resets are easier to understand.
- Continued UI polish across sidebar controls, contact review surfaces, and dense operational tables based on beta feedback.

### Added
- Live dashboard recent-scrape activity that reflects current and recently finished scrape jobs instead of stale placeholder results.
- Outreach quick-entry candidates on the Outreach page, prioritizing recently scraped high-scoring contacts for faster manual logging.
- Server-side full-dataset sorting for export preview results, with sort state carried into preview pagination and downloads.
- Owner-facing usage documentation in `docs/OWNER_MANUAL.md`.

### Fixed
- Restored export sorting so it applies across the full filtered result set instead of only the currently loaded preview rows.
- Fixed contacts-page layout overflow so action buttons and confidence badges remain more usable at common desktop widths.
- Fixed remaining batch-panel usability rough edges, including saved collapse state handling and clearer control wording.
- Added the missing XLSX export dependency in `requirements.txt` so spreadsheet export works when packaged or installed from requirements.

## v0.6.0 - 2026-04-18

### Improved
- Refined batch scraping with live school-level progress cards, cross-page monitoring, collapsible results, safer cancellation behavior, and orphaned-job recovery on startup.
- Improved scraper throughput with configurable request timeouts, configurable page-worker concurrency, and parallel subpage processing.
- Tightened contact extraction so obvious junk labels such as portal, gallery, calendar, and similar non-person results are filtered more aggressively.
- Reduced wrong name/title pairing by using tighter local context when inferring roles from staff cards and mailto-driven layouts.
- Expanded website autodiscovery with stronger Oklahoma district-domain guessing, broader search queries, better scoring, and clearer manual-review notes.
- Expanded theme customization so color profiles drive the broader application palette instead of only a narrow accent layer.
- Reworked filter layouts across schools, contacts, review, and export screens to use space more efficiently.

### Added
- School-list search across school name, district, city, website, and website status.
- Dashboard startup notice explaining that some districts no longer publish staff directories publicly, with an option to hide future prompts.
- Regression coverage for website autodiscovery heuristics in `tests/test_website_discovery_service.py`.

### Fixed
- Restored export preview pagination and filter-aware preview loading for CSV/XLSX export workflows.
- Fixed export preview contact inclusion logic so rows with contact details are not incorrectly dropped.
- Fixed stale batch job state after server restart by reconciling SQLite job status with live worker threads.
- Fixed school-list action-column truncation issues so primary actions remain visible as the viewport narrows.
