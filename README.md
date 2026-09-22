# Rating Dashboard — Vercel

## 1. Connect Google Sheet
Open `script.js` and replace:

const SHEET_CSV_URL = "PASTE_YOUR_GOOGLE_SHEET_CSV_URL_HERE";

with your published Google Sheet CSV URL.

### Recommended Google Sheet setup
Google Sheets -> File -> Share -> Publish to web -> select the data tab -> CSV -> Publish.

The dashboard expects these columns (column names can be in any order):
- Board Name
- Subject Name
- rating
- rating_date_updated
- Week Name
- Month Name
- studentid

## 2. Run locally
You can use VS Code + Live Server, or:
npx serve .

## 3. Deploy to Vercel
Option A:
- Push these 3 files to GitHub.
- Vercel -> Add New -> Project -> Import the GitHub repo.
- Framework Preset: Other
- Deploy.

Option B:
- Install Vercel CLI.
- Run `vercel` in this folder.

## Dashboard behavior
- Weekly view automatically shows only the latest 5 available week numbers in the filtered data.
- Weekly table Grand Total columns (Board, Subject and overall) use ALL filtered weeks, while the visible week columns remain limited to the latest 5 weeks.
- Monthly view shows every available month in the filtered data.
- Board rows expand/collapse to show Subject Name rows.
- Rating < 4.3 = red.
- Rating > 4.3 = green.
- Rating = 4.3 = amber.
- Board, Subject and rating-date filters apply to both tables.
- Each table has an Export PNG button.
- Grand Total is calculated from underlying rating records, not an average of displayed subject averages.
