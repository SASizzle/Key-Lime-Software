# KLS Contact Finder

KLS Contact Finder is a local-first outreach contact management system for Oklahoma high school workflows. It combines school list management, website discovery, contact scraping, review, outreach tracking, import/export, and Windows-friendly packaging in one single-operator application.

This README is the entry point. The fuller product documentation set lives in [`docs/`](docs/).

## Project Status

- The app is functionally usable today for local outreach work.
- The repository includes the original `v1.0.0` release plus follow-up refinements recorded in [`CHANGELOG.md`](CHANGELOG.md).
- This README reflects current repository behavior rather than only the original launch state.

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

- [`docs/PRESS_RELEASE.md`](docs/PRESS_RELEASE.md): customer-facing summary
- [`docs/FAQ.md`](docs/FAQ.md): user questions, design decisions, and limitations
- [`docs/PRODUCT_SPEC.md`](docs/PRODUCT_SPEC.md): product goals, workflows, behavior, dependencies, and known gaps
- [`docs/USE_CASES.md`](docs/USE_CASES.md): real step-by-step workflow scenarios
- [`docs/OWNER_MANUAL.md`](docs/OWNER_MANUAL.md): day-to-day operational guide

## Run Locally

From the project root:

```powershell
pip install -r requirements.txt
uvicorn app.main:app --reload
```

If you are using the local virtual environment:

```powershell
.venv\Scripts\python -m pip install -r requirements.txt
.venv\Scripts\python -m uvicorn app.main:app --reload
```

Open the app at:

```text
http://127.0.0.1:8000/dashboard
```

## Packaging

This repo includes:

- `launcher.py`
- `KLS_Contact_Finder.spec`

Build a portable Windows executable with:

```powershell
pyinstaller KLS_Contact_Finder.spec
```

The packaged build starts a local server, opens the dashboard in the default browser, and shuts down when no tracked browser tabs remain open.

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
- [`docs/OWNER_MANUAL.md`](docs/OWNER_MANUAL.md)
