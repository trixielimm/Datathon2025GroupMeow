# Datathon 2025 Group Meow Macquarie University – Ski Holiday Forecasting

This repository contains our work for the **Datathon 2025**, where the challenge is to plan the **ultimate ski holiday for 2026**.  
Using visitation, climate, and cost datasets, we explored multiple forecasting and scoring methods to identify the best weeks and resorts for a winter getaway in Australia.

---

## 📂 Repository Structure

### 1. Data Files
- **2025 Allianz Datathon Dataset.xlsx**  
  Raw dataset provided by the competition. Contains:
  - **Sheet 1** – README/info sheet  
  - **Sheet 2** – Visitation data (Year, Week, and visitors for each resort: Mt. Baw Baw, Mt. Stirling, Mt. Hotham, Falls Creek, Mt. Buller, Selwyn, Thredbo, Perisher, Charlotte Pass)  
  - **Sheet 3** – Climate data (station number, Year, Month, Day, max/min temperatures, rainfall)

- **2025 Allianz Datathon Dataset Filtered.xlsx**  
  Cleaned version of the dataset used for modeling:
  - Removed outlier years (2020–2021, COVID-19)  
  - Adjusted column headers for consistency  
  - Ready-to-use for analysis in notebooks

- **TripScore Tables (CSV/XLSX)**  
  Derived tables combining weather (bluebird days), capacity, cost, and terrain difficulty into a **TripScore** and final rankings.  
  - Columns include: `BluebirdDays`, `CapacityPct`, `TotalCost`, normalized scores, `TerrainLevel`, overall `TripScore`, and ranking fields.

---

### 2. Notebooks & Scripts
- **Datathon.ipynb**  
  Main analysis notebook with step-by-step experiments:
  - **Data Cleaning & Exploration** – import visitation & climate data, handle missing values, drop 2020–2021.  
  - **Forecasting Models**  
    - Exponential Smoothing (Holt-Winters)  
    - RNN / LSTM models (TensorFlow + Darts) with recursive forecasts and MC dropout for uncertainty  
  - **Visualizations** – historical vs forecasted visitors, 95% prediction bands, seasonal patterns  
  - **TripScore Ranking** – combining forecasts with price and weather data to identify top trips  

- **Supporting Code Snippets**  
  - `upload_to_colab.py` – helper for uploading Excel datasets into Colab  
  - Utility functions for converting Year/Week into weekly timelines, scaling, and generating forecast tables.
---

## ⚙️ How to Run
1. Clone the repository:
   ```bash
   git clone https://github.com/<your-team>/<your-repo>.git
   cd <your-repo>
