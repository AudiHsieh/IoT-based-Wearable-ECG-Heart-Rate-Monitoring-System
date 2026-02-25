# IoT Wearable ECG System

## 📌 Project Overview
This project involves the research and development of a high-fidelity, low-power **Wearable Biosensing System** designed for continuous **Electrocardiogram (ECG)** and heart rate monitoring. By integrating medical-grade Analog Front-End (AFE) technology with a dual-core IoT processor, the system achieves clinical-grade biopotential acquisition and real-time telemetric visualization on mobile platforms.

## 🏗️ System Architecture & Engineering Depth

### 1. Strategic AFE Selection: Precision vs. Cost-Efficiency
The core of this system is engineered around the **Texas Instruments ADS1293**, a strategic choice made to outperform standard consumer-grade sensors while maintaining a competitive cost structure:
* **Cost-Performance (CP) Optimization**: Unlike redundant 12-lead diagnostic chipsets, the ADS1293 was selected for its ability to deliver **24-bit resolution** across 3 channels, providing the necessary precision for P-QRS-T wave analysis at a fraction of the BOM (Bill of Materials) cost.
* **Superior Accuracy**: While maintaining affordability, the system delivers higher diagnostic reliability than standard optical (PPG) sensors, making it a "medical-lite" solution for early cardiovascular anomaly detection.

### 2. Embedded Intelligence & Deterministic Logic
* **Core Controller**: Powered by the **ESP32 Dual-Core SoC**, managing concurrent tasks for data sampling, digital filtering, and wireless telemetry.
* **Real-time OS (FreeRTOS)**: Implements **Deterministic Task Scheduling** to prioritize high-frequency ADC interrupts over background communication tasks, ensuring zero data loss during critical heart rate fluctuations.
* **Wireless Telemetry**: Leverages the **BLE (Bluetooth Low Energy) GATT Profile** for power-efficient data streaming to mobile hosts.

### 3. Cross-Platform Analytics & Visualization
* **Real-time DSP (Digital Signal Processing)**: The mobile application implements real-time plotting algorithms to visualize raw ECG streams with minimal latency.
* **Health Analytics Engine**: Integrated algorithms for heart rate variability (HRV) analysis, caloric expenditure estimation, and body composition tracking based on multi-sensor fusion.

## 💻 Technical Highlights
* **Active Shielding & Noise Mitigation**: Implementation of hardware-level lead-off detection and right-leg drive (RLD) circuits to enhance signal quality.
* **Edge-to-Cloud Architecture**: A scalable framework that supports local real-time monitoring and optional cloud-based historical data logging for longitudinal health trends.
* **Proactive Diagnostics**: Designed with a focus on early detection of asymptomatic cardiovascular anomalies, bridging the gap between consumer wearables and clinical diagnostic tools.

## 📁 Repository Structure
| Component | Description |
| :--- | :--- |
| `/Firmware` | ESP-IDF based source code utilizing FreeRTOS for multi-threaded biosensing. |
| `/Mobile_App` | Android Studio project (Java/Kotlin) featuring real-time telemetry and UI/UX for ECG tracing. |
| `/Hardware` | Schematic and PCB layouts for the ADS1293 and ESP32 integration. |
| `/Docs` | Comprehensive technical report and signal processing analysis. |

## 🛠️ Tech Stack
* **Processor**: Espressif ESP32 (Dual-core Xtensa® 32-bit LX6)
* **Biomedical AFE**: Texas Instruments ADS1293
* **Firmware Framework**: ESP-IDF / FreeRTOS
* **Mobile Development**: Android Studio / BLE API
* **Communication Protocols**: BLE 4.2+, Wi-Fi (802.11 b/g/n)

---
*Disclaimer: This system is intended for research and health-tracking purposes. It is not a replacement for professional medical diagnosis.*
