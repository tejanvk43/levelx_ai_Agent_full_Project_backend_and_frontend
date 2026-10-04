# 🌍 AI Travel Guide

An AI-powered travel guide that provides **dynamic information and audio guides** for tourist destinations using **Google Gemini** and **Murf AI**.

Users can select a destination, choose the level of information, select a language and voice, and generate an AI-powered audio guide.

---

## ✨ Features

- 🗺️ Select popular tourist destinations
- 🔎 Search/select travel destinations
- 🤖 Generate travel information using Google Gemini
- 🎧 Convert AI-generated descriptions into audio using Murf AI
- 🌐 Multi-language support
  - English
  - Hindi
  - Tamil
  - Telugu
- 🗣️ Male and Female voice selection
- 📖 Summary and Detailed guide modes
- 🎵 Audio playback directly in the browser
- 📜 View generated travel-guide transcript
- 📱 Responsive and interactive frontend
- ☁️ Deployable frontend and backend architecture

---

## 🛠️ Tech Stack

### Frontend

- HTML
- CSS
- JavaScript

### Backend

- Python
- Flask
- Flask-CORS

### AI

- Google Gemini
- Murf AI

### Deployment

- Frontend: Netlify / Vercel
- Backend: Render

---

## 🏗️ Project Structure

```text
levelx_genai_workshop_ai_travel_guide/
│
├── Frontend/
│   ├── index.html
│   ├── index.js
│   ├── style.css
│   └── ...
│
├── Backend/
│   ├── app.py
│   ├── requirements.txt
│   └── ...
│
├── .gitignore
└── README.md
```

---

## 🔄 How It Works

```text
User selects destination
        ↓
Selects language
        ↓
Selects Summary / Detailed
        ↓
Selects Male / Female voice
        ↓
Frontend sends request
        ↓
Flask Backend
        ↓
Google Gemini generates travel guide
        ↓
Murf AI converts text to speech
        ↓
Audio converted to Base64
        ↓
Frontend receives audio
        ↓
Browser plays audio guide
```

---

# 🚀 Getting Started

## 1. Clone the Repository

```bash
git clone https://github.com/tejanvk43/levelx_genai_workshop_ai_travel_guide.git
```

```bash
cd levelx_genai_workshop_ai_travel_guide
```

---

# 🔧 Backend Setup

Go to the backend directory:

```bash
cd Backend
```

## Create Virtual Environment

### Linux / macOS

```bash
python3 -m venv env
```

Activate it:

```bash
source env/bin/activate
```

### Windows

```bash
python -m venv env
```

Activate:

```bash
env\Scripts\activate
```

---

## Install Dependencies

```bash
pip install -r requirements.txt
```

---

## 🔑 Environment Variables

Create a `.env` file inside the `Backend` folder:

```env
GEMINI_API_KEY=your_gemini_api_key
MURF_API_KEY=your_murf_api_key
```

### Important

Do **not** upload `.env` to GitHub.

The API keys should only be stored locally or in your deployment platform's environment variables.

---

# ▶️ Run Backend

From the `Backend` directory:

```bash
python3 app.py
```

The backend will run at:

```text
http://127.0.0.1:5000
```

You can test the backend by opening:

```text
http://127.0.0.1:5000/
```

Expected response:

```json
{
  "message": "Travel Guide Backend Running"
}
```

---

# 🌐 Frontend Setup

Go to the frontend directory:

```bash
cd Frontend
```

Since the frontend uses HTML, CSS and JavaScript, you can run it using a local server.

For example, with VS Code:

```text
Right Click index.html
        ↓
Open with Live Server
```

The frontend may run at:

```text
http://0.0.0.0:5500
```

or:

```text
http://127.0.0.1:5500
```

---

# 🔌 Backend API

## Generate Audio Guide

### Endpoint

```text
POST /generate-audio-guide
```

### Request

```json
{
  "place": "Taj Mahal",
  "answerType": "Summary",
  "language": "English",
  "voiceId": "en-US-matthew",
  "locale": "en-US"
}
```

### Response

```json
{
  "description": "The Taj Mahal is...",
  "audio_base64": "..."
}
```

The frontend converts the Base64 audio into an audio Blob and plays it using the browser's audio player.

---

# 🗣️ Supported Languages

| Language | Male Voice | Female Voice |
|---|---|---|
| English | Matthew | Alicia |
| Hindi | Aman | Namrita |
| Tamil | Sarvesh | Abirami |
| Telugu | Samar | Anisha |

The application uses Murf voice IDs and locale configuration for speech generation.

---

# 📖 Guide Types

## Summary

Provides a short explanation covering:

- Historical significance
- Why the destination is famous
- Major highlights
- Basic visitor information

## Detailed

Provides a longer explanation covering:

- Historical background
- Architecture
- Cultural importance
- Important events
- Interesting facts
- Visitor insights

---

# ☁️ Deployment

## Backend – Render

The Flask backend can be deployed on Render.

### Build Command

```bash
pip install -r requirements.txt
```

### Start Command

```bash
gunicorn app:app
```

Add these environment variables in Render:

```text
GEMINI_API_KEY
MURF_API_KEY
```

After deployment, Render provides a URL such as:

```text
https://your-backend.onrender.com
```

---

## Frontend – Netlify / Vercel

Deploy the `Frontend` directory to Netlify or Vercel.

Update the API URL in `index.js`:

```javascript
const GENERATE_AUDIO_GUIDE_API_URL =
  "https://your-backend.onrender.com/generate-audio-guide";
```

Make sure to use **HTTPS** for the deployed backend URL.

---

# 🔐 Security

API keys should never be placed directly inside frontend JavaScript.

### ❌ Don't do this

```javascript
const GEMINI_API_KEY = "your-secret-key";
```

### ✅ Use environment variables

```env
GEMINI_API_KEY=your-secret-key
MURF_API_KEY=your-secret-key
```

The backend communicates with Gemini and Murf so that the API keys remain hidden from users.

---

# 🧪 Example

Select:

```text
Destination: Mysore Palace
Guide Type: Summary
Language: English
Voice: Male
```

The frontend sends:

```json
{
  "place": "Mysore Palace",
  "answerType": "Summary",
  "language": "English",
  "voiceId": "en-US-matthew",
  "locale": "en-US"
}
```

Gemini generates the travel explanation.

Murf converts the explanation into speech.

The resulting audio is then played directly in the browser.

---

# 🎯 Project Goal

The goal of this project is to make travel information more **interactive, accessible and engaging** by combining generative AI with voice technology.

Instead of simply reading static information about a destination, users can listen to an AI-generated guide in their preferred language and voice.

---

# 👨‍💻 Author

**Teja Naga Venkata Kishore Pothuri**

B.Tech – Computer Science & Engineering

---

## ⭐ Project

**LevelX GenAI Workshop – AI Travel Guide**

Built using:

```text
HTML + CSS + JavaScript
          +
        Flask
          +
    Google Gemini
          +
       Murf AI
```
