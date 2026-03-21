# 📦 Supply Chain Control Tower: Automated Exception Engine 
> **Eliminating the "SAP-to-Excel" manual grind with real-time n8n automation.**

![n8n](https://img.shields.io/badge/n8n-Workflow-FF6C37?style=flat-square&logo=n8n)
![SAP](https://img.shields.io/badge/SAP-Data_Logic-008FD3?style=flat-square&logo=sap)
![Slack](https://img.shields.io/badge/Slack-Real--time_Alerts-4A154B?style=flat-square&logo=slack)
![Status](https://img.shields.io/badge/Status-Portfolio_MVP-success?style=flat-square)

---

## 📌 Business Case
In supply chain operations, data is often fragmented across multiple SAP T-codes. The traditional method of manual exports and `VLOOKUP` reconciliation results in **delayed visibility**. By the time an analyst identifies a shipment delay, the opportunity for proactive intervention has often passed.

**This project solves for:**
* **Data Silos:** Merges PO data (SAP EKKO/EKPO) with live logistics tracking APIs.
* **Manual Effort:** Replaces a 2-hour daily reconciliation task with a 2-second automated trigger.
* **Actionability:** Shifts the team from *searching* for delays to *receiving* instant alerts via Slack.

---

## ⚙️ Architecture & Logic
The workflow is built in **n8n** and follows a standard ETL (Extract, Transform, Load) pattern:

### 1. Data Ingestion (Extraction)
* **Node A:** Fetches Open Purchase Order data (Line-item level).
* **Node B:** Fetches real-time shipment statuses and Updated ETAs from logistics providers.

### 2. Logic & Transformation (The "Brain")
* **Inner Join:** Uses a primary key (`PO_Number`) to merge SAP data with tracking data.
* **Anomaly Detector:** A conditional logic gate that evaluates:
  > IF `Updated_ETA` > `Expected_Delivery_Date` AND `Status` == "Delayed" ➡️ **Trigger Alert**

### 3. Output (Load)
* **Slack Notification:** Sends a formatted message to the Operations team for immediate action.
* **BI Data Warehouse:** Appends the cleaned, joined record to a master sheet for dashboard reporting.

---

## 🖼️ Visualizations

### The Workflow
![Workflow Screenshot](image_e27f24.png)

### The Result: Real-time Alert
![Slack Alert](YOUR_SLACK_SCREENSHOT_FILENAME.png)

---

## 📊 Data Schema Mapping
To ensure accuracy, the following data points are synchronized:

| Field | Source | Purpose |
| :--- | :--- | :--- |
| `PO_Number` | SAP (Internal) | Primary Key / Join ID |
| `Expected_Date` | SAP (Internal) | Baseline Performance Metric |
| `Updated_ETA` | Logistics (External) | Live Performance Data |
| `Status` | Logistics (External) | Exception Trigger |

---

## 🚀 Future Roadmap
- [ ] Integration with Snowflake for long-term historical trend analysis.
- [ ] Automated "Nudge" emails to vendors when delays are detected.
- [ ] Predictive ETA modeling using historical carrier lead times.

---
**Looking for a Supply Chain professional who automates the boring stuff? [Let's Connect on LinkedIn!](YOUR_LINKEDIN_URL)**
