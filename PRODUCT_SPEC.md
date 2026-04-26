# Product Spec

## Document Purpose

This document describes the current KLS Contact Finder product as implemented in the live repository, with clear separation between implemented behavior and candidate future work. It reflects the codebase after the `v1.0.0` launch and subsequent refinements recorded in `CHANGELOG.md`.

## Product Summary

KLS Contact Finder is a local-first outreach contact management application for Oklahoma high school workflows. Its purpose is to help a single operator maintain a working school database, identify likely public-facing contacts, choose the best official contact for each school, track outreach over time, and export filtered working lists.

## Problem Statement

Outreach preparation is slow when school information is fragmented across inconsistent public websites. The operator often has to:

- find the right school website
- inspect whether that site is usable
- scrape or manually gather public contact information
- decide which contact is most relevant
- remember what outreach already happened
- prepare filtered lists for follow-up work

KLS Contact Finder reduces that overhead by keeping those tasks inside one local workflow.

## Target User

Primary user:

- one local outreach operator maintaining school and contact data

Secondary use:

- demo or instructor review environments that need a realistic local workflow

## Product Goals

- Keep outreach contact management local and lightweight.
- Reduce the time required to move from school selection to contact follow-up.
- Make scraped results reviewable instead of opaque.
- Preserve operator judgment when selecting an official contact.
- Support repeated use over time rather than one-off scraping.
- Provide practical import/export paths for surrounding workflows.

## Non-Goals

- Multi-user collaboration
- Role-based permissions or authentication
- Cloud synchronization
- Guaranteed contact verification
- Fully autonomous outreach decisions
- Large-scale distributed scraping infrastructure

## Operating Model

- Local FastAPI application
- SQLite persistence
- Browser-based UI served from the local machine
- Optional packaged Windows executable using PyInstaller
- Single active operator assumption

## Core Workflows

### 1. Initial Startup and Seeding

1. User launches the app.
2. App initializes the SQLite database.
3. If no schools exist yet, the app seeds from `data/oklahoma_high_schools_seed.csv`.
4. App runs startup cleanup and batch-job reconciliation.
5. User lands on the dashboard and proceeds to School List or other pages.

### 2. School Website Discovery

1. User opens a school record with a missing or questionable site.
2. User runs website discovery.
3. System generates Oklahoma-oriented search queries and direct domain guesses.
4. Candidate sites are validated and scored.
5. The school record is updated with candidate URL, status, confidence, notes, and last-checked time.
6. User reviews the result before trusting it.

### 3. Single-School Scrape

1. User runs scrape for a specific school.
2. System normalizes the website URL and fetches public pages.
3. Scraper extracts candidate contacts, merges them with existing saved contacts, and removes obvious junk where safe.
4. System updates scrape metadata and produces a best-contact summary.
5. User reviews results immediately in Quick Review or Full Review.

### 4. Batch Scrape

1. User selects a scope: selected schools, all active schools, or selected plus all active.
2. System creates a batch scrape job and background worker thread.
3. Progress remains visible in the School List and across other pages.
4. User may continue working while the batch job runs.
5. User may request cancellation.
6. System stores job-level and school-level outcome details.

### 5. Contact Review and Selection

1. User inspects candidate contacts for a school.
2. User chooses the best official contact when appropriate.
3. System stores `verified_contact_id` on the school and sets `last_verified_at` on the contact.
4. Review notes and manual contact entries remain available for later refinement.

### 6. Outreach Tracking

1. User logs outreach from Full Review or the Outreach quick-add panel.
2. System stores method, custom label if needed, timestamp, note, and outcome.
3. If the contact was previously `not_contacted`, system advances status to `attempted`.
4. Outreach history becomes available for filters, review, and contact summaries.

### 7. Import and Export

1. User previews a CSV import before writing data.
2. System validates rows and summarizes duplicates or new schools.
3. On commit, system inserts contacts and creates missing schools where needed.
4. For export, user filters and previews school-level rows, then downloads CSV or XLSX.

## System Behavior

### School Data

- School records include identity fields, website metadata, activity state, scrape state, and optional verified contact.
- Website readiness is derived from URL presence plus website status.
- Inactive schools can be hidden or shown depending on workflow.

### Contact Data

- Contact records may be scraped or added manually.
- A contact can exist without full information, as long as at least one of name, email, or phone is present for manual entry.
- Contact status options are `not_contacted`, `attempted`, `responded`, and `inactive`.
- Verified contacts are not the only contacts stored for a school; alternatives remain available for later review.

### Scraping

- The scraper uses `requests` and BeautifulSoup as the default path.
- Playwright is available as a fallback when browser rendering is needed.
- Existing contacts are merged instead of blindly duplicated.
- Post-scrape cleanup removes obvious junk contacts unless the user has already preserved them through activity or review.

### Batch Job Handling

- Batch jobs are stored in SQLite with per-school items.
- The app reconciles orphaned jobs on startup.
- Batch progress is visible outside the School List through a global monitor banner.
- Cancellation is cooperative; an in-progress school can be discarded so the batch can stop cleanly.

### Runtime and Packaging

- Development runtime files stay in the project directory.
- Frozen runtime files prefer the executable directory and fall back to `%LOCALAPPDATA%\KLS Contact Finder`.
- The packaged launcher opens the browser automatically and shuts down when tracked browser tabs are gone.

## Implemented Features

### Implemented Today

- Dashboard with recent scrape activity and startup notice
- School List with search, pagination, status badges, add/edit actions, scrape actions, and website discovery
- Single-school scrape flow
- Batch scrape with saved panel state, cross-page progress, and cancel support
- Quick Review for fast official-contact selection
- Full Review for detailed contact filtering and outreach history
- Manual contact creation
- Outreach feed and outreach quick-add candidates
- Contact-level filters for school, district, city, title, status, email, phone, notes, verification, and outreach activity
- CSV import preview and commit
- CSV and XLSX export preview/download
- Local UI settings for appearance, tables, workflow, and some scraper-related preferences
- PyInstaller packaging support

## Planned or Candidate Future Work

These items are not implemented in the current repository as committed behavior. They are candidate follow-on directions inferred from current limitations and packaging state.

- Signed Windows installer instead of portable-only packaging
- True multi-user or shared deployment support
- Authentication and role-based permissions
- Broader import formats beyond CSV
- Stronger backend wiring for every scraper-related UI preference
- More explicit reporting and audit summaries for outreach operations

## Dependencies

### Application Dependencies

- FastAPI
- Uvicorn
- SQLAlchemy
- Pydantic
- Pydantic Settings
- python-dotenv
- requests
- beautifulsoup4
- jinja2
- playwright
- email-validator
- python-multipart
- openpyxl

### Runtime Assets

- `templates/`
- `static/`
- `data/oklahoma_high_schools_seed.csv`
- `launcher.py`
- `KLS_Contact_Finder.spec`

## Known Limitations

- Scrape quality depends on what each school publishes publicly.
- Some schools expose little or no useful public staff data.
- Website autodiscovery improves speed but still requires human review.
- The product is optimized for one operator, not concurrent shared use.
- Import is CSV-only.
- Export operates at the school level and does not export every contact candidate by default.
- The portable Windows build is not yet a signed installer.
- Some scraper-related settings shown in the UI appear to be local preferences rather than full backend controls.

## Areas to Watch

- Documentation should avoid implying that scraping is authoritative.
- Documentation should avoid implying that every settings control changes backend execution.
- Documentation should treat candidate future work as aspirational, not committed roadmap.
