---
title: 'Redundancy-Aware Sensor Fusion with Drift Detection'
summary: 'A simulation demonstrating sensor fusion techniques (mean, weighted, Kalman filter) with automatic drift detection using residual analysis and adaptive trust weighting.'
tags:
  - AI/ML
  - Sensor Fusion
  - Anomaly Detection
  - Python
  - Data Science
date: '2024-09-01'
icon: crosshairs
external_link: 'https://github.com/kalidasan-2001/redundancy-aware-sensor-fusion'

links:
  - icon: brands/github
    name: View Code
    url: 'https://github.com/kalidasan-2001/redundancy-aware-sensor-fusion'
  - icon: custom/colab
    name: Open in Colab
    url: 'https://colab.research.google.com/github/Kalidasan-2001/redundancy-aware-sensor-fusion/blob/main/notebooks/redundancy_sensor_fusion.ipynb'

url_code: 'https://github.com/kalidasan-2001/redundancy-aware-sensor-fusion'
---

## Overview

A **toy demonstration** of how **redundancy** and **sensor fusion** improve reliability in noisy measurement systems. The project simulates three sensors measuring a hidden signal, with one sensor developing a drift fault, and demonstrates automatic fault detection and isolation.

**Inspired by research at TH OWL** on industrial sensor systems and redundancy management.

## Key Features

### Fusion Techniques
| Technique | Description | Purpose |
|-----------|-------------|---------|
| **Mean Fusion** | Simple average of all sensors | Reduces random noise |
| **Weighted Fusion** | Trust based on sensor variance | Improves accuracy under noise |
| **Kalman Filter** | Predicts & updates with uncertainty | Dynamic, robust fusion |

### Drift Detection
- **Rolling Residual Z-Scores**: Detects persistent drift
- **Automatic Fault Flagging**: Identifies drifting sensors
- **Adaptive Trust Visualization**: Shows changing sensor weights

## Simulation Results

âœ… **Before Drift** â€” All sensors agree, fusion matches true signal  
âš ï¸ **After Drift** â€” Sensor C drifts upward; weighted & Kalman fusion resist drift  
íº¨ **Drift Detection** â€” Residual analysis correctly flags Sensor C  
í³‰ **Fusion Stability** â€” Fused signals remain stable despite drift  
í¾›ï¸ **Adaptive Weights** â€” Trust for Sensor C drops after drift onset  

## Technical Approach

### Drift Detection Algorithm
1. Calculate residual: `sensor_reading - fused_value`
2. Compute rolling z-score of residuals
3. Flag sensor if z-score exceeds threshold (e.g., 3.0)
4. Adjust sensor weights based on reliability

### Implementation
```python
# Simulate sensors
sensors = {
    'A': latent_signal + noise_A,
    'B': latent_signal + noise_B,
    'C': latent_signal + noise_C + drift  # Drift after t=700
}

# Fusion methods
mean_fusion = np.mean([A, B, C])
weighted_fusion = weighted_avg(sensors, weights)
kalman_fusion = kalman_filter.update(sensors)

# Drift detection
z_score = (residual - rolling_mean) / rolling_std
if abs(z_score) > 3.0:
    flag_sensor_drift()
```

## Applications

- **Industrial IoT**: Redundant sensor monitoring
- **Autonomous Systems**: Sensor reliability for self-driving
- **Aerospace**: Critical system fault detection
- **Manufacturing**: Quality control with sensor arrays

## Notebook Structure

1. **Simulation** â€“ Latent signal + noisy sensors
2. **Visualization** â€“ Sensor behavior and drift
3. **Fusion** â€“ Mean, weighted, Kalman comparison
4. **Stability Check** â€“ Rolling standard deviation
5. **Drift Detection** â€“ Z-score analysis
6. **Adaptive Trust** â€“ Weight visualization
7. **Reporting** â€“ Automatic summary

## Technologies

- **NumPy**: Array operations and simulations
- **Matplotlib**: Visualization and plotting
- **SciPy**: Statistical analysis
- **Jupyter Notebook**: Interactive demonstration

---

**Technologies**: Python, NumPy, Matplotlib, Kalman Filter, Statistical Analysis, Sensor Fusion
