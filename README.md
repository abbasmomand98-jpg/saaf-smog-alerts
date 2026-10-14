# Saaf — Smog Alerts & Clean-Air Planner (UX Concept)

Every October–January, smog chokes Lahore, Karachi, Islamabad, Peshawar and other Pakistani cities — AQI crosses 300, schools shut, and families get no reliable answer to three simple questions: *is it safe to go out, which mask actually works, and how do I protect my home?*

**Saaf** is a mobile-first web app concept that answers all three: a city-wise AQI dashboard with a color-coded gauge, a "should you go outside?" planner that adapts to who's going (kids, elderly, asthma) and for what, live-style smog alerts, a 5-day forecast, an honest mask guide with PKR prices, and indoor clean-air tips.

## Features
- City selector (Lahore, Gujranwala, Faisalabad, Multan, Rawalpindi, Karachi, Peshawar, Islamabad) with realistic smog-season AQI data
- Hero AQI card with SVG gauge arc, band label, dominant pollutant and hotspot
- "Should you go outside?" recommender — profile + activity based verdicts (Go / Caution / Stay indoors)
- Smog alerts feed with severity chips and timestamps
- 5-day color-coded smog forecast
- Mask effectiveness guide with PKR prices and a per-day mask picker
- Indoor protection: purifier options (PKR) + practical DIY tips

## Tech
Pure HTML, CSS and JavaScript — no frameworks, single `index.html`.

## How it works
- All data lives in one JavaScript object (`CITIES`) — each city carries its AQI, band, dominant pollutant, hotspot, a 5-day forecast, and its alerts. Switching cities just re-renders from that object, no page reloads.
- The AQI gauge is a hand-drawn SVG arc: the filled portion and color are computed from the AQI value and its health band (Good → Hazardous).
- The "Should you go outside?" planner is a small rule engine: it combines the city's AQI band with who's going (child, elderly, asthma, healthy adult) and the activity type, then returns a verdict — Go, Caution, or Stay indoors — with a reason and the right mask for the day.
- Everything is rendered by small, single-purpose functions (`renderDashboard`, `renderAlerts`, `renderForecast`, `renderMaskGuide`), so the code is easy to follow top to bottom.

## What you can learn from this project
- **Design for a real, seasonal problem:** this concept is timed to Pakistan's October–January smog season and built around the three questions families actually ask — not around features.
- **Data-driven UI without a backend:** how to structure realistic sample data so a static page still feels alive and city-specific.
- **Rule-based recommendations:** turning expert guidance (AQI bands × vulnerable groups) into simple, explainable verdicts a non-technical user can trust.
- **SVG gauges and color systems:** drawing a semicircular gauge with stroke math, and mapping data ranges to a consistent color scale.
- **Accessible, mobile-first layout:** large tap targets, high-contrast bands, and plain-language labels that work for everyone, including elderly users.

Fork it, read the single `index.html`, and adapt the pattern to your own city's problem — load-shedding schedules, water supply timings, flood alerts, anything local and seasonal.

## Links
- Live demo: https://abbasmomand98-jpg.github.io/saaf-smog-alerts/
- Repo: https://github.com/abbasmomand98-jpg/saaf-smog-alerts

## Disclaimer
Concept demo — AQI figures are simulated for design purposes, not live data.
