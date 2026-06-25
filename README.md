# Resort Atlas

Map-first browser for Maldives resort information.

It shows operating resort records from the CSV, under-development resort records from the Ministry of Tourism PDF, explicit coordinate sites from the PDF, and OneMap island outlines fetched from the public ArcGIS layer.

## Run locally

```bash
python -m http.server 8000
```

Open http://localhost:8000

## Deploy to Vercel

1. Create a new GitHub repository.
2. Upload the full contents of this folder.
3. Import the repository in Vercel.
4. Choose Other as the framework preset.
5. Leave build command empty.
6. Leave output directory empty.
7. Deploy.

## Files

- `index.html` contains the full static app.
- `data/operating_resorts.json` powers operating resort records.
- `data/under_development_resorts.json` powers development records.
- `data/resorts_combined_for_onemap_join.csv` is the main joining table.
- `data/under_development_explicit_coordinates.geojson` contains coordinate sites extracted from the PDF.

## Data notes

The app matches resorts to OneMap islands in this order:

1. Atoll and island name exact match.
2. Unique island name match.
3. Fuzzy match inside the same atoll.
4. Manual review queue when no confident match exists.
