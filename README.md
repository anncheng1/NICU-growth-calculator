# NICU Growth Chart

**Hospital Miri NICU · Department of Paediatrics & Neonatology, Sarawak, Malaysia**

An offline-capable growth chart app that moves automatically from the **Fenton 2025 preterm chart** (to 50 weeks CGA) to the **WHO Child Growth Standards** (0–5 years), for boys and girls. Designed to be added to the iPhone home screen.

## Features

- **Auto chart selection** — Fenton 2025 while CGA ≤ 50 weeks; then WHO by corrected age until 2 years, and by actual (chronological) age from 2 to 5 years
- **Age display** — CGA, corrected age, chronological age and day of life
- **Centile and z-score** (LMS method) for weight, length/height and head circumference, with a colour band (Below P3 · P3–P10 · P10–P90 · P90–P97 · Above P97)
- **Growth chart** — plotted on the same P3 / P10 / P50 / P90 / P97 curves as the printed Fenton 2025 chart (P3/P97 dotted, P10/P90 dashed, P50 solid); tap a point for details
- **Multiple patients**, serial measurements, back up / restore (JSON)
- **PDF report (A4)**, chart image (PNG) and print
- Weight in **kg or grams** (values above 30 are read as grams)
- iPhone-friendly, dark mode, **works offline**

## Install on iPhone

1. Open the GitHub Pages link in **Safari**
2. Tap **Share → Add to Home Screen**

## Files

```
index.html             The whole app (reference LMS data, logic, PDF generator)
manifest.json          Home-screen / PWA settings
sw.js                  Offline cache
icon-180.png           iPhone home-screen icon (also used as the header and PDF logo)
icon-192.png, icon-512.png, icon-maskable-512.png, icon-32.png
README.md
```

## Method notes

- **Fenton 2025.** The authors' LMS table is not published. The P3/P10/P50/P90/P97 curves were digitised from the official 2025 boys' and girls' charts (600 dpi PDFs from fentongrowth.ca) and fitted with daily LMS parameters. Agreement with the printed curves: median ≈ 7 g for weight and ≈ 0.03 cm for length and head circumference (95th percentile ≤ 15 g / ≤ 0.08 cm). Weight and head circumference start at 22⁴⁄₇ weeks, length at 23⁴⁄₇ weeks, as on the printed charts.
- **Join to WHO.** The charts state that the curves equal the WHO standard at 50 weeks. The printed post-term curves run about 0.1–0.15 z below WHO in weeks 46–49, so the app follows the printed chart to 49 weeks and blends smoothly into WHO between 49 and 50 weeks (no step at the switch).
- **WHO 2006.** Official WHO LMS tables (daily 0–1 year, weekly to 5 years; interpolation error < 0.002 z). Length (recumbent) to 2 years, standing height from 2 years. Weight z-scores beyond ±3 use WHO's restricted method. Checked against the WHO weight-for-age 2–5 year z-score charts: within 0.013 z.
- **Age.** Corrected age = CGA − 40 weeks, used until chronological age 2 years; actual age after that.
- Z-scores may differ slightly from the official Fenton calculator; check borderline values at fentongrowth.ca. For clinical reference only — verify against printed growth charts.
- Patient data are stored only on the device. Back up regularly.

## References

- Fenton TR, Elmrayed S, Alshaikh BN, et al. Fenton third-generation growth charts of preterm infants without abnormal fetal growth. *Paediatr Perinat Epidemiol* 2025;39:543–555.
- WHO Multicentre Growth Reference Study Group. WHO Child Growth Standards, 2006.
