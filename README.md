# OPUS Connecticut Emissions Testing Stations Map

Interactive map showing 669 emissions testing stations across Connecticut, organized into 7 categories.

## Map Colors

- **Green** — Current Stations (active, accepting inspections)
- **Yellow** — Waiting List (approved but not yet operational)
- **Black** — Out of Program (inactive, no longer participating)
- **Pink** — Schools (educational institutions)
- **Gray** — Referrals (referred but status pending)
- **Dark Blue** — VIN Only (accepts VIN-specific inspections only)
- **Light Blue** — Fleet (handles fleet vehicle inspections)

## How to Use the Map

1. **Open the map** in your browser at `https://yourusername.github.io/opusctmap/`
2. **View stations** — Each colored pin is a testing station
3. **Click a pin** — Hover or click to see station details:
   - Station name
   - Address, city, ZIP
   - Type
   - Phone number
   - County
   - Email
4. **Watch the status** — Geocoding takes ~15-20 minutes on first load. Pins appear as they load.

## Monthly Updates

### Step 1: Export New CSVs from Google Sheets

1. Open your OPUS Connecticut Google Sheets
2. For each of these 7 sheets, export as CSV:
   - CURRENT_STATIONS
   - WAITING_LIST
   - OUT_of_PROGRAM
   - SCHOOLS
   - REFERRALS
   - VIN_ONLY
   - FLEET
3. Name each file exactly as shown above

### Step 2: Update GitHub

1. **Open GitHub Desktop**
2. **Navigate to your `opusctmap` folder**
3. **Replace the 7 CSV files in the `data/` folder** with the new exports
4. **GitHub Desktop shows "Changes"**
5. **Bottom left: Type** `Update station data - [Month/Year]`
6. **Click "Commit to main"**
7. **Click "Push origin"**

### Step 3: Verify

1. **Go to your map URL** in a browser
2. **Hard refresh** (Ctrl+Shift+R on Windows, Cmd+Shift+R on Mac)
3. **Wait for geocoding** to complete (~15-20 minutes)

## Troubleshooting

### Pins aren't loading
- **Check the browser console** (F12 → Console tab)
- **Make sure CSV files are in the `data/` folder** — map looks there
- **Check file names** — must match exactly (case-sensitive)
- **Wait longer** — geocoding takes time

### Map is blank
- **Check internet connection** — OpenStreetMap tiles need to load
- **Clear browser cache** — Hard refresh (Ctrl+Shift+R)
- **Check GitHub Pages is enabled** — Settings → Pages → Source = "main"

### CSV file names are wrong
- **Must be named exactly:**
  ```
  CURRENT_STATIONS_-_OPUSMAP_CURRENTSTATIONS.csv
  WAITING_LIST_-_OPUSMAP_WAITING_LIST.csv
  OUT_of_PROGRAM_-_OPUSMAP_OUTofPROGRAM.csv
  SCHOOLS_-_OPUSMAP_SCHOOLS.csv
  REFERRALS_-_OPUSMAP_REFERRALS.csv
  VIN_ONLY_-_OPUSMAP_VINONLY.csv
  FLEET_-_OPUSMAP_FLEET.csv
  ```

## Folder Structure

```
opusctmap/
├── index.html (the map)
└── data/
    ├── CURRENT_STATIONS_-_OPUSMAP_CURRENTSTATIONS.csv
    ├── WAITING_LIST_-_OPUSMAP_WAITING_LIST.csv
    ├── OUT_of_PROGRAM_-_OPUSMAP_OUTofPROGRAM.csv
    ├── SCHOOLS_-_OPUSMAP_SCHOOLS.csv
    ├── REFERRALS_-_OPUSMAP_REFERRALS.csv
    ├── VIN_ONLY_-_OPUSMAP_VINONLY.csv
    └── FLEET_-_OPUSMAP_FLEET.csv
```

## Technical Details

- **Map:** Leaflet.js + OpenStreetMap tiles
- **Geocoding:** Nominatim API (1.4 sec per station)
- **Total stations:** ~669 across all categories
- **Browser compatibility:** All modern browsers (Chrome, Firefox, Safari, Edge)

## Questions?

If the map breaks or you need to troubleshoot:
- Check file names and paths
- Verify all 7 CSV files are in the `data/` folder
- Make sure the folder structure is correct
- Hard refresh your browser

## Next Person Taking Over

This README is for you. The map updates monthly with new CSV data. Keep the folder structure, replace the CSV files, push to GitHub. That's it. If you have questions, check the troubleshooting section above.
