# Document Automation Engine (n8n & Airtable)

An intelligent, fully automated workflow designed to eliminate manual document generation, reduce human error, and streamline document status tracking across multiple platforms.

## 🎯 The Business Problem
In many operational pipelines, generating standard documents (contracts, reports, formal letters) is a highly manual process. This typically involves:
* "Copy-pasting" data from spreadsheets into Word templates, leading to critical typos and formatting errors.
* Wasted employee hours on repetitive administrative tasks.
* Fragmented file storage and inconsistent status tracking across the team.

## 💡 The Solution
This automated engine acts as a bridge between the database (Airtable) and the file storage (Google Drive). Triggered automatically or via webhook, it generates pixel-perfect PDFs and synchronizes their statuses in real-time.

### Key Features:
* **Workflow Orchestration (n8n):** The brain of the operation. Handles triggers, API requests, data transformations, and error routing.
* **Dynamic Template Rendering:** Ingests raw data from Airtable and maps it precisely to placeholders within a base DOCX template.
* **Format Conversion:** Automatically converts the finalized DOCX document into a secure, ready-to-send PDF.
* **Automated Filing & Synchronization:** Uploads the final PDF to specific Google Drive folders and writes back the direct URL and 'Completed' status into the Airtable record.

## 🛠️ Tech Stack
* **Orchestrator:** n8n (Webhooks, HTTP Requests, Switch/If logic)
* **Database / Trigger:** Airtable
* **File Storage:** Google Drive API
* **Document Processing:** Custom DOCX rendering and PDF conversion services / APIs

## 🔄 Workflow Architecture
1. **Trigger:** A record in Airtable is marked as "Ready for Generation".
2. **Fetch & Validate:** n8n retrieves the record data and validates required fields.
3. **Render (DOCX):** Data is injected into the designated DOCX template.
4. **Convert (PDF):** The customized DOCX is converted into a PDF format.
5. **Store:** The PDF is saved to Google Drive.
6. **Update:** The Airtable record is updated with the file URL and its status is changed to "Done".

---
*Note: This repository publicly showcases the architectural mapping and workflow design. Sensitive credentials, production API keys, and internal business templates have been intentionally omitted for security purposes.*
