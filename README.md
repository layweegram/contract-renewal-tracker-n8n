```markdown
# ⚠️ Contract Renewal Tracker (n8n)

[![License](https://img.shields.io/badge/License-MIT-green.svg)](https://opensource.org/licenses/MIT)
[![n8n](https://img.shields.io/badge/Integration-n8n-blue.svg)](https://n8n.io/)

<p align="center">
  <img src="images/hero-marketing.png" alt="Automation unlocks growth — eliminate risk and save time by automating contract renewal alerts and notifications." width="900"/>
</p>

Automation unlocks growth — eliminate risk and save time by automating contract renewal alerts and notifications.

## Quick Overview
- Detect upcoming renewals and send automated alerts
- 1-day trigger window for urgent renewals
- Post alerts to Slack and keep history in Airtable

## Features
- Automated alerts and Slack notifications for contracts approaching expiry
- Configurable alert windows (e.g., immediate, 1-day)
- Easy to extend: add email, Teams, or other notification channels
- Store and track contract metadata in Airtable (or your preferred datasource)

## Demo / Screenshots
- Airtable: Vendor Contract Tracker (data source)
<p align="center">
  <img src="images/airtable-grid.png" alt="Airtable grid titled 'Vendor Contract Tracker' showing contract values, renewal dates, days-left and alert-window fields." width="1000"/>
  <br/>
  <em>Vendor Contract Tracker — main data source with Renewal Date, Days Left and Alert Window fields.</em>
</p>

- Spreadsheet calc: Days Left & Alert Window logic
<p align="center">
  <img src="images/sheet-snippet.png" alt="Spreadsheet showing 'Days Left' values (-1, 1, 3, 88) and 'Alert Window' flags (FIRE_ALERT or ---)." width="560"/>
  <br/>
  <em>Sample calculated Days Left values and Alert Window flags used to decide notifications.</em>
</p>

- n8n workflow execution
<p align="center">
  <img src="images/n8n-workflow.png" alt="n8n workflow execution: Schedule Trigger → Get Alert Contracts → Format Alert Message → Send a message (Slack); execution succeeded." width="1000"/>
  <br/>
  <em>n8n workflow finds expiring contracts, formats a message, and posts to Slack.</em>
</p>

- Slack alert example
<p align="center">
  <img src="images/slack-alert.png" alt="Slack alert message: urgent contract renewal alert listing two contracts with renewal dates and days-left counts." width="900"/>
  <br/>
  <em>Automated Slack alert posted by the n8n workflow with contract names, renewal dates, and days-left counts.</em>
</p>

## Getting Started
1. Clone the repo
   ```
   git clone https://github.com/layweegram/contract-renewal-tracker-n8n.git
   cd contract-renewal-tracker-n8n
   ```
2. Import the workflow
   - Import the n8n workflow file from `workflows/contract-renewal.json` into your n8n instance (Editor → Import). (*Note: You need to manually upload the JSON file to a 'workflows' folder in the repo.*)
3. Configure credentials
   - Add Airtable (or your datasource) and Slack credentials inside n8n.
4. Test and activate
   - Run the workflow manually to confirm messages are formatted correctly.
   - Activate the workflow on the schedule you prefer.

## Slack message template (example)
:rotating_light: URGENT CONTRACT RENEWAL ALERT! :rotating_light:

The following active contracts require immediate attention:
- Cloud Hosting Tier  
  - Value: $800  
  - Renewal Date: 2025-12-10 (Days Left
