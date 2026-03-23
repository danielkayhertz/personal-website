# Personal Website

## Project overview
A minimal personal website for a Chicago housing policy professional. Four pages: homepage, housing policy guide, art gallery, zoning data.

## File structure
```
Personal Website/
├── index.html          # Homepage
├── style.css           # Homepage styles
├── housing.html        # Housing policy guide
├── housing.css         # Housing guide styles
├── art.html            # Art collection
├── art.css             # Art page styles
├── Art/                # 57 images (.jfif + .png), named by artist
├── zoning.html         # Zoning data explorer
├── zoning.css          # Zoning page styles
├── zoning-data.csv     # Downloadable zoning dataset
├── CLAUDE.md
├── Housing in Chicago.docx   # Source document for housing.html
├── Chicago Zoning History.zip
├── ami-limits-table-2025.png
├── hud-maximum-monthly-rents-by-ami-table.png
└── blank-spacer.png
```

## Design
- **Background**: `#f4ecd8` (pale warm cream) — both pages
- **Homepage font**: Courier Prime (body), Big Shoulders Display (available but unused)
- **Housing guide font**: IBM Plex Serif (body), Big Shoulders Display (page title)
- Both fonts loaded via Google Fonts `<link>` in `<head>`

### Homepage (`index.html` + `style.css`)
- No header, no nav — starts directly with bio text
- Single centered column, max-width 600px
- Each paragraph has its own color (nth-child), cycling blues and browns
- Links inherit paragraph color, underlined
- No JavaScript

### Housing guide (`housing.html` + `housing.css`)
- Full text of "Working* in Housing Policy in Chicago" — no content omitted
- Sticky sidebar nav (fixed position, slides in from left) — **collapsed by default**
- "Contents" toggle button (fixed, top-left); closes automatically on link click
- Sidebar fills left margin space without shifting main content (main is centered independently via `margin: 0 auto`)
- Main content max-width 740px, centered
- All ~200 hyperlinks from the source .docx are embedded
- Both AMI images included in the housing continuum section
- "Under Construction" section removed
- PDF links styled as small `[PDF]` inline links via `.pdf-link` class

### Art page (`art.html` + `art.css`)
- 57 images, 34 artist sections, sorted alphabetically by display name (e.g. "de Chirico" sorts under D)
- Layout: horizontal scrolling shelf per artist, uniform 220px thumbnail height, natural width
- Click → lightbox (full-screen, keyboard accessible: ESC closes, Tab trapped, focus returns to trigger)
- JS data array in `art.html` defines all artists/images/captions — edit this to add images
- Captions sourced from filenames: anything after ` - ` is shown as italic caption below thumbnail
- Images in `Art/` subfolder; paths are `Art/filename`
- `.jfif` files: verify in Firefox (rename to `.jpg` if any fail to render — content is identical)

### Zoning page (`zoning.html` + `zoning.css`)
- Two-tab layout: Explore (data table) and Sources (historic document links)
- Explore tab: era filter buttons (1923/1942/1957/2004), one era at a time, 1923 default
- Table: horizontal scroll with sticky first two columns (Use District, Density District)
- CSV download button generates RFC 4180-compliant file from JS data array
- Sources tab: 6 source cards with external links (HathiTrust, PDF); 1971 marked unavailable
- Font: Courier Prime (body), Big Shoulders Display (headings)
- WAI-ARIA tab pattern with keyboard navigation
- JS data array in `zoning.html` defines all 62 rows — edit this to update data
- `zoning-data.csv` is a pre-built downloadable copy of the same data

## Aesthetic reference
1980s Chicago postmodern — Helmut Jahn's Thompson Center geometry, Roger Brown's flat graphic sensibility. Bare-bones HTML + CSS; avoid over-engineering.
