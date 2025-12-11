# ⚠️ Contract Renewal Auto-Alert System (n8n & Airtable)

## 🎯 Project Overview

This critical automation ensures **100% assurance** against costly contract lapses, saving time and mitigating business risk. The system eliminates manual checks by firing alerts only for immediately urgent contracts.

**Tech Stack:** n8n, Airtable API, Slack.

---

## ⚙️ How It Works (The Workflow)

The system runs on a strict schedule, using precise filtering to prevent alert fatigue.

1.  **Scheduled Trigger:** N8N runs a daily check on the contract database.
2.  **Surgical Filtering:** The Airtable search uses a formula (`AND({Alert Window} = 'FIRE_ALERT', {Status} = 'Active')`) to pull only contracts due today or overdue.
    * *Airtable Logic:* Contracts with `Days Left` $\le 1$ are automatically flagged as `FIRE_ALERT`.
3.  **Data Consolidation:** A custom Code Node transforms multiple Airtable records into a single, clean Slack message.
4.  **Instant Notification:** The final message containing the Vendor, Value, and Renewal Date is delivered to a dedicated Slack channel.

---

## ✅ Key Deliverables

* **Fully Scheduled Workflow:** Guarantees continuous, automated contract monitoring.
* **Precision Alert Logic:** Eliminates noise; only critical renewals are flagged.
* **Custom Slack Alert:** Consolidated message for immediate action by contract owners.

## 🔗 Setup & Use

1.  Clone this repository.
2.  Import the workflow JSON (`contract-renewal-tracker-n8n.json`).
3.  Connect your Airtable and Slack credentials.
