# Compass Digital Asset Library

A self-hosted digital asset management (DAM) page for Compass, built on GitHub Pages. It pulls live data from Airtable on every load — no manual updates needed when new assets are added.

## What it does

- Displays all assets from the Airtable Digital Asset Management base as visual preview cards
- Lets anyone filter by Use Case and Format, or search by name
- "Grab it" assets link directly to SharePoint for download
- "Request it" assets open a form that writes directly to the Airtable Requests table
- Fully dynamic: new assets added in Airtable appear automatically on next page load

## Files

| File | Purpose |
|------|---------|
| `index.html` | The entire app — HTML, CSS, and JavaScript in one file |

## Updating assets

All content is managed in Airtable. To add or update an asset:

1. Open the **Digital Asset Management** base in Airtable
2. Add or edit a record in the Assets table
3. That's it — the page picks up changes automatically on the next load

## Airtable structure

**Assets table** fields used:

| Field | Purpose |
|-------|---------|
| Name | Asset display name |
| Use Case | Multi-select tags shown on cards |
| Asset | Attachment — used for image preview thumbnails |
| Download Link | SharePoint URL for direct downloads |
| Format | File format badge (.PDF, .PNG, etc.) |
| Category | "Grab it" (download) or "Request it" |
| Last Updated | Date shown on card |

**Requests table** — populated when users submit the request form.

## API key note

The Airtable Personal Access Token is embedded in `index.html`. It is **read-only** and scoped to this base only. Anyone who views the page source can read it. If you rotate the token, update the `PAT` constant near the top of `index.html` and re-upload the file.

## Deployment

Hosted on GitHub Pages from the `main` branch, root folder. Any change pushed to `main` goes live within ~60 seconds.

To update the page: edit `index.html` directly in GitHub (click the file, then the pencil icon) and commit. No build process needed.
