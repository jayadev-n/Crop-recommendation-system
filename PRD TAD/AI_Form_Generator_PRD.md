# Product Requirements Document (PRD)

# AI Form Generator

## Version
1.0

## Prepared By
Jayadev

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
