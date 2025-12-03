# 🧙‍♂️ The Hogwarts Mystery — Interactive AI Text Adventure

A cross-platform magical mystery game powered by FastAPI (Python backend) + a beautiful HTML/JS frontend. Works on Windows, macOS, and Linux.

Players explore Hogwarts, talk to NPCs, collect clues, inspect objects, and solve a mystery — all with natural language.

---

## 📁 Project Structure

```
Harry_Potter/
├── backend/
│   ├── app.py                # FastAPI backend
│   └── .env                  # Environment variables
├── app.js                    # Frontend logic
├── styles.css                # UI styling
├── hogwarts-mystery-game.html
├── requirements.txt
├── start_backend.sh          # macOS/Linux backend starter
├── start_backend.ps1         # Windows PowerShell backend starter
├── start_backend.bat         # Windows CMD backend starter
├── start_frontend.sh         # macOS/Linux frontend server
├── start_frontend.ps1        # Windows frontend server
└── README.md
```

---

## 🚀 Quick Start Guide (Works Everywhere)

### ✅ Prerequisites

- Python 3.8+
- A modern browser (Chrome, Edge, Firefox, Safari)
- Internet (only if using real LLM API)

---

## 🖥️ 1. Start the Backend (Game Engine)

Choose your OS:

### Mac / Linux

**Step 1** — Make script executable (first time only):

```bash
chmod +x start_backend.sh
```

**Step 2** — Start backend:

```bash
./start_backend.sh
```

Backend runs at: **👉 http://127.0.0.1:8000**

---

### Windows (PowerShell)

**Step 1** — Allow script execution (first time only)

Run PowerShell as Admin:

```powershell
Set-ExecutionPolicy -Scope CurrentUser RemoteSigned
```

**Step 2** — Start backend:

```powershell
.\start_backend.ps1
```

---

### Windows (CMD)

Just double-click:

```
start_backend.bat
```

or run:

```cmd
start_backend.bat
```

---

## 🌐 2. Start the Frontend

Choose your OS:

### Mac / Linux

```bash
./start_frontend.sh
```

Frontend runs at: **👉 http://127.0.0.1:3000**

---

### Windows (PowerShell)

```powershell
.\start_frontend.ps1
```

---

## 🎮 3. Play the Game

Open your browser and go to:

**👉 http://127.0.0.1:3000**

The game will automatically start a new session.

Try commands like:
- `go to library`
- `inspect shimmer`
- `talk to draco`
- `ask evelyn about the artifact`

---

## 🔧 Backend Configuration (backend/.env)

Create or edit:

```env
MODEL=gemini-2.5-flash-preview-09-2025
PORT=8000
GEMINI_API_KEY=   # Leave empty to use MOCK_MODE (no API key required)
```

**If `GEMINI_API_KEY` is empty** → Mock Mode (best for testing)

**If you add a real Google Gemini API key** → Real AI Mode

⚠️ **Restart backend after editing this file.**

---

## 🧩 How the Game Works

### Deterministic Actions

**Movement:**
```
go to courtyard
go to dumbledore's office
```

**Inspection:**
```
inspect cloak
examine the books
```

### Dialogue

```
talk to draco
ask evelyn where she was
speak with professor dumbledore
```

---

## 📦 Installing Dependencies Manually (Optional)

If not using scripts:

### macOS / Linux

```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
uvicorn backend.app:app --reload --port 8000
```

### Windows (PowerShell)

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
pip install -r requirements.txt
uvicorn backend.app:app --reload --port 8000
```

---

## 🐛 Troubleshooting

### ❌ Frontend can't connect

- Backend must be running on `127.0.0.1:8000`
- Check console for CORS messages
- Ensure `BACKEND_URL` in `app.js` matches your backend

### ❌ Backend not starting

- Check Python version: `python --version`
- Reinstall dependencies:
  ```bash
  pip install -r requirements.txt
  ```
- Ensure port 8000 isn't used by another process

### ❌ PowerShell saying "scripts disabled"

Run this once:

```powershell
Set-ExecutionPolicy -Scope CurrentUser RemoteSigned
```

### ❌ HTML direct-open gives CORS errors

You must serve via server (`http.server`), not open the file directly.

---

## 🧠 Want to Customize?

### Add new locations

Edit `LOCATIONS` in `backend/app.py`:

```python
LOCATIONS["potions classroom"] = {
    "display": "Potions Classroom",
    "description": "The scent of herbs fills the air."
}
```

### Add new NPCs

Edit `NPCS`:

```python
NPCS["snape"] = {
    "display": "Professor Snape",
    "avatar": "green",
    "persona": "Cold, sarcastic, intimidating."
}
```

---

## 🧭 Future Enhancements

- Save sessions to database
- More NPCs and locations
- RAG-driven clue retrieval
- Ending confrontation + scoring
- Fine-tuned LLM for NPC behavior

---

## 🎉 Enjoy Your Magical Journey!

Step into Hogwarts and uncover the mystery!

---

## 🤝 Contributing

Feel free to submit issues and enhancement requests!