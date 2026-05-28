# Technical Architecture Document (TAD)
## AI QA Automation Platform

---

# 1. Introduction

The AI QA Automation Platform is an AI-powered developer tool designed to automate unit and integration test generation for React applications using Large Language Models (LLMs).

The platform uses a modern full-stack architecture consisting of:
- React frontend
- FastAPI backend
- Ollama AI server
- GPT-OSS 20B model

The system enables developers to paste React source code and receive intelligent Jest + React Testing Library test suites automatically.

---

# 2. System Objectives

The primary objectives of the platform are:

- Automate frontend test generation
- Improve software quality assurance
- Increase test coverage
- Reduce manual QA effort
- Provide intelligent developer tooling

---

# 3. High-Level Architecture

Frontend (React + Monaco Editor)
↓
FastAPI Backend
↓
AI Engine Layer
↓
Ollama Server
↓
GPT-OSS 20B Model
↓
Generated Test Cases
↓
Frontend Dashboard Display

---

# 4. Frontend Architecture

## Technologies
- React.js
- Monaco Editor
- Axios

## Responsibilities
- Accept React source code
- Display generated test cases
- Display execution logs
- Show code coverage metrics
- Communicate with backend APIs

## Main UI Components

### Source Code Editor
Allows developers to paste React component source code.

### Generated Tests Viewport
Displays AI-generated Jest test suites.

### Execution Logs Console
Displays:
- PASS/FAIL logs
- AI workflow logs
- Coverage analysis

### Coverage Metrics Display
Shows estimated code coverage percentage.

---

# 5. Backend Architecture

## Technologies
- FastAPI
- Python
- Uvicorn
- Pydantic

## Responsibilities
- Receive frontend requests
- Process code input
- Connect to AI engine
- Return generated output

## API Endpoint

### POST /generate-tests

Request:
{
  "code": "React source code"
}

Response:
{
  "generated_tests": "Generated Jest tests",
  "logs": []
}

---

# 6. AI Engine Architecture

## AI Provider
- Ollama Enterprise Server

## Model Used
- GPT-OSS 20B

## Environment Configuration

OLLAMA_BASE_URL=http://10.100.20.76:11434
OLLAMA_MODEL=gpt-oss:20b

## AI Workflow

1. Receive React source code
2. Analyze:
   - UI structure
   - State handling
   - Click handlers
   - Conditional rendering
   - API dependencies
3. Generate:
   - Unit tests
   - Integration tests
   - Edge-case validations
4. Return formatted Jest test suite

---

# 7. Coverage Analysis System

Coverage is estimated using:

Coverage = (Executed Statements / Total Statements) × 100

Validation threshold:
Coverage ≥ 80%

The system displays coverage metrics inside the dashboard UI.

---

# 8. Data Flow Architecture

User Input
↓
Frontend Request
↓
FastAPI API Endpoint
↓
AI Processing Layer
↓
Ollama Model Inference
↓
Generated Tests
↓
Frontend Rendering

---

# 9. UI Design Architecture

## Layout Structure

### Left Panel
- Source code editor

### Right Panel
- Generated test cases

### Bottom Console
- Execution logs

## Theme
- Dark mode
- Developer-focused design
- VS Code-inspired interface

---

# 10. Security Architecture

- CORS-enabled API communication
- Controlled backend execution
- Local AI inference support
- Environment variable-based configuration

---

# 11. Scalability Considerations

The architecture supports future scalability through:

- Modular backend services
- AI abstraction layer
- Multi-file repository support
- Container deployment readiness
- CI/CD integration support

---

# 12. Future Enhancements

- Real Jest execution engine
- GitHub repository ingestion
- AST-based code analysis
- Real-time streaming logs
- Multi-project analysis
- PDF report generation

---

# 13. Deployment Architecture

## Frontend
- Vite React Application

## Backend
- FastAPI Server

## AI Layer
- Ollama Enterprise AI Server

## Communication
- REST APIs over HTTP

---

# 14. Conclusion

The AI QA Automation Platform combines AI-powered reasoning with modern developer tooling to automate software testing workflows efficiently.

The architecture is modular, scalable, and enterprise-ready, making it suitable for intelligent QA automation systems and future DevOps integrations.
