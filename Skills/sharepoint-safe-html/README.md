# SharePoint Safe HTML

Creates single-file HTML artifacts that render reliably in SharePoint, OneDrive, Teams, File Viewer, and embedded iframe preview surfaces. The skill turns general requests for reports, dashboards, decks, one-pagers, and visual pages into sandbox-safe HTML with no external dependencies, plus an explicit exception for supported live-linked CSV/XLSX data files.

![preview](./assets/preview.png)

## What you get

- A single self-contained `.html` file designed for SharePoint and OneDrive preview surfaces
- Inline CSS, system fonts, responsive iframe-friendly layout, and semantic accessible HTML
- Optional live links to up to 10 SharePoint/OneDrive `.csv` or `.xlsx` files in the same folder as the HTML artifact so data-backed artifacts can update when source files change
- Defensive live-data rendering rules that prevent blank pages and errors when linked files are empty, renamed, or missing expected columns
- Live-only behavior for live-linked reports: no hardcoded backup rows, fallback datasets, cached snapshots, sample rows, or stale render data
- A deterministic render contract with input normalization, explicit empty states, visible error panels, and source checks for unresolved placeholders or leaked JavaScript values
- Guardrails against CDNs, runtime network calls, local file paths, external assets, secrets, and unsafe raw HTML
- A validation checklist for source scanning, responsive rendering, accessibility, and privacy review

## When to use

Ask Copilot:

- *"make this a SharePoint-safe HTML page"*
- *"build an HTML dashboard I can upload to SharePoint"*
- *"create a self-contained HTML report for OneDrive preview"*
- *"make an HTML dashboard that live-links to this Excel workbook"*
- *"turn this into an embeddable HTML artifact for Teams or File Viewer"*
- *"generate a visual one-pager with no external dependencies"*

## SharePoint Skill

| Solution | Author(s) |
| --- | --- |
| sharepoint-safe-html | Zach Rosenfield &#124; [GitHub](https://github.com/zrosenfield) &#124; [LinkedIn](https://www.linkedin.com/in/zrosenfield/) |

## Version history

| Version | Date | Comments |
| --- | --- | --- |
| 1.0 | June 2026 | Initial Release |

## Disclaimer

**THIS CODE IS PROVIDED _AS IS_ WITHOUT WARRANTY OF ANY KIND, EITHER EXPRESS OR IMPLIED, INCLUDING ANY IMPLIED WARRANTIES OF FITNESS FOR A PARTICULAR PURPOSE, MERCHANTABILITY, OR NON-INFRINGEMENT.**

<img src="https://m365-visitor-stats.azurewebsites.net/sharepoint-skills/skills/sharepoint-safe-html" />
