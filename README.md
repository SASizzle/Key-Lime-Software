# Key Lime Software

Welcome! This repository contains projects developed under **Key Lime Software (KLS)** (formerly Pastel Platypus Posse). This repository currently hosts the **KLS Contact Finder**, a web-based tool for discovering, reviewing, and managing school contact data.

---

# Contact Finder: URL-Based Data Extractor

A full-stack web application designed to identify, analyze, and organize Oklahoma high school college liaisons and related staff contacts for outreach initiatives.

---

## Current Status

This project is an actively developed FastAPI-based local web application that has progressed beyond a prototype into a functional system with persistence and data workflows.

Core scraping, review, persistence, and import/export functionality are operational.

---

## Current Features

### Core Workflow
- Local browser-based UI powered by FastAPI  
- School List page with live scrape trigger  
- Custom contact scraper with scoring and deduplication logic  
- Advanced Contact View overlay for inspecting scrape results  
- Dedicated Contact Review page for comparing and selecting contacts  

### Persistence
- SQLite-backed storage for:
  - schools  
  - contacts  
  - verified (official) contact selections  
- Data persists across sessions  

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

---

## In Progress / Planned Features

- Excel (.xlsx) import support  
- Flexible column mapping for imported datasets  
- Improved scraper handling for dynamic or JavaScript-heavy sites  
- Contact history tracking and audit trail  
- Expanded dashboard metrics and reporting  
- Bulk operations and filtering tools  

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
- School List with integrated scraping workflow  
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
- VS Code  

---

## Project Notes

This project is currently in an **early-stage production-ready phase**.

### Current Strengths
- Fully functional core workflow  
- Persistent data storage  
- Import and export capabilities  
- Shared and maintainable UI structure  

### Areas of Ongoing Development
- Scraper accuracy for complex or inconsistent websites  
- Import schema flexibility  
- Performance optimization for larger datasets  
- Enhanced analytics and reporting  

---

## Version

**v0.2.1**

### Highlights
- SQLite-backed persistence for contacts and review workflow  
- CSV import system with preview and validation  
- Database-driven export functionality  
- Duplicate detection for imported contacts  
- Shared sidebar navigation and active page highlighting  
- Settings panel relocated to sidebar  
- General UI cleanup and template consolidation  
