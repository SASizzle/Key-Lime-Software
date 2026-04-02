# Key Lime Software

Welcome! This is the landing page for projects developed under Key Lime Software (formerly Pastel Platypus Posse). This repository currently hosts the **KLS Contact Finder**, a web-based tool for discovering and reviewing school contact data.

---

# Contact Finder — URL-Based Data Extractor

A full-stack web application designed to identify, analyze, and organize Oklahoma high school college liaisons and related staff contacts for outreach initiatives.

---

## Current Status

This project is an actively developed FastAPI-based local web application focused on scraping, scoring, and reviewing school contact data.

### Current Features
- Local browser-based UI powered by FastAPI
- School List page with live scrape trigger
- Custom contact scraper with scoring and deduplication logic
- Advanced Contact View overlay for quick inspection of scrape results
- Dedicated Contact Review page for comparing and selecting contacts
- Global settings panel with:
  - Dark mode
  - Compact layout
  - Debug options (scaffolding)
- Persistent frontend settings via localStorage
- Key Lime-themed UI with light/dark mode support
- Jinja-based templating system
- CSV export preview functionality
- Logging system for debugging and diagnostics

---

## In Progress / Planned Features

- SQLite-backed persistence layer
- Saving scrape results and verified contacts
- CSV-based school seeding
- Manual school entry and editing
- Contact review persistence (approval workflow)
- Improved scraper handling for complex/dynamic school websites
- Expanded export and reporting capabilities

---

## Deployment Model

The application is designed for **local, department-level deployment**.

Each organization can:
- Run its own isolated instance
- Maintain its own dataset
- Avoid reliance on external servers or shared infrastructure

---

## Preview

![Dashboard](dashboard2.png)

![School List](school-list.png)

![Scrape Results](scrape-result2.png)

![Advanced Contact View Overlay](adv-contact-view.png)

![Contact Review Page](contact-review.png)

![Export Page (Light Mode)](light-export.png)

![Settings Overlay](settings.png)

---

## Key Features

- Dashboard for scrape activity and confidence metrics
- School List with integrated scraping workflow
- Advanced contact inspection via overlay modal
- Contact Review page for manual validation
- Export-ready data structure
- Configurable UI settings (dark mode, layout, etc.)
- Modular scraping and scoring architecture
- Logging support for debugging and troubleshooting

---

## Tech Stack

- Python
- FastAPI
- JavaScript (Vanilla)
- HTML / CSS
- SQLite (planned integration)
- VS Code

---

## Project Notes

This project is currently in an **early-stage prototype / pre-production phase**.

Core workflows are functional, but:
- Data persistence is not yet implemented
- Scraper accuracy is still being refined
- Review selections are not yet saved

The current focus is on building a strong foundation for:
- reliable scraping
- intuitive review workflows
- scalable architecture

---

## Version

**v0.2.0**

Introduces:
- Key Lime Software rebrand
- Settings overlay system
- Dark mode and UI theming
- Advanced Contact View modal
- Contact Review page workflow
