# Skills

AI skills are instruction files that give a Copilot agent a focused capability. Each skill lives in its own folder and is installed by uploading that folder to the **Skills** library in SharePoint.

Some skills also include a `demo/` subfolder containing sample content you can use to try the skill end-to-end (e.g., [`library-cleanup/demo/`](./library-cleanup/demo/)). Each skill folder now contains an upload-ready inner package folder with the same name (for example, `file-classifier/file-classifier/`). Keep sample/demo material outside that inner package.

## Quick links

- **Browse skills:** [Libraries](#libraries) · [Operations](#operations) · [Styling](#styling) · [Writing](#writing)
- **Install:** [Installing a Skill](#installing-a-skill)
- **Contribute:** [✅ Pre-submission checklist](#pre-submission-checklist) · [Creating a Skill](#creating-a-skill) · [Required files](#required-files) · [File templates](#file-templates)

---

## Installing a Skill

Skills follow the [agentskills.io specification](https://agentskills.io/specification). The `Skills/` library in SharePoint is created automatically — install by uploading the skill folder into it.

1. Download the skill folder (e.g., `file-classifier/`)
2. In your SharePoint site, open the **Agent Assets** library
3. Navigate into the **Skills** folder (auto-created)
4. Open the matching inner package folder (e.g., `file-classifier/file-classifier/`) and upload that folder — the agent discovers it by the `name` field in `SKILL.md`

## Creating a Skill

A skill is a folder containing docs, samples, and an upload-ready inner package. The outer folder lives directly under `Skills/`, and the inner package folder must have the same name as the outer folder.

### Where it goes

**In this repo:** `Skills/<skill-name>/<skill-name>/SKILL.md`

**In SharePoint:** upload `Skills/<skill-name>/<skill-name>/` as the package folder. Keep `README.md`, `assets/`, and `demo/` in the outer folder for repo documentation and samples.

### Naming convention

- Folder name: **kebab-case** — lowercase, dash-separated (`organize-library`, not `OrganizeLibrary` or `organize_library`)
- The folder name must match the `name` field in `SKILL.md` exactly
- Be specific — avoid generic names like `tool`, `helper`, `processor`

### Required files

| File | Purpose |
|---|---|
| `<skill-name>/SKILL.md` | Skill instructions with `name` and `description` frontmatter (inside the upload-ready inner package) |
| `README.md` | Description, what you get, and contribution credits |
| `assets/sample.json` | Metadata for the PnP community samples gallery |
| `assets/preview.png` | Screenshot of the skill's output for the samples gallery (recommended 1280×720, 16:9, PNG) |

If your skill needs extra runtime files (for example, persona reference documents), keep those files beside `SKILL.md` inside the inner package folder.

### Optional — demo content

If your skill benefits from a hands-on demo, add a `demo/` subfolder. Include a `README.md` with setup steps and a `sample-files/` folder with the content. Keep demo content in the outer folder, not in the inner upload package.

---

## File templates

### `SKILL.md`

```markdown
---
name: summarize-page
description: Summarizes a SharePoint page in 3 bullet points.
  Use when the user asks for a quick summary of a page.
---

# Summarize Page

## Instructions

1. Read the full content of the specified page.
2. Identify the 3 most important points.
3. Return a bulleted summary, each bullet no longer than one sentence.
```

### `README.md`

```markdown
# Summarize Page

Short description of what the skill does and when to use it.

## What you get

- Bullet list of outputs and outcomes

## Contribution

| Property | Value |
|---|---|
| Author | Your Name |
| GitHub | [your-handle](https://github.com/your-handle) |
| First published | Month YYYY |
```

### `assets/sample.json`

```json
[
  {
    "name": "pnp-sharepoint-skills-summarize-page",
    "source": "pnp",
    "title": "Summarize Page",
    "shortDescription": "Summarizes a SharePoint page in 3 bullet points.",
    "url": "https://github.com/pnp/sharepoint-skills/tree/main/Skills/summarize-page",
    "longDescription": [
      "Longer description spanning one or more paragraphs.",
      "Each array entry is rendered as a separate paragraph in the gallery."
    ],
    "creationDateTime": "2026-05-07",
    "updateDateTime": "2026-05-07",
    "products": [
      "SharePoint",
      "Microsoft 365 Copilot"
    ],
    "metadata": [
      { "key": "SAMPLE-TYPE", "value": "SharePoint-AI-Skill" },
      { "key": "SKILL-CATEGORY", "value": "Document Management" }
    ],
    "thumbnails": [
      {
        "type": "image",
        "order": 100,
        "url": "https://github.com/pnp/sharepoint-skills/raw/main/Skills/summarize-page/assets/preview.png",
        "alt": "Summarize Page skill in action"
      }
    ],
    "authors": [
      {
        "gitHubAccount": "your-handle",
        "pictureUrl": "https://github.com/your-handle.png",
        "name": "Your Name"
      }
    ],
    "references": [
      {
        "name": "agentskills.io specification",
        "description": "The specification that SharePoint AI skills follow for installation and discovery.",
        "url": "https://agentskills.io/specification"
      }
    ]
  }
]
```

---

## Pre-submission checklist

Before opening your pull request, verify:

- [ ] Skill folder is directly under `Skills/` (`Skills/<skill-name>/`)
- [ ] Upload-ready inner package exists at `Skills/<skill-name>/<skill-name>/`
- [ ] Folder name uses kebab-case and matches the `name` field in `SKILL.md` exactly
- [ ] `SKILL.md` has `name` and `description` in the frontmatter and is in the inner package folder
- [ ] `README.md` follows the template (description, "What you get", Contribution table)
- [ ] `assets/sample.json` exists with the `url` and `thumbnails[0].url` pointing to your skill's actual path
- [ ] `assets/preview.png` exists and shows the skill's actual output (not a logo or placeholder)
- [ ] Skills work best when they are **focused** (one capability), **self-contained** (no external dependencies), and **discoverable** (clear `description` with trigger phrases)
