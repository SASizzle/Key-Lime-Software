# KLS Contact Finder

**KLS Contact Finder** is a local-first outreach contact management system built for discovering, reviewing, verifying, and tracking school contacts over time.

Originally developed under **Key Lime Software (KLS)**, this project focuses on Oklahoma high school outreach workflows and is designed for practical day-to-day use by a single operator on a local machine.

> Note: The active source repository for the application is private.  
> This public repository is used for project information, release visibility, and previews.

---

## Overview

KLS Contact Finder is not just a scraper.

It is a workflow-focused system for:

- discovering likely contacts from school websites
- reviewing and validating candidate contacts
- storing verified contacts locally
- tracking outreach history and status
- filtering and organizing records
- exporting usable outreach data
- maintaining a trustworthy local dataset over time

The application runs locally and is intended for private, department-level or owner-operated use rather than cloud-hosted multi-user deployment.

---

## Version v0.6.0

### Release Highlights

Version **0.6.0** continues the transition from a scrape-and-review prototype into a more dependable local contact operations tool.

Key additions and improvements include:

- batch scrape workflow refinements with live school-level progress readouts
- cross-page batch status visibility while navigating the app
- improved batch cancellation behavior and stale-job recovery after restarts
- faster scraper page processing with configurable request and browser timeouts
- better junk-contact filtering for non-person labels and noisy page artifacts
- improved title/name pairing in certain staff-directory and mailto-based layouts
- stronger website autodiscovery with smarter Oklahoma district-domain guessing
- school-list search plus denser filter layouts across major workflow pages
- export preview pagination fixes and filtered export workflow improvements
- broader, full-palette appearance customization across supported color profiles
- startup guidance that some districts may restrict public directory access

---

## Current Capabilities

### School Management
- Local database of school records
- Active/inactive school tracking
- Website status and scrape readiness indicators
- Manual school entry and editing
- School pagination, search, and list management

### Contact Discovery
- Automated contact discovery from public-facing school websites
- Heuristic scoring for likely outreach-relevant roles
- Requests + BeautifulSoup scraping with selective Playwright fallback
- Duplicate reduction and contact merge behavior across re-scrapes
- Improved filtering of junk names, portal-like labels, and non-person directory artifacts
- Website autodiscovery support for schools with missing or uncertain website records

### Review Workflow
- **Quick Review** for fast official-contact decisions
- **Full Review** for deeper record management and outreach context
- Reviewer notes and verification tracking
- Official contact selection per school

### Outreach Tracking
- Structured outreach history per contact
- Methods supported:
  - email
  - phone call
  - text
  - in person
  - mailed material
  - other
- Contact status tracking:
  - not contacted
  - attempted
  - responded
  - inactive
- Central outreach activity view

### Contact Management
- Global contact table
- Keyword search
- Filtering by school, district, city, status, email/phone presence, notes, outreach state, and verification state
- Sorting and pagination
- Manual contact entry
- Trust and completeness cues for faster review

### Import / Export
- CSV import preview before commit
- Validation and duplicate-aware import handling
- Export preview and scoped export
- CSV export
- XLSX export

### User Experience
- Settings modal with live-applied preferences
- Dark mode and appearance settings
- Broader color-profile control across the full interface palette
- Table usability improvements
- Fixed/collapsible sidebar
- Local-first workflow optimized for speed and repeat use

---

## Deployment Model

KLS Contact Finder is designed for **local-first deployment**.

The intended operating model is:

- single owner/operator
- local machine use
- local data storage
- no dependence on external hosted infrastructure
- browser-based local app experience
- packaged desktop launcher support for demo/release builds

This project is intentionally optimized for simple private use before any future multi-user or enterprise features.

---

## Public Repository Note

This public repository does **not** contain the active private source code for the full application.

It exists to provide:

- product overview
- release/version visibility
- preview screenshots
- project notes
- public-facing changelog context

---

## Preview

![Dashboard](dashboard.png)

![School List](school-list.png)

![Scrape Results](scrape-result.png)

![Advanced Contact View Overlay](adv-contact-view.png)

![Contact Review Page](contact-review.png)

![Export Page](light-export.png)

![Settings Overlay](settings.png)

---

## Product Direction

KLS Contact Finder is being developed toward a stable **v1.0.0** local release focused on:

- stronger contact discovery quality
- clearer trust and verification signals
- better record maintenance over time
- reliable batch workflows
- practical local packaging and deployment

Current development is centered on making the tool operationally dependable rather than expanding into enterprise-only feature areas.

---

## Planned / Ongoing Improvements

Areas still being refined include:

- deeper single-school scrape accuracy
- clearer scrape confidence and source transparency
- stronger full-review record management workflows
- additional duplicate-handling safeguards
- continued UI polish for dense operational tables
- final packaging and local release hardening

---

## Tech Stack

The application is built around a local web app architecture using:

- Python
- FastAPI
- SQLite
- SQLAlchemy
- Jinja2
- Vanilla JavaScript
- HTML / CSS
- Requests
- BeautifulSoup
- Playwright

---

## Status

KLS Contact Finder is currently in an active pre-v1 release phase.

Version **0.6.0** reflects a meaningful round of refinement around batch operations, scraper quality, website autodiscovery, filtering/export workflows, and operator-facing usability.
