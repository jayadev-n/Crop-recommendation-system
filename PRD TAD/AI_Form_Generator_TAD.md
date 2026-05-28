
---

# 1. Product Overview

AI Form Generator is an AI-powered web application that allows users to generate dynamic Google Form-style forms using natural language prompts.

The platform uses:
- React + Vite frontend
- FastAPI backend
- Ollama LLM integration
- Excel-based response storage
- Dynamic form rendering
- File upload support

The system generates shareable form links similar to Google Forms.

---

# 2. Problem Statement

Traditional form creation requires:
- Manual field setup
- UI configuration
- Validation configuration
- Database mapping

This process is time-consuming and non-technical users struggle to create forms efficiently.

AI Form Generator solves this problem using AI-generated schemas from plain English prompts.

---

# 3. Goals

## Primary Goals

- Generate forms using AI prompts
- Create shareable form links
- Support dynamic fields
- Save responses automatically
- Allow file uploads
- Provide Google Forms-like UI

## Secondary Goals

- Add authentication
- Add analytics dashboard
- Add drag-and-drop builder
- Cloud deployment
- Team collaboration

---

# 4. Target Users

## Primary Users

- Students
- HR teams
- Colleges
- Recruiters
- Event organizers
- Businesses

## Secondary Users

- SaaS platforms
- Startup incubators
- Internal enterprise teams

---

# 5. Core Features

## 5.1 AI Form Generation

Users enter prompts such as:

- "Generate a student admission form"
- "Create an employee onboarding form"
- "Generate feedback form with rating fields"

AI generates:
- Form title
- Fields
- Validation rules
- File upload fields
- Dropdown options

---

## 5.2 Dynamic Form Rendering

Generated schema dynamically creates frontend forms.

Supported field types:
- text
- email
- number
- date
- textarea
- dropdown
- radio
- phone
- file upload

---

## 5.3 Shareable Form Links

Each generated form gets:
- unique form ID
- public form URL

Example:
http://localhost:5173/form/abc123

---

## 5.4 Excel Response Storage

Submitted form responses are stored in:
- Excel (.xlsx) files

Each form maintains:
- Separate response sheet
- Structured columns
- Timestamp data

---

## 5.5 File Upload Support

Users can upload:
- resumes
- images
- PDFs
- documents

Files are stored locally in uploads folder.

---

# 6. Functional Requirements

## FR-1
System shall generate forms using natural language prompts.

## FR-2
System shall validate AI-generated schemas.

## FR-3
System shall create unique form links.

## FR-4
System shall dynamically render forms.

## FR-5
System shall store responses in Excel files.

## FR-6
System shall support file uploads.

## FR-7
System shall provide validation support.

---

# 7. Non-Functional Requirements

## Performance
- Form generation under 10 seconds
- Fast form loading

## Security
- File validation
- Secure upload handling
- Input sanitization

## Scalability
- Support multiple forms
- Future DB migration support

## Reliability
- AI fallback schema support
- Error handling

---

# 8. Technology Stack

## Frontend
- React
- Vite
- Tailwind CSS
- Axios

## Backend
- FastAPI
- Python

## AI Layer
- Ollama
- gpt-oss:20b

## Storage
- Excel (openpyxl + pandas)

---

# 9. User Flow

1. User enters prompt
2. Frontend sends request
3. Backend calls Ollama
4. AI returns JSON schema
5. Backend stores schema
6. Form link generated
7. User fills form
8. Data stored in Excel

---

# 10. Future Enhancements

- Authentication
- Admin dashboard
- Email notifications
- Cloud deployment
- Database integration
- PDF export
- Form analytics
- Multi-page forms
- Workflow approvals

---

# 11. Success Metrics

- Faster form creation
- Reduced manual effort
- AI accuracy
- User adoption
- Response submission rate

---

# 12. Conclusion

AI Form Generator transforms traditional form creation into an AI-powered automated workflow. The platform combines AI, dynamic rendering, and modern web technologies to simplify form generation for technical and non-technical users.
"""

trd_content = r"""# Technical Requirements Document (TRD)

# AI Form Generator

## Version
1.0

## Prepared By
Jayadev

---

# 1. System Overview

AI Form Generator is a full-stack AI-powered application that generates dynamic forms using Large Language Models (LLMs).

The architecture includes:
- React frontend
- FastAPI backend
- Ollama AI engine
- Dynamic schema generation
- Excel-based persistence
- File upload handling

---

# 2. High-Level Architecture

Frontend (React + Vite)
        |
        v
FastAPI Backend
        |
        v
LLM Engine (Ollama)
        |
        v
Generated JSON Schema
        |
        v
Dynamic Form Rendering
        |
        v
Excel Storage + File Uploads

---

# 3. Frontend Architecture

## Technologies

- React
- Vite
- Tailwind CSS
- Axios
- React Router

## Main Components

### HomePage.jsx
Handles:
- prompt input
- generate form request
- form link display

### FormPage.jsx
Handles:
- dynamic rendering
- validations
- file uploads
- form submission

### App.jsx
Handles routing.

---

# 4. Backend Architecture

## Technologies

- Python
- FastAPI
- Uvicorn
- Pandas
- OpenPyXL
- python-dotenv

---

# 5. API Endpoints

## GET /

Health check endpoint.

Response:
{
  "message": "AI Form Generator Backend Running"
}

---

## POST /generate-form

Generates AI form schema.

Request:
{
  "prompt": "Generate student admission form"
}

Response:
{
  "status": "success",
  "form_id": "abc123",
  "form_link": "http://localhost:5173/form/abc123",
  "schema": {}
}

---

## GET /get-form/{form_id}

Returns stored form schema.

---

## POST /submit-form/{form_id}

Stores form response.

Supports:
- multipart/form-data
- file uploads
- Excel storage

---

# 6. LLM Integration

## Ollama Configuration

Environment variables:

OLLAMA_BASE_URL=http://10.100.20.76:11434
OLLAMA_MODEL=gpt-oss:20b

---

## AI Flow

1. User enters prompt
2. Backend sends prompt to Ollama
3. Ollama generates JSON schema
4. Backend validates JSON
5. Schema stored in memory
6. Frontend renders form

---

# 7. Schema Design

Example schema:

{
  "form_title": "Student Form",
  "fields": [
    {
      "label": "Full Name",
      "name": "full_name",
      "type": "text",
      "required": true
    }
  ]
}

---

# 8. Supported Field Types

- text
- email
- number
- date
- textarea
- dropdown
- radio
- phone
- file

---

# 9. Validation System

Supported validations:
- min_length
- max_length
- regex patterns
- required fields
- allowed file extensions

---

# 10. File Upload Architecture

## Upload Flow

1. User uploads file
2. Backend validates extension
3. File stored in uploads folder
4. File path saved in Excel

---

# 11. Excel Storage Architecture

## Technologies
- pandas
- openpyxl

## Flow

1. Form submitted
2. Data converted to dataframe
3. Appended to Excel sheet
4. Separate Excel per form

Storage path:
backend/excel_data/

---

# 12. Security Considerations

## Input Validation
- Prompt sanitization
- File validation
- Required field checks

## File Upload Security
- Allowed extensions
- Unique filenames

## Backend Protection
- Exception handling
- Timeout configuration

---

# 13. Error Handling

Implemented:
- AI fallback schema
- JSON parsing fallback
- Request timeout handling
- Frontend error alerts

---

# 14. Development Environment

## Frontend

Run:
npm run dev

Port:
5173

---

## Backend

Run:
python -m uvicorn main:app --reload

Port:
8000

---

# 15. Folder Structure

ai-form-generator/
│
├── backend/
│   ├── main.py
│   ├── llm_engine.py
│   ├── uploads/
│   ├── excel_data/
│   └── .env
│
├── src/
│   ├── pages/
│   ├── components/
│   └── App.jsx
│
├── package.json
└── vite.config.js

---

# 16. Scalability Plan

Future upgrades:
- PostgreSQL integration
- Cloud storage
- Authentication
- Docker deployment
- Kubernetes scaling
- Admin dashboards

---

# 17. Future Architecture Enhancements

- AI workflow engine
- Multi-tenant support
- SaaS deployment
- Real-time analytics
- Email integrations
- OTP verification

---

# 18. Conclusion

The AI Form Generator architecture is modular, scalable, and AI-centric. The system successfully integrates React, FastAPI, Ollama, and Excel-based storage into a unified intelligent form-generation platform.
"""

base = Path("/mnt/data")

prd_path = base / "AI_Form_Generator_PRD.md"
trd_path = base / "AI_Form_Generator_TRD.md"

prd_path.write_text(prd_content, encoding="utf-8")
trd_path.write_text(trd_content, encoding="utf-8")

print(f"Created: {prd_path}")
print(f"Created: {trd_path}")
