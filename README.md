# 📘 Project Setup Guide — Backend & Frontend

This README explains how to set up and run both the backend and frontend of the project on a local system.

---

# 🖥️ Backend Setup (Django / FastAPI)

## 📦 1. Go to backend folder

```bash
cd backend
```

## 🐍 2. Create virtual environment

```bash
python -m venv venv
```

## ▶️ 3. Activate virtual environment

### Windows (CMD)

```bash
venv\Scripts\activate
```

### Windows (PowerShell)

```bash
venv\Scripts\Activate.ps1
```

### Mac/Linux

```bash
source venv/bin/activate
```

You should see:

```
(venv)
```

## 📥 4. Install dependencies

```bash
pip install -r requirements.txt
```

If requirements.txt not available:

```bash
pip install django djangorestframework fastapi uvicorn python-dotenv
```

## ⚙️ 5. Run backend server

### Django:

```bash
python manage.py runserver
```

### FastAPI:

```bash
uvicorn main:app --reload
```

Backend will run at:

```
http://127.0.0.1:8000
```

---

# 🌐 Frontend Setup (React + Vite + Tailwind)

## 📦 1. Go to frontend folder

```bash
cd frontend
```

## 📥 2. Install dependencies

```bash
npm install
```

## 🎨 3. Run development server

```bash
npm run dev
```

Frontend will run at:

```
http://localhost:5173
```

---

# 🎯 Tailwind CSS Setup (if not installed)

Install Tailwind stable version:

```bash
npm install -D tailwindcss@3.4.1 postcss autoprefixer
npx tailwindcss init -p
```

Update `tailwind.config.js`:

```js
export default {
  content: [
    "./index.html",
    "./src/**/*.{js,ts,jsx,tsx}",
  ],
  theme: {
    extend: {},
  },
  plugins: [],
}
```

Update `src/index.css`:

```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

Make sure `main.jsx` includes:

```js
import './index.css'
```

Restart server:

```bash
npm run dev
```

---

# 🔗 Project Structure

```
project-root/
│
├── backend/
│   ├── venv/
│   ├── app/
│   ├── manage.py / main.py
│   └── requirements.txt
│
├── frontend/
│   ├── src/
│   ├── public/
│   ├── package.json
│   └── vite.config.js
│
└── README.md
```

---

# 🚀 Development Workflow

1. Start backend server
2. Start frontend server
3. Frontend calls backend APIs
4. Upload documents → backend processes → frontend displays results

---

# 🛠️ Useful Commands

## Backend

```bash
pip freeze > requirements.txt
deactivate
```

## Frontend

```bash
npm install axios
npm install lucide-react
```

---

# 📌 Notes

* Always activate `venv` before running backend
* Restart frontend server after installing new packages
* Use `.env` files for secrets and configs
* Keep backend and frontend running together for full functionality

---

# 👨‍💻 Tech Stack

**Frontend**

* React (Vite)
* Tailwind CSS
* Axios

**Backend**

* Django REST Framework / FastAPI
* Python
* REST APIs

---

# ✅ You're Ready!

Backend → API services
Frontend → UI dashboard
Both connected for full system operation.
