# 📊 Client Satisfaction Measurement Survey (CSMS) System

The **Client Satisfaction Measurement Survey (CSMS) System** is a full-stack web-based platform designed to collect, analyze, and report client satisfaction data from individuals who have availed services from government agencies.

The system is built to support **digital transformation in public service delivery** by providing data-driven insights, automated reporting, and AI-assisted analysis to help government offices continuously improve service quality.

---

## 🎯 Project Vision

CSMS starts as a scalable MVP and is designed to evolve into a **full AI-powered Client Satisfaction Measurement System**, capable of:
- Supporting multiple government agencies
- Automating sentiment analysis
- Generating standardized PDF reports
- Providing real-time dashboards for decision-makers

---

## 🚀 Key Features (MVP)

### 📝 Survey Management
- Customizable client satisfaction surveys
- Support for structured and open-ended responses
- Mobile-friendly survey forms (Android & iOS browsers)

### 📊 Analytics & Reporting
- Dashboard-based monitoring of survey results
- Aggregated satisfaction metrics
- AI-powered sentiment analysis for qualitative feedback
- Automated **PDF report generation**

### 🧑‍💼 Administration & Access Control
- **Django Admin**
  - Used for internal system management
  - Model inspection, user management, and database maintenance
  - Intended for developers and system-level super administrators
- **Next.js Admin Dashboard**
  - Designed for government officials and authorized agency administrators
  - Used to monitor survey results, view analytics, and generate reports
  - Provides a modern, responsive, and user-friendly interface

### ⚙️ Technical Stack
- **Backend**: Django + Django REST Framework
- **Frontend**: Next.js (React)
- **Database**:
  - Local development: PostgreSQL (via pgAdmin)
  - Cloud deployment: Supabase
- **AI Processing**: Sentiment analysis for open-ended survey responses
- **Deployment-ready**: Docker-compatible architecture (planned)

---

## 🏗️ System Architecture Overview

The CSMS System follows a **decoupled architecture**:

- **Django Backend**
  - Handles business logic, authentication, AI analysis, and PDF generation
  - Exposes RESTful APIs for frontend consumption
  - Provides Django Admin for internal management

- **Next.js Frontend**
  - Serves as the primary user interface
  - Includes:
    - Public survey forms
    - Admin dashboard for authorized government personnel
  - Communicates with the backend exclusively via API calls

---

## 🗂 Project Structure

```

CSMS/
│
├── backend/                     # Django REST API backend
│   ├── manage.py
│   ├── requirements.txt         # Python dependencies
│   ├── .env                     # Backend environment variables (ignored in Git)
│   ├── backend/                 # Django project configuration
│   │   ├── settings.py
│   │   ├── urls.py
│   │   └── ...
│   ├── survey/                  # Core survey app (models, APIs, AI logic)
│   │   ├── models.py
│   │   ├── views.py
│   │   ├── serializers.py
│   │   ├── urls.py
│   │   └── ...
│   ├── static/
│   ├── media/                   # Generated PDF reports
│   └── ...
│
├── frontend/                    # Next.js frontend application
│   ├── package.json
│   ├── next.config.js
│   ├── public/
│   ├── app/                     # Next.js App Router
│   │   ├── survey/              # Survey pages
│   │   ├── dashboard/           # Admin dashboard (government officials)
│   │   └── ...
│   └── components/              # Reusable UI components
│
├── docs/                        # Documentation (optional)
│   ├── architecture.md
│   ├── api-design.md
│   ├── roadmap.md
│
├── .gitignore
├── README.md
└── LICENSE

````

---

## ⚙️ Local Development Setup

### 1️⃣ Clone the Repository
```bash
git clone https://github.com/<your-username>/CSMS-system.git
cd CSMS
````

---

### 2️⃣ Backend Setup (Django)

```bash
cd backend
python -m venv venv
venv\Scripts\activate   # Windows
pip install -r requirements.txt
```

Create a `.env` file inside `backend/`:

```env
DEBUG=True
SECRET_KEY=your-secret-key
DB_NAME=csms_db
DB_USER=postgres
DB_PASSWORD=yourpassword
DB_HOST=localhost
DB_PORT=5432
```

Run database migrations and create a superuser:

```bash
python manage.py migrate
python manage.py createsuperuser
python manage.py runserver
```

Backend available at:
👉 [http://127.0.0.1:8000](http://127.0.0.1:8000)
Django Admin:
👉 [http://127.0.0.1:8000/admin](http://127.0.0.1:8000/admin)

---

### 3️⃣ Frontend Setup (Next.js)

```bash
cd frontend
npm install
npm run dev
```

Create `.env.local` inside `frontend/`:

```env
NEXT_PUBLIC_API_URL=http://127.0.0.1:8000/api
```

Frontend available at:
👉 [http://localhost:3000](http://localhost:3000)

---

## 🔐 User Roles & Access Model

| Role         | Platform          | Description                               |
| ------------ | ----------------- | ----------------------------------------- |
| Super Admin  | Django Admin      | System-level control, database management |
| Agency Admin | Next.js Dashboard | View analytics, generate reports          |
| Client/User  | Next.js           | Submit survey responses                   |

---

## 🛣 Roadmap

* Role-based access control (RBAC)
* Multi-agency deployment support
* Advanced AI-driven insights & recommendations
* Dockerized production deployment
* CI/CD pipeline integration
* Government-standard CSMS reporting formats

---

## ℹ️ About the CSMS System

The CSMS System is designed to support **Philippine government agencies** in evaluating and improving service delivery through structured data collection and AI-assisted analysis.

By digitizing client satisfaction measurement and automating report generation, the system reduces manual effort, improves transparency, and enables faster, evidence-based decision-making.

---

## 📜 License

This project is licensed under the MIT License.
