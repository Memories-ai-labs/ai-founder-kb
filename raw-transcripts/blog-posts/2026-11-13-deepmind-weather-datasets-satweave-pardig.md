# Title: Opening the datasets behind our AI weather models
# URL: https://deepmind.google/blog/opening-the-datasets-behind-our-ai-weather-models/
# Date: 2026-11-13
# Source: Google DeepMind Blog

## Opening the datasets behind our AI weather models

Published: November 13, 2026
Team: Google DeepMind WeatherNext

### Summary

Google DeepMind's WeatherNext team is releasing two datasets — SatWeave and PARDIG — to help researchers build weather, hydrology, and climate applications. Both support WeatherNext 3.

### Key Points

**SatWeave:**
- Global mosaic of geostationary satellite imagery
- 17 channels: visible, water vapor, and infrared
- Hourly updates
- Includes live feed + archive spanning over a decade
- Available on Google Cloud Storage

**PARDIG (Precipitation AI Reanalysis: Densely Inferred GPM):**
- AI-based global precipitation dataset
- ~10 km resolution at 15-minute intervals
- ~5 hours latency
- Improves hourly light-to-moderate precipitation detection by >30% over NASA's IMERG-Final
- Historical data: 1999–2026
- Available on Google Cloud Storage and Google Earth Engine

### Significance

Open-releasing high-quality satellite and precipitation datasets removes a major barrier for weather AI research. PARDIG's 30%+ improvement over NASA IMERG-Final for light/moderate precipitation is significant for agriculture, disaster response, and climate research applications. The decade+ archive in SatWeave enables historical model training at scale.
