📘 AI Note Generator using n8n

🚀 Overview

This project is an automated AI-powered note generation system built using n8n workflow automation.
It allows users to upload lecture content (PDF/DOCX/text) and automatically generates:

- 📄 Summary
- 🔑 Key Points
- ✅ Action Items

---

🧠 Features

- 📥 Upload files via Webhook (Postman / API)
- 📑 Extract text from PDF files
- 🤖 AI-based summarization using Gemini API
- 📌 Structured output:
  - Summary
  - Key Points
  - Actionable Tasks
- ⚡ Fully automated workflow using n8n

---

🛠️ Tech Stack

- n8n – Workflow automation
- Google Gemini API – AI text processing
- Postman – API testing
- JavaScript (n8n Code Node) – Data processing

---

🔁 Workflow Architecture

Webhook
   ↓
Extract from File (PDF)
   ↓
Edit Fields (Map lecture text)
   ↓
HTTP Request (Gemini API)
   ↓
Code Node (Parse Response)
   ↓
Respond to Webhook

---

📂 Project Structure

note-genesis-ai/
│
├── workflow/
│ └── note-genesis.json
│
├── screenshots/
│ ├── workflow.png
│ └── output.png
│
└── README.md

---

⚙️ Setup Instructions

1️⃣ Import Workflow

- Open n8n
- Import the provided "note-genesis.json" file

2️⃣ Configure API Key

- Get API key from Google AI Studio
- Add it in HTTP Request node:

x-goog-api-key: YOUR_API_KEY

3️⃣ Run Workflow

- Activate workflow
- Copy webhook URL

---

🧪 Testing (Using Postman)

- Method: "POST"
- URL: "your-webhook-url"

Option 1: JSON Input

{
  "lecture": "Machine learning is a subset of AI..."
}

Option 2: File Upload

- Body → form-data
- Key → "file" (type: File)
- Upload PDF

---

📤 Sample Output

{
  "summary": "This lecture explains...",
  "key_points": [
    "Point 1",
    "Point 2"
  ],
  "actions": [
    "Action 1",
    "Action 2"
  ]
}

---

⚠️ Common Issues

Issue| Fix
Service unavailable| Retry or enable retry in HTTP node
lecture = null| Check Edit Fields mapping
Binary field error| Use correct field name (data0/file)

---

🔮 Future Improvements

- 📄 DOCX support
- 🌐 Frontend UI (React / Web App)
- ☁️ Deployment (Cloud / API service)
- 🧾 Export notes as PDF

---

👨‍💻 Author

Vijay Vji
AI & ML Engineering Student

---

⭐ Support

If you like this project:

- ⭐ Star the repo
- 🍴 Fork it
- 📢 Share it

---

📜 License

This project is open-source and available under the MIT License.
