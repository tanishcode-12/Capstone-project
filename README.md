## 📘 README.md

```markdown
# 🚗 Dynamic Pricing for Urban Parking Lots

This project simulates a real-time, intelligent pricing engine for urban parking spaces using historical and streaming data. It adjusts parking prices dynamically based on demand, traffic conditions, queue lengths, special events, and competition between nearby lots.

Developed as part of the **Summer Analytics 2025** capstone challenge hosted by the **Consulting & Analytics Club × Pathway**.

---

## 📊 Project Overview

Urban parking spaces are limited and often mispriced due to static pricing models. This project introduces a **data-driven dynamic pricing system** that reacts to real-time features to improve utilization and efficiency.

---

## 🔍 Features

- ⏱️ Real-time simulation of 14 parking lots over 73 days
- 📈 Three dynamic pricing models:
  1. **Baseline Linear Model** – Increases price based on occupancy
  2. **Demand-Based Model** – Uses a weighted demand function
  3. **Competitive Model (Optional)** – Adjusts price based on nearby lots' pricing
- 📡 Live data simulation using **Pathway**
- 🧠 Models implemented from scratch using **NumPy** and **Pandas**
- 📉 Visualizations using **Bokeh** and **Plotly**

---

## 📁 Dataset

- **Records:** 18,000+ (sampled every 30 mins between 8:00 AM – 4:30 PM)
- **Fields Include:**
  - `Latitude`, `Longitude`, `Capacity`, `Occupancy`
  - `VehicleType`, `TrafficConditionNearby`, `QueueLength`
  - `IsSpecialDay`, `Datetime`

---

## 🧠 Model Summary

### 1️⃣ Baseline Linear Model
Price increases linearly with occupancy:

```

Price\_t+1 = Price\_t + α \* (Occupancy / Capacity)

```

---

### 2️⃣ Demand-Based Model
Price adjusts based on calculated demand:

```

Demand = α\*(Occupancy/Capacity) + β*QueueLength − γ*Traffic + δ*IsSpecialDay + ε*VehicleTypeWeight
Price = BasePrice \* (1 + λ \* NormalizedDemand)

````

---

### 3️⃣ Competitive Model (Optional)
- Uses geospatial proximity to simulate nearby lot competition
- Price decreases or reroutes vehicles if nearby lots are cheaper

---

## ⚙️ Tech Stack

| Component         | Technology           |
|------------------|----------------------|
| Data Processing   | Python, Pandas, NumPy |
| Real-Time Engine  | Pathway              |
| Visualization     | Bokeh, Plotly        |
| Geo Calculations  | Geopy                |
| Deployment        | Google Colab / Jupyter Notebook |

---

## 📦 Installation

```bash
pip install pandas numpy pathway bokeh plotly geopy
````

---

## ▶️ How to Run

1. Open the notebook in **Google Colab** or **VS Code Jupyter**.
2. Run all cells from top to bottom.
3. Visualizations will auto-generate using Bokeh or Plotly.
4. To view real-time charts using Bokeh:

   * Use `output_file()` to export to an interactive HTML page.

---

## 📊 Visualization

* 📍 Real-time pricing line plots per parking lot
* 📊 Comparison of price trends over time
* 📡 Competitor-aware pricing changes (Model 3)

---

## 📝 Assumptions

* Base price is fixed at **\$10**
* Demand normalization ensures price stays between **0.5x and 2x** base
* Vehicle weights and traffic weights are manually tuned
