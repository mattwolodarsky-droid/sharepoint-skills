# Organize Library — Demo Content

Demo content for the [organize-library](../) skill. Use these sample files to set up an end-to-end demo of the skill in SharePoint.

## What's included

The `sample-files/` folder contains 12 documents — the same set used by the `file-classifier` demo, since organize-library orchestrates that skill:

- **5 Contracts** — Supply Agreement, SLA, Consulting Services Agreement, NDA, and a commercial office Lease
- **4 Invoices** — including a Credit Memo (negative amount)
- **3 Purchase Orders** — raw materials, cloud services, and fleet vehicles

This mix lets the skill demonstrate per-content-type views, color-coded classification pills for all three types, status pills with different colors, data bars across a wide range of values, and overdue date highlighting on past expiration/due dates.

## Setup

1. Create or open a SharePoint document library.
2. Upload all files from `sample-files/` into the library.
3. Install both skills into your SharePoint Skills library:
   - [organize-library](../) — the orchestrator
   - [file-classifier](../../file-classifier/) — used by organize-library for classification
4. Ensure your site has a `SHAREPOINT.md` brand reference file (organize-library reads this for colors and formatting).
5. From a Copilot agent, ask: *"Organize this document library."*

## What to expect

The agent will run the full end-to-end workflow:
- Color folders using brand colors
- Classify files using the file-classifier skill
- Format the FileClassification column with color-coded pills
- Update the default view with grouped headers
- Format date columns with overdue highlighting, status columns with icon pills, number columns with data bars
- Create per-content-type views (Contracts, Invoices, Purchase Orders)
- Create notification rules for overdue items, alerting a reviewer of your choice

You'll get visible progress at each step rather than a long silent period.
