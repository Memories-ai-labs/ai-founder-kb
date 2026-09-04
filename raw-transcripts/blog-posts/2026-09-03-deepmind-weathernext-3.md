# Introducing WeatherNext 3, our most advanced and accurate global weather AI model
# URL: https://blog.google/innovation-and-ai/models-and-research/google-deepmind/introducing-weathernext-3/
# Date: 2026-09-03
# Source: Google DeepMind Blog

Google DeepMind and Google Research introduced WeatherNext 3, the most advanced and accurate global weather model to date. The system represents a significant advancement in AI-powered weather forecasting through enhanced resolution, real-time data integration, and improved prediction capabilities.

## Key Features

**Resolution and Frequency**

The model generates hourly forecasts at multiple spatial resolutions: 5 kilometers for surface variables like temperature, 10 kilometers for other surface data, and 25 kilometers for atmospheric variables. This is approximately five times greater detail than WeatherNext 2.

**Data Integration**

Rather than relying solely on traditional numerical weather prediction models, WeatherNext 3 ingests live, global geostationary satellite data, enabling hourly forecast updates grounded in current observations. The system also trains directly on sparse weather station data to capture regional topographic variations.

**Precipitation Forecasting**

The model shows substantial improvements in rain and snow prediction accuracy, training on NASA's satellite-based precipitation data and Google's precipitation reanalysis. Independent evaluations indicate improvements up to 60% against certain precipitation benchmarks.

**Clean Energy Variables**

WeatherNext 3 specifically forecasts 100-meter wind speeds for wind turbine assessment and provides cloud cover and solar radiation predictions for solar energy planning.

## Platform Integration

The model powers weather information across Google Search, Gemini, Maps, Google Maps Platform Weather API, and Google Earth Engine. Developers can access data through BigQuery, Earth Engine, or direct cloud storage downloads.
