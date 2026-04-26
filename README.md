# KLS Contact Finder

KLS Contact Finder is a local-first outreach contact management system for Oklahoma high school workflows. It combines school list management, website discovery, contact scraping, review, outreach tracking, import/export, and Windows-friendly packaging in one single-operator application.

This README is the entry point. The fuller product documentation set lives in [`docs/`](docs/).

## Product Preview

### Dashboard

![KLS Contact Finder dashboard preview](Product%20Previews/dashboard-page.png)

### School List

![KLS Contact Finder school list preview](Product%20Previews/schools-page.png)

### Contact Quick Review

![KLS Contact Finder contact review preview](Product%20Previews/quick-review.png)

### Export Preview

![KLS Contact Finder export preview](Product%20Previews/export-page.png)

### Dark Mode - Lime

![KLS Contact Finder lime dark](Product%20Previews/lime-dark.png)

### Light Mode - Sunset

![KLS Contact Finder sunset light](Product%20Previews/sunset-light.png)

### Dark Mode - Sunset

![KLS Contact Finder sunset dark](Product%20Previews/sunset-dark.png)

## Project Status

- The app is functionally usable today for local outreach work.
- The repository DOES NOT include the original `v1.0.0` release or follow-up refinements recorded in [`CHANGELOG.md`](CHANGELOG.md).
- This README reflects private repository behavior rather than only the original launch state.

## Current Features

- School list management with search, pagination, website status, scrape readiness, and quick actions
- Single-school scraping with result summaries and immediate review
- Batch scraping with background progress, cancel support, and cross-page visibility
- Website autodiscovery for schools missing or needing review of their site
- Quick Review for fast official-contact selection
- Full Review for deeper contact management, manual entry, notes, and outreach history
- Automatic post-scrape contact cleanup that removes obvious junk while preserving user-touched records
- Outreach tracking with contact statuses, notes, outcomes, timestamps, and recent quick-add candidates
- CSV import with preview and commit steps
- CSV and XLSX export with preview, filtering, and sorting
- Appearance, table, workflow, and local preference settings
- Portable Windows packaging via PyInstaller

## Tech Stack

- FastAPI
- Uvicorn
- SQLAlchemy
- SQLite
- Jinja2
- JavaScript
- CSS
- `requests`
- BeautifulSoup
- Playwright fallback
- PyInstaller

## Documentation Set

- [`PRESS_RELEASE.md`](PRESS_RELEASE.md): customer-facing summary
- [`FAQ.md`](FAQ.md): user questions, design decisions, and limitations
- [`PRODUCT_SPEC.md`](PRODUCT_SPEC.md): product goals, workflows, behavior, dependencies, and known gaps
- [`USE_CASES.md`](USE_CASES.md): real step-by-step workflow scenarios
- [`OWNER_MANUAL.md`](OWNER_MANUAL.md): day-to-day operational guide

## Runtime Behavior

- In development, runtime files stay in the project root.
- In a frozen build, runtime files prefer the executable directory.
- If the executable directory is not writable, the app falls back to `%LOCALAPPDATA%\KLS Contact Finder`.
- The local SQLite database is stored as `app.db`.
- Logs are written under `logs\kls-contact-finder.log`.
- If the database is empty on startup, the app seeds schools from `data\oklahoma_high_schools_seed.csv`.

## Operational Notes

- Internet access is required for scraping and website autodiscovery.
- Scraping uses `requests` and BeautifulSoup first, with Playwright browser fallback for tougher pages.
- Some districts no longer publish full staff directories publicly, so results may be partial or unavailable.
- Recent scrape cleanup removes many obvious junk contacts automatically, but review is still required.
- Import currently supports CSV only.
- Export is based on each school's verified contact when one exists; otherwise it uses the top-ranked saved contact.
- The current Windows package is portable and not yet a signed installer.

## Related Files

- [`CHANGELOG.md`](CHANGELOG.md)
- [`LICENSE`](LICENSE)
- [`OWNER_MANUAL.md`](OWNER_MANUAL.md)
