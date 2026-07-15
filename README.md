# Torres Strait Water Dynamics: A Remote Sensing Analysis
**GISC331 Real-World Investigation | Jessica Burrows**

## 📌 Project Overview
This study investigates the temporal relationship between local monthly rainfall and surface water extent on **Badu and Horn Islands** (1995–2022). The report aims to identify the physical characteristics of fractured granite aquifers and ephemeral catchments which are highly sensitive to climate variability.

**Research Question:** To what extent do local rainfall patterns correlate with the surface area of freshwater bodies, and how has this relationship changed over time?

## 🛠️ Tech & Methodology
*   **Platform:** Digital Earth Australia (DEA) Sandbox
*   **Sensor:** Sentinel-2 Analysis Ready Data (ARD) @ 20m spatial resolution
*   **Index:** Modified Normalized Difference Water Index (MNDWI)
    *   Formula: $MNDWI = \frac{Green - SWIR}{Green + SWIR}$
*   **Classification:** Water pixels classified using a threshold of $MNDWI > 0$.

## 📁 Data Integration & Pre-processing
A key component of this analysis was the integration of in-situ meteorological records with satellite-derived observations.

*   **Rainfall Data Acquisition:** Monthly rainfall records were sourced from the **Bureau of Meteorology (BOM)** Horn Island Station (ID 027058).
*   **Import Workflow:** The `.csv` data was imported into the DEA Sandbox environment and processed using the `pandas` library.
*   **Temporal Aggregation:** To align the daily rainfall records with the seasonal satellite passes, I performed a temporal aggregation:
    *   Converted "Date" strings to `datetime` objects.
    *   Resampled daily data to **Monthly Medians** to match the 20m Sentinel-2 seasonal time-steps.
*   **Data Alignment:** The resulting dataframe was combined with the MNDWI water-area array to produce dual-axis time-series plots, allowing for the identification of the hydrological "lag" between rainfall events and surface water response.

## 📊 Key Findings
*   **Managed Systems (Horn Island):** Showed a clear, positive, and lagged correlation between rainfall and dam levels, peaking during the 2020–2022 La Niña.
*   **Natural Systems (Badu Island):** Broadly aligned with seasonal patterns, but MNDWI performance was limited by persistent cloud cover and shallow, vegetated water bodies.

## 🚀 Further Research
This baseline analysis highlights the potential for integrating **Explainable AI (XAI)** to improve cloud-masking and automated detection in tropical island settings.

---
*Data Sources: Geoscience Australia (Sentinel-2), Bureau of Meteorology (Rainfall).*
