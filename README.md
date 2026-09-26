# ⚡ Automated Receipt Parser Workflow (n8n)

An automated n8n workflow designed to parse incoming receipt images, extract structured line-item data using AI, and append transaction details directly to Google Sheets.

![Workflow Screenshot]([screenshots/workflow-canvas.png](https://github.com/chenkyle1/Receipt-Tagger-Workflow/commit/6beaf1178e577a733b5d0cc7f424bfb7ca69cb91))

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
