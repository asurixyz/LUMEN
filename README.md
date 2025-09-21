# Asian Economic Data

A lightweight, static website visualizing trade and investment trends across key maritime regions. Everything runs client-side using CSV files in this repo, parsed via CDN libraries and rendered with responsive charts.

## Live pages
- Home: `home.html`
- South China Sea: `scs.html`
- Bay of Bengal: `bob.html`
- East African Coast: `eac.html`
- Persian Gulf: `pg.html`

On GitHub Pages, your URLs will look like:
- `https://<your-username>.github.io/<your-repo>/home.html`
- `https://<your-username>.github.io/<your-repo>/scs.html` (and similarly for the others)

## What's inside

- Client-side only (no build, no backend).
- CSV parsing: Papa Parse (CDN).
- Charting: Plotly (CDN).
- Mobile-friendly layout, responsive charts.
- Small home button (🏠) in each page's top bar linking back to `home.html`.

### Data folders
- `South China Sea/`
- `Bay of Bengal/`
- `East African Coast/`
- `Persian Gulf/`

Each folder contains one or more CSVs used by its corresponding page.

## How to view locally

Modern browsers block CSV fetches from file://. Serve the folder over HTTP:

- Node (recommended):
```bash
npx serve .
```
Then open the printed localhost URL and navigate to `/home.html`.

- VS Code: Use the "Live Server" extension and open `home.html`.

## Deploying on GitHub Pages

1) Push this repo to GitHub.
2) In your repository, go to Settings → Pages.
3) Select your default branch and root as the source.
4) Save and wait ~1 minute.
5) Visit `https://<your-username>.github.io/<your-repo>/home.html`.

## Pages overview

- Home (`home.html`)
  - Intro to the datasets and how to read the charts.
  - Cards linking to each region page.

- South China Sea (`scs.html`)
  - Trade volume by country over time.
  - Investment breakdowns (e.g., oil & gas, military infrastructure, ports/BRI).
  - Energy consumption shares through the SCS.
  - Key players' trade with SCS countries.

- Bay of Bengal (`bob.html`)
  - Total trade volume (long- or wide-form CSV support).
  - Investment series across countries/sectors.

- East African Coast (`eac.html`)
  - Total trade volume with East African countries.
  - Investment series across countries/sectors.
  - Excludes "Source/Notes" columns from legends.

- Persian Gulf (`pg.html`)
  - Total trade volume in the Gulf.
  - Key players' trade with Gulf countries.
  - Excludes "Source/Notes" columns from legends.

## Data and assumptions

- CSVs are expected to have a `Year` column plus one or more numeric series.
- Column names are used directly as legend labels; updating headers updates the plots.
- Some pages auto-handle long-form vs wide-form data.
- Numeric strings like "$1,234" or "44%" are parsed to numbers.

## Adding or updating data

- Keep filenames and folder names exactly as referenced in each page (GitHub Pages is case-sensitive).
- To add a new series, add a new column to the CSV; it will appear as a new line in the chart.
- If you rename columns, legends will reflect the new names automatically.

## Troubleshooting

- Blank or "Error loading data": ensure you're serving over HTTP and the CSV paths exist.
- 404 on GitHub Pages: verify exact file and folder casing; paths in HTML must match repository paths.
- CSV header differences: if a chart doesn't show expected lines, confirm the header names and adjust the page's key mapping if needed.

## Acknowledgements

- Charts: Plotly (CDN)
- CSV parsing: Papa Parse (CDN)

If you'd like a combined "All Regions" page, a dark theme, or fixed color palettes for specific countries/categories across pages, open an issue or request and I'll extend the site.
