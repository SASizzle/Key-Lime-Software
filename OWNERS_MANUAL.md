# KLS Contact Finder Owner's Manual

## Overview

KLS Contact Finder is a local-first contact management tool designed to help you find, review, verify, and track outreach contacts for Oklahoma high schools.

The system is built to support a simple working routine:

- keep a list of schools
- locate likely contacts from school websites
- review and confirm the best contact for each school
- track outreach over time
- search, filter, and export records when needed

This is not just a one-time scraping tool. It is meant to help you maintain a working contact database over time.

If you want supporting reference material, see:

- [README](../README.md)
- [FAQ](FAQ.md)
- [Product Spec](PRODUCT_SPEC.md)
- [Use Cases](USE_CASES.md)

## Getting Started

### Launching the app

In normal day-to-day use, you will open the packaged KLS Contact Finder application from your local machine.

Typical startup flow:

- double-click the KLS Contact Finder executable
- wait a moment for the local app to start
- your default browser should open automatically
- the app usually opens to the Dashboard

If the browser does not open on its own:

- wait a few seconds
- check whether the app is already running in the background
- try opening the local app page manually if your setup instructions include a saved local address

### What happens on first launch

On first use, the app may populate the database with its built-in school seed list. That gives you a starting point instead of an empty system.

### What you will see first

The main navigation is on the left side:

- Dashboard
- School List
- Contacts
- Outreach
- Export
- Import

For most work, you will spend the most time in:

- School List
- Contact Review
- Contacts
- Outreach

## Core Workflow

### Recommended day-to-day process

Use this order for the cleanest workflow:

- open the app
- go to **School List**
- confirm the school website is present and usable
- run a scrape for one school or a batch of schools
- open **Quick Review** or **Full Review**
- choose or verify the official contact
- add notes if needed
- log outreach activity after calls, emails, texts, or other actions
- use **Contacts** and **Outreach** to manage follow-up work
- export filtered results when you need a working list outside the app

### When to use single-school scrape

Use a single-school scrape when:

- one school matters right now
- you want a deeper look at one site
- a school needs more careful review
- you want to inspect results immediately after scraping

### When to use batch scrape

Use batch scrape when:

- you want broader coverage across many schools
- you are refreshing records in bulk
- you want to process selected schools, all active schools, or both

The batch panel shows progress while the job runs. You can move to other pages and keep working while the scrape continues.

## Dashboard

### What the dashboard is for

The **Dashboard** gives you a fast snapshot of recent scrape activity and overall progress.

Use it to:

- confirm the app is running normally
- see recent scrape results
- notice whether your school list has been worked recently
- read the startup reminder about districts that no longer publish full staff directories

The dashboard is a starting point, but most action happens on the other pages.

## Scraper Behavior

### What the scraper does

The scraper visits school websites and looks for likely staff contacts based on the information that appears publicly on those pages.

It may pull:

- names
- job titles
- email addresses
- phone numbers
- source pages

It then ranks likely contacts so you can review them more quickly.

### What to expect from scrape results

Scrape results are often helpful, but they are not perfect.

You should expect a mix of:

- strong contact matches
- partial contacts
- contacts that need review
- occasional weak or noisy results

A contact with a good name and email can still be useful even if the phone number is missing.

### Why some schools return weak results

Some schools no longer publish full staff directories publicly. In those cases, KLS may only find:

- public-facing staff pages
- department pages
- partial contact details
- no usable contact at all

This does not always mean the scraper failed. It may simply mean the school does not expose much information on its public site.

### Website discovery

If a school does not already have a good website listed, the system can try to find one for you.

Use **Find Website** when:

- the school has no website saved
- the saved website looks wrong
- a school is marked as missing or needs review

After discovery, you should still review the result before trusting it fully.

If website discovery takes too long, the lookup will stop instead of running forever. When that happens:

- review whether the school already has a usable site saved
- try the lookup again later
- enter or correct the website manually if you already know the right address

## Contact Management

### School List

The **School List** page is your main starting point.

From here you can:

- search schools
- view website status
- view scrape readiness
- add a school
- edit a school
- scrape a school
- find a website
- open Quick Review

### Quick Review

Use **Quick Review** when you want to make a fast decision.

Best use cases:

- choosing the official contact quickly
- checking a short list of likely candidates
- adding brief reviewer notes
- moving through many schools efficiently

Typical Quick Review flow:

- open Quick Review from the School List
- compare the candidates shown
- choose the best contact
- add a short note if needed
- save the official contact

### Full Review

Use **Full Review** when you need deeper control.

Best use cases:

- reviewing all candidate contacts for a school
- checking trust and completeness
- editing notes
- adding manual contacts
- reviewing outreach history
- logging new outreach entries

Typical Full Review flow:

- open the Full Review page for a school
- scan the contact table
- compare trust indicators and status
- select the best contact
- add review notes
- save as official contact
- use the outreach section for follow-up tracking

### Manual contact entry

If the scraper misses someone useful, you can add a contact manually.

Recommended times to do this:

- a school lists a contact you found outside the scrape results
- you have a verified contact from direct communication
- the scrape found partial data and you want to complete the record

When adding a manual contact, include as much as you know:

- name
- title
- email
- phone
- source page
- notes
- current status

### Official contacts

Each school should end up with one main official contact when possible.

Use the official contact choice to keep your working list clear and to make exports more useful.

## Outreach Tracking

### What outreach tracking is for

Outreach tracking helps you keep a history of what has already happened with a contact.

This helps you avoid:

- duplicate follow-up
- guessing when you last reached out
- losing context after a conversation

### Supported outreach methods

The system supports these methods:

- email
- phone call
- text
- in person
- mailed material
- other

If you choose **Other**, add a short custom label.

### How to log outreach

From the Full Review page:

- select the contact
- go to the **Outreach History** section
- click **Add Outreach**
- choose the method
- add a note
- add an outcome if useful
- save the entry

From the **Outreach** page, you can also use the recent quick-entry list:

- look for recently scraped contacts near the top of the page
- higher-scoring contacts appear first
- click a contact card to open a faster outreach entry flow
- save the outreach record when finished

If you do not need the quick-entry list while reviewing older outreach, use **Collapse** on the Quick Add Outreach panel. The app remembers that choice the next time you open the page.

### Contact status

Each contact can be marked with a status:

- **Not Contacted**: no outreach yet
- **Attempted**: outreach was sent or tried
- **Responded**: the contact replied or engaged
- **Inactive**: no longer usable or not worth active follow-up

Keep these statuses current. They make filtering and export more useful.

### Outreach page

Use the **Outreach** page to review recent outreach activity across schools.

This page is useful for:

- seeing the latest activity in one place
- reviewing notes quickly
- jumping back into school review when needed

## Search and Filtering

### Why search and filtering matter

KLS is meant to help you work quickly across a large number of records. Use filters often instead of scrolling through everything manually.

### School List search

On the **School List** page, you can search by terms such as:

- school name
- district
- city
- website
- website status

Use this when you want to:

- find a specific school fast
- narrow a district list
- find schools missing websites or needing review

### Contacts filtering

On the **Contacts** page, you can narrow records by combinations such as:

- school
- district
- city
- title
- contact status
- whether email exists
- whether phone exists
- whether notes exist
- whether outreach exists
- verification state

This is useful for building practical working queues, such as:

- all not-contacted contacts with email
- all responded contacts in one district
- contacts missing phone numbers

### Full Review filtering

Inside **Full Review**, use the contact filters to narrow the candidate list for one school.

This is especially helpful when a school has:

- many scrape results
- mixed-quality candidates
- manual entries combined with scraped entries

### Best practice

Use filters in layers:

- start broad
- narrow to one district, status, or contact type
- review results
- reset when done

## Exporting Data

### What export is for

Use the **Export** page when you need a structured list outside the app for working, reporting, or sharing internally.

### Export workflow

Recommended export steps:

- open **Export**
- choose your filters
- review the preview table
- confirm the scope looks right
- download CSV or XLSX

The preview is important because it shows what will actually be included before you download the file.

### Export options

You can export:

- all matching records
- only filtered records
- inactive schools if needed
- schools without contacts if needed

You can also filter by:

- contact status
- email presence
- phone presence
- search text

### What export uses as the contact

Export works at the school level. If a school has a verified official contact, that record is used. If not, the app uses the top-ranked saved contact for that school.

### Choosing file type

Use **CSV** when:

- you want a simple file
- you plan to open it in many different tools

Use **XLSX** when:

- you want an Excel-ready file
- you prefer a more polished spreadsheet format

## Importing Data

### What import is for

Use the **Import** page when you already have contact data in a CSV file and want to bring it into KLS in a controlled way.

### Import workflow

Recommended import steps:

- open **Import**
- choose a CSV file
- run the preview
- review valid rows, duplicates, and errors
- fix the file if needed
- commit the import only after the preview looks right

### Important import notes

- import currently supports CSV only
- the preview step checks the file before anything is written
- missing schools can be created during import
- duplicates are skipped instead of inserted again

## Settings

### What settings control

Use **Settings** to adjust how the app feels while you work.

Settings can help with:

- appearance
- table readability
- workflow defaults
- local troubleshooting preferences

### Appearance settings

These include:

- dark mode
- color profile
- lime-pattern background
- compact layout
- larger text
- reduced motion

Use these to make the app easier to read during long work sessions.

### Table and workflow settings

These options help control how records are displayed and how the app behaves day to day.

Examples include:

- striped table rows
- sticky headers
- showing inactive schools by default
- keeping school selections during refresh
- default batch scrape scope
- showing or hiding the startup directory warning

### Scraper settings

The settings panel also includes scraper-related options such as debug preferences. Treat these as helpful local preferences and troubleshooting aids. Some of them affect the interface more clearly than they affect backend scraping behavior.

## Troubleshooting

### The app opens slowly

Try this:

- give it a little extra time on launch
- close extra browser tabs or other heavy apps
- restart the app

### The browser did not open automatically

Try this:

- wait a few seconds
- check if the app is already running
- relaunch the packaged application

### A scrape returns weak or incomplete results

Try this:

- confirm the school website is correct
- use **Find Website** if the current site is missing or questionable
- run a single-school scrape instead of relying only on batch results
- use Full Review to keep useful partial contacts
- add a manual contact if you have verified information

The system removes many obvious junk records automatically, but you should still scan high-scoring results quickly before trusting them.

### Batch scrape looks stuck

Try this:

- check the status indicator in the batch panel
- move to another page and confirm the global batch banner is updating
- give slower school sites extra time
- cancel only if you are sure the current run should stop

If you cancel a batch job, the current in-progress school may be discarded so the app can stop cleanly.

### A school has no website or a bad website

Try this:

- use **Find Website**
- review the result before trusting it
- edit the school record manually if you know the correct site

If the lookup times out, try again later or enter the website manually.

### Import preview shows errors

Try this:

- review the CSV file for missing names or other bad values
- correct the file
- run preview again before committing

Do not skip the preview step. It is there to help you catch issues before anything is written.

### Export results do not look right

Try this:

- review the filters at the top of the Export page
- check whether inactive schools or schools without contacts are included
- confirm the preview matches what you expect before downloading

## Known Limitations

- scrape quality depends on what a school makes public on its website
- some schools no longer publish full staff directories
- a missing phone number does not always mean the contact is unusable
- website discovery is helpful, but it still needs human review
- some weak or unusual scrape results may still need manual cleanup even after automatic junk filtering
- batch scraping is faster than single-school review, but it may return more mixed-quality results
- exports are only as clean as the records currently saved in the system
- this release is designed for a single local operator, not for multi-user or shared-permission workflows
