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

## Version v0.4.0

### Highlights
- School data seeding from external datasets  
- Website normalization to handle inconsistent input formats  
- Automated contact discovery from public-facing sources  
- Contact scoring and prioritization  
- Manual review and verification workflows  
- Outreach tracking and activity logging  
- Contact lifecycle status management  
- Centralized outreach activity view  
- CSV export for downstream usage 

---

## Current Features

### School Data Management
- Local database of school records  
- Structured import and normalization pipeline  
- Active/inactive school tracking  

### Contact Discovery
- Automated identification of potential staff contacts  
- Heuristic-based prioritization of relevant roles  
- Aggregation of contact data from multiple sources  

### Review Workflow
- Side-by-side comparison of candidate contacts  
- Selection of an official outreach contact per school  
- Reviewer notes and validation tracking  

### Outreach Tracking
- Logging of outreach actions across multiple methods  
- Historical tracking of communication attempts  
- Contact status progression (e.g., not contacted, attempted, responded, inactive)  
- Centralized outreach activity feed  

### Data Export
- Export of structured school and contact data  
- Supports reporting, handoff, and external workflows

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
