# Digital Twin & OpenBIM for Industrial Smart Microgrids (2.5 MW)

![Digital Twin Overview](https://img.shields.io/badge/Project-Digital_Twin-38bdf8?style=flat-square)
![Institution](https://img.shields.io/badge/Institution-Sapienza_University_of_Rome-b32317?style=flat-square)
![Status](https://img.shields.io/badge/Status-Completed-10b981?style=flat-square)

## 📌 Project Overview
This repository contains the interactive cyber-physical simulation developed for the Master's Thesis in Electrical Engineering at **Sapienza University of Rome**. 

The project demonstrates the transition from a static BIM model to a fully operational **Digital Twin** for a 2.5 MW Industrial Smart Microgrid. By integrating OpenBIM data (IFC4/bSDD) with real-time dynamic thermal modeling and predictive algorithms, this platform enables **Condition-Based Maintenance (CBM)** and autonomous resilience strategies (Island Mode & Load Shedding) for mission-critical industrial facilities (e.g., Pharma Cleanrooms, Aerospace FMS).

**Candidate:** Gianluca Palazzi  
**Advisor:** Prof. Luigi Martirano  
**Co-Advisor:** Prof. Riccardo Loggia

---

## ⚙️ Core Architecture & Technologies
*   **3D WebGL Visualization:** Built with `Three.js` for lightweight, browser-based execution without proprietary software.
*   **OpenBIM Semantic Extension:** IFC4 schema enriched via buildingSMART Data Dictionaries (bSDD) to map Modbus/MQTT telemetry directly to BIM assets (ABB commercial components).
*   **Dynamic Physical Modeling:** Real-time integration of **IEC 60076-7** equations for continuous transformer thermal modeling, coupled with Arrhenius-Eyring and Coffin-Manson cumulative fatigue models for power electronics.
*   **Industrial Standard Compliance:** Power Quality thresholds engineered according to **EN 50160** and **SEMI F47** immunity curves.

---

## 🕹️ Simulation Scenarios

The interactive dashboard features two main simulation environments demonstrating the system's cyber-physical capabilities:

### Scenario 1: 24h Thermal Stress & Predictive Diagnostics
Simulates an operational day characterized by a prolonged 115% overload. 
*   **Features:** Real-time Hot-Spot temperature tracking, dynamic calculation of Relative Aging Rate ($V(t)$), and thermochromic visual feedback.
*   **KPIs:** Continuous update of Asset State of Health (SoH) and Remaining Useful Life (RUL) estimation.
*   **Prescriptive Action:** Allows manual execution of Load Derating to actively recover asset lifespan.

### Scenario 2: Event-Driven Load Shedding & Island Mode
Simulates a severe voltage sag originating from the macro-grid, threatening the stability of critical industrial processes.
*   **Features:** Ultra-fast Solid-State Circuit Breaker (SSCB) tripping ($\le$ 15 ms), transition of the BESS to Grid-Forming mode, and startup of the standby Diesel Generator.
*   **Adaptive Intelligence:** Execution of an autonomous Load Shedding algorithm guided by the physical degradation state (SoH) of the switchboards, rather than static priorities.
*   **Live CBA Analytics:** Real-time monetization of the Total Cost of Downtime (TCD) avoided and calculation of White Certificates (TEE) earned.

---

## 📈 Economic & Environmental Impact
The integration of this Digital Twin architecture proves highly viable from a Capital Budgeting perspective:
*   **ROI:** Estimated at 40% per annum.
*   **Payback Period:** Achieved within 2.5 years.
*   **ESG Metrics:** Contributes to an annual reduction of nearly 12 tons of $CO_2$ equivalent by optimizing asset load factors and eliminating destructive startup transients.

---

## 🚀 How to Run the Simulation
This project is designed to run entirely client-side. No complex server setup is required.
1. Simply open the `index.html` file in any modern web browser (Chrome, Edge, Firefox).
2. Use the top-left navigation buttons to switch between Scenario 1 and Scenario 2.
3. Interact with the bottom toolbar to adjust playback speed, inject voltage sags, or export metrological CSV audits.