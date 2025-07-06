#  Dynamic Pricing for Urban Parking Lots

This project implements a **dynamic pricing engine** for urban parking lots, leveraging real-time data ingestion and machine learning to optimize parking rates. The goal is to balance occupancy and revenue based on demand patterns using a predictive pipeline built on modern data engineering and ML tools.

---

## Overview

Urban parking lots often face congestion, underutilization, or revenue losses due to static pricing. This project introduces a **machine learning-based adaptive pricing solution**. It uses real-time data such as time of day, location, demand, and occupancy rates to predict the optimal price dynamically.

The pipeline is powered by:
- A streaming framework (Pathway)
- A machine learning ensemble model
- Real-time feature engineering
- Interactive visualizations

---
## Project Architecture and Workflow

1. Data Ingestion:
- Real-time parking lot data (timestamp, lot ID, occupancy, etc.) is streamed into the system.

- Handled using Pathway to support real-time data processing.

2. Data Preprocessing:
- Incoming data is cleaned, parsed into a schema, and stored as dynamic Pathway tables.

- Date-time fields are extracted for several features.

3. Feature Engineering:
- Compute temporal features, occupancy stats, lot popularity index, and traffic intensity.

- Window-based aggregations are used to derive trends.

4. Predictive Modeling
A custom ensemble of:

- Basic numpy and pandas based linear functions.

5. Prediction Pipeline:
- New data points trigger real-time predictions using the ensemble model.

- Pathway handles stateful updates and ensures freshness of outputs.

6. Output Handling:
   
- Predicted prices are served via:

- Live dashboard using bokeh/panel

- Exported tables (CSV/Parquet)

- Potential REST API endpoint

- Visualized in an interactive map/table/dashboard interface for stakeholders to view and adjust.

7. Future Improvements:
   
- Incorporate reinforcement learning for dynamic price optimization.

- Integrate weather and traffic APIs to enhance feature richness.

- Develop a user-side mobile app interface for live pricing view and booking.

8. Contributors:
   
- Aniruddha Ray 

10. References:
    
- Pathway Documentation

- Bokeh Interactive Visuals

---
##  Tech Stack

| Category | Tools / Libraries |
|---------|-------------------|
| Programming Language | Python |
| Streaming Engine | [Pathway](https://pathway.com/) |
| Feature Engineering | `pandas`, `numpy`, `datetime` |
| Visualization | `bokeh`, `panel` |
| Notebook Interface | Google Colab / Jupyter |
| Model Optimization | `numpy`,`pandas` |

---

##  Architecture Diagram

```mermaid
---
config:
  layout: dagre
  theme: mc
---
flowchart TD
    A["Real-time Parking Data Stream"] --> B["Pathway Data Pipeline"]
    B --> C["Feature Engineering Module"]
    C --> D[" Ensemble Model"]
    D --> E["Predicted Parking Prices"]
    E --> F["Live Dashboard"] & G["Pricing API / Output Table"]

