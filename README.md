# SkillBridge AI - Competency Gap Analysis & Career Roadmap Engine
JNTUA Innovators Conclave 2026 | IC26-02-10 Open EdTech Innovation

## Folder structure
```
skillbridge-ai/
├── requirements.txt
├── backend/   main.py  engine.py  knowledge.py  database.py  .env.example
└── frontend/  index.html
```

## Run in VS Code (Windows)
```powershell
cd skillbridge-ai
python -m venv venv
venv\Scripts\activate
pip install -r requirements.txt
cd backend
copy .env.example .env      # then paste your Neon connection string into .env
uvicorn main:app --reload
```
## Run (macOS / Linux)
```bash
cd skillbridge-ai && python3 -m venv venv && source venv/bin/activate
pip install -r requirements.txt
cd backend && cp .env.example .env
uvicorn main:app --reload
```
Open http://127.0.0.1:8000  (API docs: http://127.0.0.1:8000/docs)

## Neon setup (2 minutes)
1. neon.tech -> create project -> Dashboard -> **Connect** -> copy connection string.
2. Paste into `backend/.env` as `DATABASE_URL=...` (must contain `sslmode=require`).
3. Tables are auto-created and 120 mock students are auto-seeded on first start.
If `.env` is missing, the app falls back to local SQLite so the demo never breaks.

## Scoring
Match = 70% weighted skill coverage + 30% TF-IDF cosine similarity (resume vs benchmark JD).
