# Earth's Magnetic Field Prediction Models: Research Findings

**Scout**: scout-prediction-models  
**Date**: January 13, 2026  
**Scope**: Computational models for predicting Earth's magnetic field behavior and forecasts for coming decades

---

## Executive Summary

Earth's magnetic field is monitored and modeled by two primary operational models (WMM and IGRF) updated every 5 years, supplemented by research-grade geodynamo simulations. Current models predict continued north magnetic pole migration toward Russia at ~55 km/year and ongoing field strength decline. **No reversal is predictable**—the process is fundamentally random. Model reliability is limited to approximately 5 years due to chaotic core dynamics.

---

## 1. Major Prediction Models

### 1.1 World Magnetic Model (WMM)
| Attribute | Details |
|-----------|---------|
| **Current Version** | WMM2025 (released December 17, 2024) |
| **Valid Until** | Late 2029 |
| **Developers** | US National Geospatial-Intelligence Agency (NGA) + UK Defence Geographic Centre (DGC); NCEI + British Geological Survey (BGS) |
| **Resolution** | Degree 12 spherical harmonic (~3000 km wavelength) |
| **Update Cycle** | Every 5 years |
| **Primary Use** | Navigation, attitude/heading systems, Android/iOS devices |
| **Source** | https://www.ncei.noaa.gov/products/world-magnetic-model |

**Key Features**:
- Standard model for DoD, NATO, FAA, and civilian navigation
- Provides magnetic declination, inclination, and total intensity
- Includes secular variation coefficients for forecasting
- Annual performance assessments against observations

### 1.2 International Geomagnetic Reference Field (IGRF)
| Attribute | Details |
|-----------|---------|
| **Current Version** | IGRF-14 (released November 2024) |
| **Maintained By** | International Association of Geomagnetism and Aeronomy (IAGA) |
| **Resolution** | Degree 13 spherical harmonic |
| **History** | Traces to IGRF-1 (1965) |
| **Primary Use** | Scientific research on deep Earth, crust, ionosphere, magnetosphere |
| **Source** | https://www.ncei.noaa.gov/products/international-geomagnetic-reference-field |

**Key Features**:
- Collaborative international effort
- Includes definitive models for historical epochs (1900-present)
- Standard reference for paleomagnetic studies

### 1.3 Enhanced Magnetic Model (EMM)
| Attribute | Details |
|-----------|---------|
| **Resolution** | Degree 790 (~51 km wavelength) |
| **Purpose** | Models both main field AND crustal magnetic anomalies |
| **Source** | NOAA NCEI |

### 1.4 World Magnetic Model High Resolution (WMMHR)
- Advanced version of WMM with degree 15 coverage
- More comprehensive secular variation data
- Released alongside WMM2025

### 1.5 Geodynamo Numerical Simulations
| Attribute | Details |
|-----------|---------|
| **Key Researchers** | Glatzmaier & Roberts (1995 breakthrough) |
| **Method** | Magnetohydrodynamic equations in liquid outer core |
| **Purpose** | Understanding field generation mechanism |
| **Status** | Research tool, NOT predictive |

---

## 2. Model Predictions

### 2.1 North Magnetic Pole Movement

**Current Position (2025)**: 85.762°N, 139.298°E

| Year | Latitude | Longitude | Notes |
|------|----------|-----------|-------|
| 1990 | 78°05'N | 103°41'W | Canadian Arctic |
| 2000 | 80°58'N | 109°38'W | Accelerating |
| 2010 | 85°01'N | 132°50'W | Rapid movement |
| 2020 | 86°29'N | 162°52'E | Crossed into Eastern Hemisphere |
| 2025 | 85.76°N | 139.30°E | Moving toward Russia |

**Predictions**:
- Speed: ~55 km/year moving north-northwest
- Direction: Continuing toward Russia/Siberia
- WMM provides predictions through 2030
- **Beyond 2030: Unreliable**

### 2.2 South Magnetic Pole Movement
- **Current Position (2025)**: 63.851°S, 135.078°E
- Movement is much slower and more stable than north pole
- Located near Antarctica

### 2.3 Field Strength Predictions
- **Current Trend**: Dipole declining at ~5% per century
- **Current Intensity Range**: 25,000-65,000 nT (location dependent)
- **South Atlantic Anomaly**: Growing region of weakened field
- **Forecast**: Decline expected to continue near-term

**Important Note**: Field strength decline does NOT indicate imminent reversal. Similar declines have occurred historically without reversals.

### 2.4 Reversal Predictions

| Factor | Status |
|--------|--------|
| **Imminent reversal?** | No—not predictable on any timescale |
| **Last full reversal** | 780,000 years ago (Brunhes-Matuyama) |
| **Average interval** | ~450,000 years (but statistically random) |
| **Duration when occurs** | 1,000-22,000 years |
| **Field during reversal** | Weak but not zero; multipolar chaos |

**Key Insight**: Reversal pattern is statistically random. Claims of periodicity are analytical artifacts. Science cannot predict the next reversal.

---

## 3. Model Limitations and Uncertainties

### 3.1 Temporal Prediction Horizon
| Timeframe | Reliability |
|-----------|-------------|
| 0-5 years | Good (within model epoch) |
| 5-10 years | Degrading |
| >10 years | Not reliable |
| 50-100 years | Fundamentally unpredictable |

**Evidence**: WMM2015 required emergency out-of-cycle update in February 2019 due to unexpected pole acceleration—demonstrating even 4-year predictions can fail.

### 3.2 What Models Cannot Predict
1. **Sudden pole accelerations** (like 2015-2019 event)
2. **Geomagnetic jerks** (sudden secular variation changes)
3. **Excursions** (brief reversals lasting hundreds of years)
4. **Space weather short-term effects**
5. **Outer core turbulence** (e.g., "high-speed jet" beneath Canada)

### 3.3 Geodynamo Simulation Limitations
- Require unrealistic physical parameters (high viscosity)
- Cannot reproduce Earth exactly
- Used for mechanism understanding, not prediction
- Computing power insufficient for Earth-like conditions

### 3.4 Spatial Resolution Limits
- WMM/IGRF: ~3000 km features only
- Cannot model local crustal anomalies
- EMM partially addresses this (51 km resolution)

### 3.5 Data Dependencies
- **Critical**: ESA Swarm satellite mission
- Ground observatory network essential
- CrowdMag crowdsourced data supplements
- Risk: Model accuracy would degrade if satellite missions end

---

## 4. Recent Advances (2024-2026)

| Date | Development |
|------|-------------|
| Nov 2024 | IGRF-14 released |
| Dec 2024 | WMM2025 released |
| Jan 2025 | BGS global space weather hazard index launched |
| Sep 2025 | UK nationwide magnetic monitoring sensors deployed |
| Dec 2025 | "Three norths" alignment leaving England |

**AI/ML Approaches**: No significant operational AI/ML advances found in mainstream models. Research continues but not yet incorporated into WMM/IGRF.

---

## 5. Key Takeaways

1. **5-year cycle is the practical limit** for reliable predictions
2. **North pole is moving fast** (~55 km/year) toward Russia
3. **Field strength declining** but this doesn't mean imminent reversal
4. **Reversals are unpredictable**—statistically random process
5. **2019 emergency update** demonstrated prediction limits
6. **Geodynamo simulations** explain mechanisms but don't forecast
7. **Long-term predictions (50-100 years) are not scientifically reliable**

---

## 6. Source URLs

- NOAA WMM: https://www.ncei.noaa.gov/products/world-magnetic-model
- NOAA IGRF: https://www.ncei.noaa.gov/products/international-geomagnetic-reference-field
- NOAA Pole Wandering: https://www.ncei.noaa.gov/products/wandering-geomagnetic-poles
- BGS Geomagnetism: https://www.bgs.ac.uk/research/geomagnetism/
- Nature (2019 pole article): https://www.nature.com/articles/d41586-019-00007-1
- Wikipedia Geomagnetic Reversal: https://en.wikipedia.org/wiki/Geomagnetic_reversal
- Wikipedia Dynamo Theory: https://en.wikipedia.org/wiki/Dynamo_theory
- Wikipedia North Magnetic Pole: https://en.wikipedia.org/wiki/North_magnetic_pole
- Wikipedia World Magnetic Model: https://en.wikipedia.org/wiki/World_Magnetic_Model

---

*Research completed January 13, 2026*
