# Key Lime Software

Welcome! This repository contains projects developed under **Key Lime Software (KLS)** (formerly Pastel Platypus Posse). This repository currently hosts the **KLS Contact Finder**, a web-based tool for discovering, reviewing, and managing school contact data.

---

# Contact Finder: URL-Based Data Extractor

A full-stack web application designed to identify, analyze, and organize Oklahoma high school college liaisons and related staff contacts for outreach initiatives.

---

## Current Status

This project is an actively developed FastAPI-based local web application that has progressed beyond a prototype into a functional system with persistence and structured data workflows.

The application now includes seeded datasets, school-level management, website discovery, and a full scrape → review → persist → export pipeline.

---

## Current Features

### Core Workflow
- Local browser-based UI powered by FastAPI  
- School List page with:
  - website status tracking  
  - scrape readiness indicators  
  - conditional scrape and discovery actions  
- Custom contact scraper with scoring and deduplication logic  
- Advanced Contact View overlay for inspecting scrape results  
- Dedicated Contact Review page for comparing and selecting contacts  

### Persistence
- SQLite-backed storage for:
  - schools  
  - contacts  
  - verified (official) contact selections  
- Seeded Oklahoma high school dataset for immediate usability  
- Data persists across sessions  

### Website Management
- Website lifecycle tracking:
  - missing  
  - candidate found  
  - verified  
  - manual review needed  
  - failed  
- Website autodiscovery for schools without URLs  
- Scrape readiness classification:
  - no website  
  - needs review  
  - lookup failed  
  - ready  
- Manual override and validation for school website data  
- Automatic cleanup of stale discovery metadata after verification  

### Import / Export
- CSV Import system:
  - preview before commit  
  - validation of required fields  
  - duplicate detection and skipping  
- Export page:
  - database-backed preview  
  - CSV download of best contacts  

### User Interface
- Shared sidebar navigation across all pages  
- Active page highlighting  
- School List enhancements:
  - status badges  
  - readiness indicators  
  - inactive school filtering  
- Global settings panel with:
  - dark mode  
  - compact layout  
  - debug options (scaffolding)  
- Persistent user settings via localStorage  
- Key Lime-themed UI with light/dark support  

### System Features
- Logging system for debugging and diagnostics  
- Jinja-based templating with shared base layout  
- Modular architecture for scraper and backend expansion  
- Structured API routes for school, contact, and workflow management  

---

## In Progress / Planned Features

- Batch website discovery and bulk scraping workflows  
- Excel (.xlsx) import support  
- Flexible column mapping for imported datasets  
- Improved scraper handling for dynamic or JavaScript-heavy sites  
- Contact history tracking and audit trail  
- Expanded dashboard metrics and reporting  
- Performance optimization for larger datasets  

---

## Deployment Model

The application is designed for **local, department-level deployment**.

Each organization can:
- run its own isolated instance  
- maintain its own dataset  
- avoid reliance on external servers or shared infrastructure  

---

## Preview

![Dashboard](dashboard2.png)

![School List](school-list.png)

![Scrape Results](scrape-result2.png)

![Advanced Contact View Overlay](adv-contact-view.png)

![Contact Review Page](contact-review.png)

![Export Page](light-export.png)

![Settings Overlay](settings.png)

---

## Key Features

- End-to-end workflow: scrape → review → persist → export  
- Seeded school dataset for immediate onboarding  
- Website discovery and validation workflow  
- School List with status and readiness indicators  
- Advanced contact inspection via overlay modal  
- Contact Review page for manual validation  
- Import and export support for data management  
- Configurable UI settings (dark mode, layout, etc.)  
- Modular scraping and scoring architecture  
- Logging support for debugging and troubleshooting  

---

## Tech Stack

- Python  
- FastAPI  
- JavaScript (Vanilla)  
- HTML / CSS  
- SQLite  
- Jinja2  
- BeautifulSoup  
- Requests  
- VS Code  

---

## Project Notes

This project is currently in an **early-stage production-ready phase**.

### Current Strengths
- Fully functional core workflow  
- Persistent data storage  
- Seeded dataset for immediate usability  
- Website lifecycle and readiness tracking  
- Structured and maintainable UI system  

### Areas of Ongoing Development
- Scraper accuracy for complex or inconsistent websites  
- Website autodiscovery reliability  
- Import schema flexibility  
- Performance optimization for larger datasets  
- Enhanced analytics and reporting  

---

## Version

**v0.3.0**

### Highlights
- Seeded Oklahoma high school dataset  
- School editing workflow with validation  
- Website status tracking and lifecycle management  
- Scrape readiness indicators in School List  
- Website autodiscovery with scoring and filtering  
- Inactive school filtering and management  
- Cleanup of stale autodiscovery metadata after manual verification  
- Improved Advanced Contact View modal  
- UI polish and consistency improvements  
