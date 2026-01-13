---
title: 'Smart Sensor Analyzer: Real-Time Anomaly Detection'
summary: 'A Streamlit application for real-time sensor data visualization and anomaly detection using z-score analysis, featuring automated data generation and interactive dashboards.'
tags:
  - Data Science
  - Anomaly Detection
  - Python
  - Streamlit
  - Web Dev
date: '2024-08-01'
external_link: 'https://github.com/kalidasan-2001/smart-analyzer'

links:
  - icon: brands/github
    name: View Code
    url: 'https://github.com/kalidasan-2001/smart-analyzer'

url_code: 'https://github.com/kalidasan-2001/smart-analyzer'
---

## Overview

A **real-time sensor monitoring application** built with Streamlit that visualizes temperature and vibration data, detects anomalies using statistical methods, and provides interactive dashboards for industrial monitoring scenarios.

## Key Features

### í³Š Data Visualization
- **Dual Line Charts**: Temperature and vibration over time
- **Real-time Updates**: Continuous data refresh
- **Last N Readings**: Tabular view of recent measurements

### íº¨ Anomaly Detection
- **Z-Score Analysis**: Statistical outlier detection
- **Configurable Threshold**: Adjustable sensitivity (default: 3.0)
- **Visual Alerts**: Color-coded warnings for anomalies
- **Anomaly Counts**: Real-time metrics display

### í¾² Data Simulation
- **Synthetic Data Generator**: Realistic sensor noise
- **Configurable Spike Probability**: Inject anomalies (default: 3%)
- **CSV File Rotation**: Maintains last 1000 readings
- **Environment Variables**: Customizable parameters

## Technical Implementation

### Core Components

1. **Simulator** (`simulator.py`):
```python
def generate_row():
    base_temp = 24.5
    temp_noise = random.gauss(0, 0.6)
    temp_spike = random.uniform(2.5, 3.5) if spike else 0
    return [timestamp, temp, vibration]
```

2. **Analytics** (`analytics.py`):
```python
def zscore_anomalies(series, threshold=3.0):
    z = (series - series.mean()) / series.std()
    return abs(z) > threshold
```

3. **Streamlit App** (`app.py`):
   - Data loading with pandas
   - Anomaly detection integration
   - Interactive charting with st.line_chart
   - Metrics display with st.metric

## Use Cases

- **Industrial Monitoring**: Track sensor health
- **Predictive Maintenance**: Early fault detection
- **Quality Control**: Manufacturing process monitoring
- **Research**: Sensor behavior analysis

## Configuration

### Environment Variables
- `DATA_PATH`: CSV file location (default: `./data.csv`)
- `INTERVAL_SEC`: Simulation update rate (default: 2s)
- `SPIKE_PROB`: Anomaly injection probability (default: 0.03)

### Anomaly Detection
- **Threshold**: Z-score cutoff (typically 2.0-3.0)
- **Window**: Rolling statistics window size

## Technologies

- **Streamlit**: Interactive web app framework
- **Pandas**: Data manipulation and analysis
- **NumPy**: Numerical computations
- **CSV**: Data persistence
- **Python**: Core implementation

## Testing

- **Unit Tests**: `tests/test_analytics.py`
- **Test Coverage**: Core analytics functions
- **Pytest**: Testing framework

---

**Technologies**: Python, Streamlit, Pandas, NumPy, Statistical Analysis, Real-Time Monitoring
