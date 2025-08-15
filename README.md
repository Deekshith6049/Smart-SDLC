# SmartSDLC - AI-Enhanced Software Development Lifecycle

**SmartSDLC** is an AI-powered platform that enhances various stages of the Software Development Lifecycle (SDLC) using Hugging Face LLM models.  
It provides functionalities like requirement classification, code generation, bug fixing, test generation, code summarization, and an interactive AI chat assistant.

Frontend is built with HTML/CSS/JS, and backend runs on Flask (Python) hosted on Google Colab with ngrok for public access.

---

## 🚀 Features

1. **Requirement Upload & Classification** – Upload a PDF document and automatically classify requirements into SDLC phases.
2. **AI Code Generator** – Generate production-ready code from natural language prompts.
3. **Bug Fixer** – Detect and fix bugs in uploaded source code.
4. **Test Case Generator** – Automatically create test cases for given requirements or code.
5. **Code Summarizer** – Summarize and explain code functionality.
6. **Floating AI Chat Assistant** – Ask SDLC-related questions in real-time.

---

## 📂 Project Structure

```
SmartSDLC/
│
├── SmartSDLC_Backend.py   # Backend Flask API (Google Colab compatible)
├── index.html             # Frontend Web UI
└── README.md              # Documentation
```

---

## 🛠️ Requirements

Backend dependencies:
```bash
flask
flask-cors
PyMuPDF
transformers
torch
accelerate
huggingface_hub
requests
langchain
pyngrok
```

You will also need:
- A **Hugging Face API Key**
- An **ngrok auth token**

---

## 📖 Setup & Deployment (Google Colab + Flask)

### 1️⃣ Open Google Colab
- Upload `SmartSDLC_Backend.py` to your Google Colab environment.

### 2️⃣ Install Required Packages
Add at the top of your Colab cell:
```python
!pip install flask flask-cors PyMuPDF transformers torch accelerate huggingface_hub requests langchain pyngrok
```

### 3️⃣ Update Configuration
In `SmartSDLC_Backend.py`:
```python
class Config:
    HUGGINGFACE_API_KEY = "YOUR_HF_API_KEY"
    MODEL_NAME = "MODEL_NAME"  # e.g., "mistralai/Mistral-7B-Instruct-v0.1"
```
And set your ngrok token:
```python
ngrok.set_auth_token("YOUR_NGROK_AUTH_TOKEN")
```

### 4️⃣ Run the Backend
In Colab, execute:
```python
!python SmartSDLC_Backend.py
```
- This will output a **Public URL** from ngrok (e.g., `https://xxxx.ngrok-free.app`).

### 5️⃣ Update Frontend API URL
In `index.html`, set:
```javascript
const API_BASE_URL = 'YOUR_NGROK_PUBLIC_URL';
```

### 6️⃣ Serve the Frontend
- Open `index.html` in any browser.
- The frontend will now communicate with your Colab backend.

---

## 🌐 API Endpoints

| Endpoint                 | Method | Description |
|--------------------------|--------|-------------|
| `/api/upload-requirements` | POST   | Upload PDF & classify requirements |
| `/api/generate-code`       | POST   | Generate code from prompt |
| `/api/fix-bug`             | POST   | Fix bugs in code |
| `/api/generate-tests`      | POST   | Generate test cases |
| `/api/summarize-code`      | POST   | Summarize code |
| `/api/chat`                | POST   | AI chatbot interaction |

---

## 📌 Example Colab Deployment Flow
1. **Open Colab**
2. **Upload Backend Script**
3. **Install Dependencies**
4. **Set Hugging Face & ngrok Tokens**
5. **Run Flask Server**
6. **Copy Public URL into Frontend**
7. **Open HTML in Browser**

---

## 📷 Screenshots
*(Add screenshots of UI here)*

---

## 📝 License
This project is licensed under the MIT License.

---

## 🤝 Contributors
- **Your Name** – Developer
