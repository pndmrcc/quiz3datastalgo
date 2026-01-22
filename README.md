# QUIZ3 — Fullstack Quiz/Service App

## Overview
A fullstack application combining a Django backend (REST API) and a React frontend. The project contains the backend Django project in the repository root and a React app in the `frontend/` folder.

## Repository layout
- **Backend**: Django project with `manage.py` and SQLite database `db.sqlite3`.
- **frontend**: React app created with Create React App; source in `frontend/src`.

## Prerequisites
- Python 3.8+ and pip
- Node.js 14+ and npm or yarn
- (Optional) Git

## Backend (Django) — Setup & Run
1. Create and activate a virtual environment:

```powershell
python -m venv venv
venv\Scripts\Activate.ps1   # PowerShell
# or
venv\Scripts\activate.bat    # cmd
```

2. Install Python dependencies (if `requirements.txt` exists). If not, install Django and djangorestframework:

```powershell
pip install -r requirements.txt
# or, if requirements.txt is missing:
pip install django djangorestframework
```

3. Apply migrations and run the development server:

```powershell
python manage.py migrate
python manage.py runserver
```

The Django server runs at `http://127.0.0.1:8000/` by default. The SQLite DB files are at `db.sqlite3`.

## Frontend (React) — Setup & Run
1. Change into the frontend folder and install dependencies:

```powershell
cd frontend
npm install
```

2. Start the development server:

```powershell
npm start
```

The React app will usually open at `http://localhost:3000/` and proxy API calls to the backend if configured.

## Environment & Configuration
- If the backend expects environment variables (e.g., secret keys, API URLs), create a `.env` or set them in your shell before running.
- If you need the frontend to talk to a backend running on a different port, adjust the API base URL in `frontend/src/api/client.js` or set `proxy` in `frontend/package.json`.

## Database
This project uses SQLite (`db.sqlite3`) for local development. For production use, switch to PostgreSQL or another production-ready DB and update `settings.py` accordingly.

## Common Troubleshooting
- If migrations fail, delete stale `__pycache__` and re-run `python manage.py makemigrations` then `migrate`.
- If frontend `npm start` fails, remove `node_modules` and re-run `npm install`.

## Next Steps
- Add a `requirements.txt` for backend dependencies if missing: `pip freeze > requirements.txt`.
- Add environment variable docs and any deployment instructions.

---
If you want, I can: add `requirements.txt`, update `frontend/package.json` proxy, or run the dev servers and verify them now.
