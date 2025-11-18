# 🌎 ClimateEye: Air Quality & Forecast System

**ClimateEye** is a web application providing real-time Air Quality Index (AQI) monitoring and forecasting, blending ground sensor data with simulated satellite readings for enhanced accuracy.

## 💻 Tech Stack & Libraries

| Component | Technology | Role |
| :--- | :--- | :--- |
| **Backend** | PHP (`api.php`) | Handles server-side Geocoding, API proxy calls (OpenWeatherMap), and AQI calculation logic. |
| **Frontend** | HTML, CSS, JavaScript | Interactive user interface and dynamic data rendering. |
| **Visualization**| Leaflet.js | Renders the interactive map for global location search and visualization. |
| **Charting** | Chart.js | Displays 7-day daily and 48-hour hourly AQI forecast trends. |

---

## ✨ Core Features

| Module | Description | Key Components |
| :--- | :--- | :--- |
| **Interactive Map View** | Pinpoint any location globally to instantly fetch current air quality metrics. | `index.php`, `script.js` |
| **Current AQI Metrics** | Displays the overall AQI score, along with fused concentrations for key pollutants ($\text{PM}_{2.5}$, $\text{O}_{3}$, $\text{NO}_2$). | `api.php` |
| **AQI Forecast** | Visualizes predicted AQI trends across both a **7-day daily summary** and a **48-hour hourly breakdown**. | `forecast.php`, `forecast.js` |
| **Health Guidance** | Provides actionable health recommendations based on the current AQI risk level. | 

[Image of the Air Quality Index (AQI) scale and corresponding health implications]
 |

---

## 🔬 Data Sources & Methodology

### API Integration
Data is primarily sourced from the **OpenWeatherMap Air Pollution API** to retrieve live concentrations of primary pollutants.

### Data Fusion Model
The system uses a simulated data fusion process to enhance prediction reliability:

1.  **Ground Data:** Direct reading from the OpenWeatherMap API (simulating ground sensors).
2.  **Satellite Data:** A randomized fluctuation model simulates readings from a **TEMPO Satellite** (Tropospheric Emissions: Monitoring of Pollution).
3.  **Fused Output:** The final AQI is derived from a weighted blend of the Ground Data (70%) and the Simulated Satellite Data (30%).

### AQI Calculation
The final AQI score is calculated based on the maximum AQI component between **$\text{PM}_{2.5}$** and **$\text{O}_{3}$** concentrations, following standardized EPA breakpoints.

---

## 🚀 Setup & API Configuration

1.  **Obtain API Key:** Register with **OpenWeatherMap** to get your API key.
2.  **Configure `api.php`:** Open `api.php` and replace the placeholder value with your actual key:

    ```php
    // --- CONFIGURATION ---
    $apiKey = "ddc33827ca40c6fedfbe8fe5fe867d76"; // <-- REPLACE THIS WITH YOUR KEY
    ```

3.  **Deployment:** Deploy the entire directory to a PHP-enabled web server (e.g., Apache, Nginx).
4.  **Access:** Navigate to `index.php` to begin using the map and forecast tools.
```eof
