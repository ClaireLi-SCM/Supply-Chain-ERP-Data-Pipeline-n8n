# SAP to Slack: Automated Delay Tracker 📦

I built this simple automation to stop the "SAP-to-Excel" struggle. Instead of jumping between T-codes and doing manual VLOOKUPs, this flow handles the heavy lifting.

### ❓ The Problem
Manually exporting PO data and matching it with logistics tracking is slow. By the time you find a delay in a spreadsheet, it's usually too late to fix it.

### ✅ The Solution
Using **n8n**, I created a workflow that:
1. **Pulls Data:** Grabs SAP POs and live tracking info at the same time.
2. **Auto-Joins:** Merges them perfectly (no more broken formulas).
3. **Alerts:** Pings **Slack** the second a shipment is actually marked "Delayed."

---

### 🖼️ How it looks
**The Workflow:**
![n8n_workflow]

**The Result (Slack Alert):**
![slack_alerts]

---

### 🛠️ Tools Used
* **n8n** (The brain)
* **SAP Data** (The source)
* **Slack** (The alerts)
* **Google Sheets** (The final dashboard)

---
**Looking for a Supply Chain Analyst who loves to automate? [Let's chat on LinkedIn!](YOUR_LINKEDIN_URL)**
