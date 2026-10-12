# Digital Twin for 2.5 MW Industrial Smart Microgrids
**Predictive Asset Management & Cyber-Physical Resilience in Industry 5.0**

![Status](https://img.shields.io/badge/Status-Completed-success)
![Platform](https://img.shields.io/badge/Platform-Web%20%2F%20Three.js-blue)
![Institution](https://img.shields.io/badge/Institution-Sapienza%20University%20of%20Rome-maroon)

## 📌 Project Overview
This repository contains the interactive 3D WebGL simulation of a **Closed-Loop Digital Twin** designed for a 2.5 MW industrial Smart Microgrid. Developed as part of a Master's Thesis in Electrical Engineering, this project bridges the gap between **OpenBIM interoperability**, real-time IoT telemetry, and predictive maintenance.

The architecture is specifically engineered for high-tech, continuous-cycle manufacturing sectors (e.g., Pharmaceutical Cleanrooms, Aerospace CNC machining, Flexible Manufacturing Systems) where tolerance to Power Quality disturbances is virtually zero. By integrating dynamic physical models with prescriptive control logics, the system ensures absolute operational continuity and zero-downtime during severe grid transients.

## ⚙️ Core Technical Features

### 1. OpenBIM to SCADA Integration
*   **Semantic Interoperability:** The 3D facility model was originally authored in Autodesk Revit MEP using commercial ABB equipment and exported to the open **IFC4** standard.
*   **bSDD Extension:** To enable real-time IoT integration, the IFC schema was semantically enriched using the **buildingSMART Data Dictionary (bSDD)**, natively mapping Modbus/MQTT holding registers and dynamic variables directly into the 3D objects.

### 2. Predictive Diagnostics & Thermal Stress (Scenario 1)
*   **Dynamic Thermal Modeling:** Solves the non-linear differential equations of the **IEC 60076-7** standard in real-time to simulate transformer Hot-Spot temperatures under varying industrial load profiles (e.g., 115% overload).
*   **Statistical Anomaly Detection:** Implements a dynamic **$3\sigma$ threshold** (3.6 °C) algorithm to filter out measurement noise and intercept latent cooling anomalies.
*   **Asset Management:** Continuously calculates the true **State of Health (SoH)** and the **Remaining Useful Life (RUL)** based on Miner's cumulative damage rule and Arrhenius-Eyring / Coffin-Manson models.

### 3. Cyber-Physical Resilience & Power Quality (Scenario 2)
*   **Ultra-Fast Island Mode:** In response to severe voltage sags violating the **SEMI F47** industrial immunity curve, the Digital Twin commands a Solid-State Circuit Breaker (SSCB) to isolate the microgrid in **$< 15$ ms**, preventing the collapse of robot DC-buses.
*   **Adaptive Load Shedding:** Evaluates a penalty function $J_i = \alpha \cdot w_i + \beta \cdot (1 - SoH_i)$ to execute smart load shedding. Non-critical switchboards are disconnected based on their actual degradation level (SoH), protecting highly stressed assets while keeping vital pharmaceutical/FMS loads powered via Grid-Forming BESS.
*   **Grid Re-synchronization:** Automated grid reconnection supervised by an **ANSI 25 Synchrocheck Relay** algorithm ($\Delta V < 2\%$, $\Delta f < 0.05$ Hz, $\Delta\theta < 5^\circ$) to prevent inrush currents.

## 📊 Data Architecture
*   **Metrological Standard:** Telemetry aggregation assumes **IEC 61000-4-30 Class A** network analyzers, ensuring $\le 0.1\%$ uncertainty for reliable Anomaly Detection.
*   **Data Pipeline:** Edge IoT gateways publish telemetry via encrypted MQTT to a **Time-Series Database (TSDB)** located in a secure DMZ, fully compliant with **IEC 62443** cybersecurity standards for OT/IT segregation.

## 💶 Cost-Benefit Analysis (CBA) & ESG Impact
The technical excellence of the Digital Twin translates directly into validated business and environmental value:
*   **Financial Return:** Generates an estimated **ROI of 40.0%** with a highly competitive **Payback Period of 2.5 years**.
*   **Avoided TCD (Total Cost of Downtime):** Monetizes the prevention of catastrophic production losses, saving ~€19,000 per single prevented event (e.g., avoiding the destruction of sterile pharmaceutical batches).
*   **Decarbonization:** Optimizes transformer load-sharing and eliminates energy-intensive HVAC hard-restarts, saving 45,000 kWh/year. This equates to **11.92 tons of avoided $CO_2$ emissions** and generates **8.43 White Certificates (TEE)** annually.

## 💻 Technical Requirements
To run the interactive simulation locally or via GitHub Pages, you need:
*   A modern web browser with WebGL hardware acceleration enabled (Google Chrome, Microsoft Edge, Mozilla Firefox, or Safari).
*   No external plugins or proprietary BIM software required.

## 🎓 Acknowledgements
This project was developed at the **Faculty of Civil and Industrial Engineering, Sapienza University of Rome**. 

Special thanks to:
*   **Prof. Luigi Martirano** (Supervisor) and **Ing. Riccardo Loggia** (Co-Supervisor) for their invaluable methodological guidance and technical support.
*   **ABB** for the commercial specifications, data sheets, and original 3D Revit families of the electrical equipment utilized in the microgrid model.

---
*Developed by Gianluca Palazzi - Master's Degree in Electrical Engineering (A.Y. 2025/2026)*