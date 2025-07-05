# 🚗 Dynamic Pricing for Urban Parking Lots

### 📘 Capstone Project | Summer Analytics 2025  
**Hosted by:** Consulting & Analytics Club × Pathway  
**Submitted by:** Kaushal Jha  

---

## 📌 Project Overview

In cities, static parking prices lead to either underutilization or over-congestion.  
This project implements a real-time, ML-based pricing system for 14 urban parking lots using Python, Pathway, and Bokeh.

### 🎯 Objective:
Maximize parking lot utilization by:
- Dynamically adjusting prices based on demand
- Considering real-time conditions and competition

### 🛠 Tools Used:
- Python
- Pandas, NumPy
- Pathway (for real-time streaming)
- Bokeh & Panel (for live visualizations)

---

## 📁 Project Structure

### 📌 Section 1: Data Loading + EDA
- Load `dataset.csv`
- Explore key features: `Occupancy`, `Capacity`, `QueueLength`, `VehicleType`, etc.
- Merge `Date` + `Time` into unified `Timestamp` for time-based streaming
- Visualize trends (optional)

---

### 📌 Section 2: Model 1 — Linear Occupancy-Based Pricing

**Formula:**


- Simple linear increase based on occupancy
- Bounded between $5 and $20
- Used as a baseline pricing model

---

### 📌 Section 3: Model 2 — Demand-Based Pricing

**Features Used:**
- Occupancy Rate
- Queue Length
- Traffic Level
- Special Day Flag
- Vehicle Type

**Formula:**


- Demand is normalized before applying
- Integrated into real-time stream via `pricing_logic()`

---

### 📌 Section 4: Model 3 — Competitive Pricing

- Uses **Haversine formula** to calculate distance between parking lots
- Identifies competitors within 1 km
- Adjusts price based on:
  - If full + competitors are cheaper → decrease or reroute
  - If competitors are expensive → increase price

---

### 📌 Section 5: Real-Time Visualization (Bokeh + Panel)

- `price_plotter()` function renders live Bokeh plot
- `delta_window.plot(...)` connects Pathway stream to Bokeh
- `pn.Column(viz).servable()` makes the dashboard interactive
- Optional: deploy as a lightweight web app or use screenshots

---

## 📊 Outputs

- Google Colab notebook with all models (Model 1 → Model 3)
- Real-time simulation using Pathway
- Live visualization using Bokeh
- PDF report included in repository

---

## ✅ How to Run

1. Clone the repo
2. Open the notebook in Google Colab
3. Install dependencies:
   ```bash
   !pip install panel bokeh pathway
