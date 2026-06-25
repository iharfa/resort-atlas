# Resort Atlas · Maldives Resort Spatial Browser

Static Leaflet app for mapping Maldives resort records against OneMap island geometry.

## What changed in this build

- Satellite basemap using Esri World Imagery.
- OneMap island outlines fetched live from the public ArcGIS layer.
- Source status and verified status are kept separately.
- Oaga Art Resort is corrected from `Not Operating` to `Operating` with evidence links.
- Status corrections are highlighted on the map and exported as CSV.

## Files

- `index.html` - full static app
- `data/operating_resorts.json` - operating resort records with verification fields
- `data/under_development_resorts.json` - development records with verification placeholders
- `data/resorts_combined_for_onemap_join.csv` - combined dataset for GIS joins
- `data/status_verification.csv` - status corrections and evidence links

## Run locally

```bash
python -m http.server 8000
```

Open `http://localhost:8000`.

## Deploy to Vercel

Use this as a static site.

- Framework preset: Other
- Build command: blank
- Output directory: blank

## Verification workflow

For each resort or development record, keep the source status unchanged, then add:

- `verified_status`
- `status_verification`
- `status_confidence`
- `status_discrepancy`
- `verification_sources`

Use at least two independent sources for corrections where possible. Preferred order:

1. Official resort website or booking engine
2. Booking.com listing with live reviews or availability context
3. Agoda listing with live reviews or availability context
4. Recent trade news or press release
5. Resort social channels as supporting evidence only
