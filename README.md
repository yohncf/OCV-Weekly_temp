# OCV-Weekly

**OL Agent OCV Dashboard** — weekly customer-feedback digests for the Outlook AI Agent.

Live site (once GitHub Pages is enabled): https://gim-home.github.io/OCV-Weekly/

## Repo layout

```
index.html          Landing page (lists all weekly reports)
reports.json        Manifest of published reports (index.html reads this)
reports/
  YYYY-MM-DD.html   One self-contained weekly report per week
.nojekyll           Disables Jekyll (we serve raw HTML)
```

## Publishing a new weekly report

1. Generate the report with `publish-ocv-report` in the `ocv-extraction` workspace.
2. Copy the resulting HTML into `reports/<week-of-monday>.html`.
3. Add a new entry to the top of the `reports` array in `reports.json`:

   ```json
   {
     "week_of": "2026-05-25",
     "label": "Week of May 25, 2026",
     "range": "May 19 - May 25, 2026",
     "file": "reports/2026-05-25.html",
     "negatives": 0,
     "subtopics": 0,
     "highlights": "One-line summary that shows on the landing card.",
     "published": "2026-05-28"
   }
   ```
4. Commit and push.

## Enabling GitHub Pages

Settings -> Pages -> Build and deployment -> Source: **Deploy from a branch** -> Branch: **main** / **(root)**.
