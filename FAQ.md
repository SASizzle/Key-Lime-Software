# FAQ

## General

### What is KLS Contact Finder?

KLS Contact Finder is a local-first application for managing Oklahoma high school outreach data. It helps you keep a school list, discover websites, scrape likely contacts, review the best options, log outreach, and export working lists.

### Who is the product for?

It is built for a single local operator rather than a team. The current design assumes one person is managing the database on one machine at a time.

### Is it a cloud product?

No. The working database is local SQLite, and the packaged build runs a local server that opens in your browser.

### Where is the data stored?

In development, data stays in the project folder. In a packaged build, runtime files prefer the executable directory and fall back to `%LOCALAPPDATA%\KLS Contact Finder` if needed.

## Design Decisions

### Why is the product local-first?

Local-first operation keeps setup simple, avoids shared infrastructure requirements, and fits the current single-operator workflow. It also makes packaging and classroom/demo use easier.

### Why does the app use a browser if it is local-first?

The UI is delivered through a local FastAPI server and opened in the browser. That approach keeps the interface flexible while still behaving like a desktop-style local tool.

### Why does KLS separate Quick Review from Full Review?

Quick Review is optimized for fast official-contact decisions from the School List. Full Review is for deeper record management, including manual contacts, broader filtering, and outreach history.

### Why does the app keep both scraped contacts and a verified official contact?

Scraped candidates are working inputs. The verified official contact is the current best choice for that school. Keeping both supports re-review after future scrapes without losing useful alternatives.

## Scraper Behavior

### How does scraping work?

The scraper fetches public school pages, looks for likely staff contact information, scores candidate contacts, merges new results with existing records, and removes obvious noise where safe.

### Does the scraper guarantee the right contact?

No. It produces likely candidates, not guaranteed truth. Human review is still required.

### Why are some scrape results weak or incomplete?

Many districts no longer publish full staff directories publicly. Some schools expose only summary pages, partial contact details, or no useful public contact data at all.

### What is website autodiscovery?

Autodiscovery tries to find a likely official school website for a school record that is missing one or needs review. It uses Oklahoma-oriented heuristics, search queries, and candidate validation.

### What do website statuses mean?

- `missing`: no usable site is saved
- `candidate_found`: the app found a likely site that still deserves review
- `verified`: the site is considered confirmed
- `manual_review_needed`: the app found something questionable or ambiguous
- `failed`: discovery did not find a usable result

### What happens if website discovery takes too long?

The backend applies a total timeout so the lookup does not appear to run forever. When that happens, the school is marked with a failed discovery result and a note explaining the timeout.

### Why did a contact disappear after a later scrape?

The cleanup step removes obvious junk contacts unless the record looks user-preserved. Contacts with outreach history, notes, verification, or a non-default status are intentionally protected.

### Does Playwright always run?

No. The scraper uses `requests` and BeautifulSoup first for speed. Playwright is a fallback for pages that appear to need browser rendering or JS challenge handling.

## Import and Export

### What file types can I import?

Import currently supports CSV only.

### What does the import preview do?

Preview parses the file, validates rows, shows errors, and summarizes likely duplicates or new schools before anything is written.

### What happens if an imported school does not already exist?

The import flow creates a new school record with a missing website status, then adds the contact.

### What counts as a duplicate during import?

The current duplicate check looks for an existing contact in the same school by email first, then by name plus title.

### What does export include?

Export works at the school level. It uses the verified official contact when one exists; otherwise it exports the top-ranked saved contact for that school.

### Can I export Excel files?

Yes. Export supports both CSV and XLSX.

## Settings and Preferences

### Are settings shared across machines?

No. Current settings are stored in the browser's local storage on the machine you are using.

### Do all settings change backend behavior?

Not yet. Appearance, table, and workflow preferences are clearly active in the UI. Some scraper settings are currently best treated as local UI or troubleshooting preferences rather than guaranteed backend overrides.

## Limitations

### Is this a multi-user system?

No. The current product does not include user accounts, permissions, or concurrent collaboration workflows.

### Is the Windows package a signed installer?

No. The current packaging is portable and unsigned, so some systems may show SmartScreen or antivirus warnings.

### Does KLS verify whether a contact is still valid after export?

No. The quality of export results depends on the current saved data and the public information available when the records were last reviewed.
