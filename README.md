# NICU Growth Chart

**Hospital Miri NICU · Department of Paediatrics & Neonatology, Sarawak, Malaysia**

An offline-capable growth chart app that moves automatically from the **Fenton 2025 preterm chart** (22–50 weeks CGA) to the **WHO Child Growth Standards** (0–5 years by corrected age), for boys and girls. Designed to be added to the iPhone home screen.

## Features

- **Auto chart selection** — Fenton 2025 while CGA ≤ 50 weeks, WHO 0–5 y thereafter (by corrected age)
- **Age display** — CGA, corrected age, chronological age and day of life
- **Centile and z-score** for weight, length/height and head circumference, with a colour band (Below P3 · P3–P10 · P10–P90 · P90–P97 · Above P97)
- **Growth record** — save measurements by date; they are kept on the device until "New patient" is tapped
- **Growth chart** — weight, length and HC plotted on the P3/P15/P50/P85/P97 curves; tap a point for details
- **PDF report (A4, 2+ pages)** — patient details, latest centiles, all three charts and the full growth record. Generated on the device, no internet needed. On iPhone use *Share / Save to Files*, AirDrop, WhatsApp or Print
- **Chart image (PNG)** and **Print**
- Weight can be typed in **kg or grams** (values above 30 are read as grams)
- iPhone-friendly: large touch targets, no zoom on input, numeric keypads, bottom action bar, safe-area aware, dark mode
- Works offline after first visit (service worker)

## Install on iPhone

1. Open the GitHub Pages link in **Safari**
2. Tap **Share → Add to Home Screen**
3. The *Growth Chart* icon opens the app full-screen

## Files

```
index.html             The whole app (data tables, logic, PDF generator)
manifest.json          Home-screen / PWA settings
sw.js                  Offline cache
icon-180.png           iPhone home-screen icon
icon-192.png, icon-512.png, icon-maskable-512.png, icon-32.png
README.md
```

Upload all files to the same folder of the GitHub repository, then enable **Settings → Pages** (branch `main`, folder `/root`).

## Method notes

- Corrected age = CGA − 40 weeks. Reference rows are interpolated between weeks (Fenton) and months (WHO).
- Centiles and z-scores are estimated by interpolating between the published P3/P15/P50/P85/P97 values; beyond P3 or P97 they are extrapolated and should be read as approximate.
- The patient name / RN field is printed on the report but never stored. Sex, DOB, GA and measurements are stored only in the browser on this device.
- For clinical reference only — verify against printed growth charts.

## References

- Fenton TR et al. Third-generation preterm growth chart, 2025 (fentongrowth.ca).
- WHO Multicentre Growth Reference Study Group. WHO Child Growth Standards. *Acta Paediatrica* 2006; Suppl 450.
