# PDFQueryBot- Gemini PDF Chatbot with Authentication and Chat History
This is a full-stack chatbot application built using **React.js**, **Supabase**, and **FastAPI**. It integrates with the **Gemini API** to allow authenticated users to upload PDF documents, ask questions about them, and receive intelligent responses. Chat History is stored for each user.
#### 🌐 Live Demo - [PDFQueryBot](https://pdf-query-bot-six.vercel.app/)
---

## Features
### User Authentication
- User registration, login, and logout using Supabase Auth.
- Access control: Only logged-in users can interact with the chatbot.
### Gemini Chatbot
- Users can upload PDF documents.
- Extracts text using `pdf-parse`.
- Sends queries to the Gemini API and returns meaningful responses.
### Chat History (Stored in PostgreSQL via Supabase)
- Stores:
  - User ID
  - Timestamp
  - User Query
  - Chatbot Response
- Authenticated users can view their previous conversations.

---

## 🛠️ Technologies Used

- **Frontend:** React.js, TailwindCSS
- **Backend:** FastAPI, Uvicorn, Langchain
- **Auth & DB:** Supabase
- **PDF Parsing:** `pdf-parse`
- **LLM API:** Gemini API (Google Generative AI)
- **Deployment:** Vercel (frontend), Render (backend)

---

## Getting Started

### 1. Clone the repository
```bash
git clone <repository-url>
cd PDFQueryBot
```

### 2. Setup Frontend
#### Install dependencies:
```
npm install
```
#### Set up environment variables (.env file):
```bash
VITE_SUPABASE_URL=<supabase_url>
VITE_SUPABASE_ANON_KEY=<supabase_anon_key>
VITE_BACKEND_URL=<backend_url>
```
#### Run the frontend:
```
npm run dev
```

### 3. Setup Backend
#### Create Virtual Environment
```
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```
#### Install Dependencies
```bash
pip install -r requirements.txt
```
#### Set up environment variables (.env file):
```bash
GOOGLE_API_KEY=<your_google_api_key>
```
#### Run the backend:
```
uvicorn server:app --reload --port 5000
```

---

## API Endpoints
#### POST /upload_pdf
- Accepts a multipart/form-data file
- Extracts and stores PDF content

#### POST /ask
- Request: { "question": <any_ques_from_pdf> }
- Response: { "answer": <corresponding_ans> }

---

## Sample Queries & Responses
- *See:* `sample_chat_log.txt`
- *For testing:* Use `testing.pdf`

---
