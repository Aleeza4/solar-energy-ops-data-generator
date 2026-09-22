# Portfolio Project 1: Synthetic Solar Energy Operations Data Generator

A Python-based data generation project that simulates a full year of operational data for a hypothetical solar energy company in Pakistan — built as a foundation for downstream analytics, dashboarding, and machine learning projects.

## Overview

This project generates a realistic, interconnected dataset covering solar plants, equipment, energy generation, load consumption, faults, maintenance, weather, and tariffs. It's designed to mirror the kind of data an energy operations company would actually work with — the same domain I work in day-to-day as a SOC Executive in the energy sector.

The goal wasn't just to produce random numbers, but to model realistic relationships between entities: equipment belongs to plants, faults are tied to specific equipment, energy generation depends on weather and irradiance, and load/tariff data follows real daily and seasonal patterns.

## Why I Built This

This is Portfolio Project 1 in my data analytics portfolio. It demonstrates:

- **Data modeling** — designing multiple interlinked tables with realistic foreign-key relationships
- **Python (Pandas, NumPy)** — vectorized data generation at scale (17M+ rows in the largest table)
- **Domain knowledge** — applying real energy-sector concepts (irradiance, capacity factor, performance ratio, tariff structures) learned from my background in energy operations
- **Data engineering fundamentals** — producing clean, analysis-ready CSVs that can plug directly into BI tools, SQL databases, or ML pipelines

## Datasets Generated

| Dataset | Rows | Description |
|---|---|---|
| `plant_master.csv` | 20 | Solar plant details — region, capacity, operator |
| `equipment_master.csv` | 540 | Inverters and transformers per plant |
| `energy_generation.csv` | ~17.4M | 15-minute energy output per inverter |
| `load_consumption.csv` | ~139,780 | Regional load demand and electrical parameters |
| `fault_events.csv` | 3,000 | Equipment fault incidents with severity and cost impact |
| `maintenance_logs.csv` | 1,200 | Maintenance activities, costs, and technician teams |
| `weather.csv` | ~139,780 | Regional temperature, irradiance, wind, humidity |
| `tariff_cost.csv` | ~139,780 | Time-of-use tariff rates and demand charges |
| `equipment_performance_scores.csv` | 540 | Computed performance score and risk level per equipment |

All data spans **2025-01-01 to 2025-12-31** at 15-minute intervals across four regions (Punjab, Sindh, KPK, Balochistan).

## Tech Stack

- Python
- Pandas
- NumPy

## How It Works

1. **Master data** — Plant and equipment tables are generated first, since everything else references them.
2. **Time-series data** — Load, weather, and tariff data are generated per region across every 15-minute timestamp in 2025, using sinusoidal patterns to simulate realistic daily/seasonal cycles.
3. **Event data** — Fault and maintenance records are randomly sampled against real equipment IDs.
4. **Derived data** — Energy generation is calculated from irradiance, rated capacity, and efficiency; equipment performance scores are computed by aggregating generation metrics and fault counts per piece of equipment.
5. All tables are exported as CSVs, ready for use in Power BI, SQL, or further Python analysis.

## What's Next

This dataset is the foundation for future portfolio projects, including:
- An interactive Power BI / Streamlit dashboard for plant and equipment performance
- A predictive maintenance model using fault and maintenance history
- Load forecasting and tariff optimization analysis

## Author

**Aleeza** — Electrical Engineer | SOC Executive in energy operations | Building a data analytics career path

---
*This is a synthetic dataset generated for portfolio and learning purposes. It does not represent real plant or company data.*
