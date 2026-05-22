# Intelligent Document Processing System

## Overview
An AI-powered Intelligent Document Processing (IDP) system that extracts, structures, and digitizes information from PDF and image documents using the Anthropic Claude API. Upload any document and get back structured data including text, tables, images, and named entities — all in JSON or CSV format.

---

## Features
- Multi-format support — PDF, JPEG, PNG (scanned and digital)
- Printed text extraction with high accuracy
- Handwritten text recognition (OCR)
- Table detection and reconstruction (rows, columns, hierarchy)
- Embedded image extraction with indexing and metadata
- Key-value pair extraction
- Named entity recognition — names, dates, amounts, addresses, emails, phone numbers
- Structured output export — JSON and CSV
- Drag-and-drop upload interface
- Confidence scoring per document

---

## Tech Stack
- React 18
- Anthropic Claude API (claude-sonnet-4)
- Tabler Icons
- Vanilla CSS with CSS variables

---

## Getting Started

### Prerequisites
- Node.js v18 or above
- Anthropic API key — get one at https://console.anthropic.com

### Installation

```bash
git clone https://github.com/your-username/intelligent-document-processing.git
cd intelligent-document-processing
npm install
```

### Environment Setup

Create a `.env` file in the root directory:

```
ANTHROPIC_API_KEY=your_api_key_here
```

### Run the App

```bash
npm start
```

Open `http://localhost:3000` in your browser.

---

## Usage

1. Open the app in your browser
2. Drag and drop or click to upload a PDF or image file
3. Click **Extract Document Contents**
4. View results across five tabs:
   - **Overview** — document summary, confidence score, entities, key-value pairs
   - **Text** — printed and handwritten text extracted separately
   - **Tables** — reconstructed tables with full row and column structure
   - **Images** — indexed list of embedded images with descriptions
   - **Structured** — full raw JSON output
5. Export results as JSON or CSV

---

## Output Structure

```json
{
  "summary": "...",
  "documentType": "invoice",
  "language": "English",
  "confidence": 94,
  "extractedText": {
    "printed": "...",
    "handwritten": "...",
    "combined": "..."
  },
  "tables": [
    {
      "caption": "...",
      "headers": ["Item", "Qty", "Price"],
      "rows": [["Product A", "2", "$50"]]
    }
  ],
  "images": [
    {
      "index": 1,
      "description": "...",
      "type": "logo",
      "estimatedSize": "small"
    }
  ],
  "keyValuePairs": {
    "Invoice Number": "INV-2024-001",
    "Due Date": "2024-06-30"
  },
  "entities": {
    "names": [],
    "dates": [],
    "amounts": [],
    "emails": []
  }
}
```

---

## Supported Document Types
- Invoices and receipts
- Forms and applications
- Reports and letters
- Contracts and agreements
- Scanned handwritten notes
- Any PDF or image containing text

---

## Security
- Never commit your `.env` file
- Your API key is used server-side only and never exposed in the frontend bundle
- See `.env.example` for the required environment variable format

---

## License
MIT License — see `LICENSE` for details.

---

## Acknowledgements
- Anthropic Claude API for document understanding
- Tabler Icons for the UI icon set
