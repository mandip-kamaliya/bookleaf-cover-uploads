# 📚 BookLeaf AI Cover Validator

An AI-powered book cover validation system built with **n8n**, **Google Drive**, **OCR**, **LLMs**, and **Airtable**. The workflow automatically validates uploaded book covers against publishing guidelines, identifies issues, logs results, and notifies authors.

---

## 🚀 Overview

BookLeaf receives thousands of book cover submissions from authors. Manual review is slow, repetitive, and prone to human error.

This workflow automates the entire validation process by:

- Detecting newly uploaded book covers
- Extracting the ISBN from the cover
- Identifying the corresponding author
- Performing AI-based cover validation
- Logging validation results
- Sending email notifications
- Recording all submissions in Airtable

---

## ✨ Features

- 📁 Google Drive integration
- 🔍 OCR-based ISBN extraction
- 👤 Automatic author lookup
- 🤖 AI-powered cover analysis
- 📊 Airtable database logging
- 📧 Automated email notifications
- ⚡ Fully automated using n8n
- 🔄 Human review support for failed submissions

---

## 🛠 Tech Stack

| Technology | Purpose |
|------------|---------|
| n8n | Workflow Automation |
| Google Drive API | File Storage |
| OCR | ISBN Extraction |
| Groq / Gemini API | AI Cover Analysis |
| Airtable | Validation Database |
| Gmail API | Email Notifications |

---

# Workflow

```
Author Uploads Cover
        │
        ▼
Google Drive Trigger
        │
        ▼
Download Cover
        │
        ▼
Extract ISBN (OCR)
        │
        ▼
Lookup Author
        │
        ▼
AI Cover Validation
        │
        ▼
Save Result to Airtable
        │
        ▼
Status = PASS ?
     ┌──────────────┐
     │              │
    Yes            No
     │              │
     ▼              ▼
Success Email   Revision Email
```

---

## AI Validation Checks

The AI validates the uploaded cover against BookLeaf publishing guidelines.

Checks include:

- Author name placement
- Safe margins
- Reserved badge area
- Text alignment
- Text readability
- Image quality
- Resolution
- Layout consistency

---

## Example AI Response

```json
{
  "status": "PASS",
  "confidenceScore": 95,
  "issuesFound": "No issues detected",
  "correctionInstructions": "Your cover meets all requirements.",
  "summary": "The cover complies with all publishing guidelines."
}
```

---

## Airtable Fields

The workflow stores:

- ISBN
- Author Name
- Author Email
- File Name
- Status
- Confidence Score
- Issues Found
- Correction Instructions
- File URL
- Detection Timestamp
- Revision Count

---

## Email Notifications

### PASS

The author receives:

- Approval notification
- Confirmation email
- Submission details

### FAIL

The author receives:

- List of detected issues
- AI-generated correction instructions
- Request to upload a revised cover

---

## Project Structure

```
BookLeaf-AI-Cover-Validator/

│
├── README.md
├── workflow.json
├── docs/
│     ├── architecture.png
│     └── workflow.png
├── screenshots/
├── prompts/
└── assets/
```

---

## Future Improvements

- WhatsApp notifications
- Slack integration
- Admin dashboard
- Multi-language validation
- Version history
- Duplicate submission detection
- Human approval portal
- Analytics dashboard

---

## Skills Demonstrated

- Workflow Automation
- API Integration
- AI Automation
- Prompt Engineering
- OCR Processing
- Conditional Logic
- Error Handling
- Database Integration
- Email Automation
- Low-Code Development

---


