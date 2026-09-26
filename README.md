# ⚡ Automated Receipt Parser Workflow (n8n)

An automated n8n workflow designed to parse incoming receipt images, extract structured line-item data using AI, and append transaction details directly to Google Sheets.

![Workflow Screenshot](https://github.com/chenkyle1/Receipt-Tagger-Workflow/blob/main/Screenshot%20From%202026-09-26%2016-25-27.png#:~:text=Screenshot%20From%202026%2D09%2D26%2016%2D25%2D27%2Epng,-Workflow)

## 📌 Overview
This workflow automates receipt processing to eliminate manual data entry. It listens for uploaded documents, processes the image using an LLM vision prompt, sanitizes the extracted monetary values, and logs the parsed record into a master spreadsheet while returning a shareable link.

## 🛠️ Tech Stack & Integrations
* **Automation Platform:** n8n
* **Triggers:** Webhook / Google Drive File Listener
* **AI/Extraction:** OpenAI GPT-4o Vision (Structured JSON Output)
* **Storage:** Google Sheets API

## 🔄 Workflow Logic
1. **Trigger:** Fires when a new receipt image is uploaded.
2. **OCR & Extraction:** Sends image payload to the AI vision model with a strict JSON extraction schema.
3. **Data Transformation:** Formats dates (`YYYY-MM-DD`), sanitizes numeric values, and handles fallback `null` logic.
4. **Action:** Appends formatted data as a new row in Google Sheets.
5. **Notification:** Generates direct Google Sheets URL for downstream alerting.

## 🚀 How to Use / Import

### Prerequisites
* A running instance of [n8n](https://n8n.io/) (Cloud or Self-Hosted).
* Configured credentials in n8n for:
  * Google Sheets API
  * OpenAI API (or alternative LLM service)

### Installation Steps
1. Clone this repository:
   ```bash
   git clone [https://github.com/your-username/your-repo-name.git](https://github.com/your-username/your-repo-name.git)
