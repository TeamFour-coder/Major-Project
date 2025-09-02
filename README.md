# Mumbai Geo-AI Backend

Backend for the Mumbai Geo-AI project. Detects new/illegal construction in Mumbai using satellite imagery analysis.

## 🚀 Quick Start

### Prerequisites

- **Docker Desktop:** Install and run [Docker Desktop](https://www.docker.com/products/docker-desktop).
- **Git:** Install Git ([https://git-scm.com/downloads](https://git-scm.com/downloads)).
- **Python 3.11+ (Optional for local development/debugging):** Install Python ([https://www.python.org/downloads/](https://www.python.org/downloads/)).

### Clone the Repository

```bash
git clone https://github.com/your-username/mumbai-geo-ai-backend.git
cd mumbai-geo-ai-backend

Run with Docker Compose (Recommended)
This starts all services (PostgreSQL, Redis, MinIO, TiTiler, your App, Worker) together.

1.Start Services:
docker-compose up
Add --build if you've made changes to Dockerfile or requirements.txt: docker-compose up --build
Add -d to run in the background: docker-compose up -d
2.Access Services:
Your App API Docs: http://localhost:8000/docs
TiTiler API Docs: http://localhost:8001/docs
MinIO Console: http://localhost:9001 (Login: minioadmin / minioadmin123)
PostgreSQL: localhost:5432 (User: mumbai_user, Pass: janmoksathi, DB: mumbai_geo_ai)
Redis: localhost:6379
3.Stop Services:
docker-compose down
Add --volumes to also remove persisted data (PostgreSQL, MinIO): docker-compose down --volumes
🛠️ Local Development (Without Docker - Limited)
For quick testing or debugging parts of the application outside Docker.

1.Create Virtual Environment:
python -m venv venv
# Windows
venv\Scripts\activate
# macOS/Linux
# source venv/bin/activate
2.Install Dependencies:
pip install --upgrade pip
pip install -r requirements.txt
Ensure Local Services are Running:
PostgreSQL (with PostGIS, database mumbai_geo_ai, user mumbai_user)
Redis
MinIO
TiTiler (on port 8001)
Run the Application:
# Make sure venv is activated
uvicorn app.main:app --reload --host 0.0.0.0 --port 8000
📁 Project Structure
mumbai-geo-ai-backend/
├── app/                   # Main application package
│   ├── __init__.py
│   ├── main.py           # FastAPI app entry point
│   ├── core/             # Core configuration and settings
│   │   ├── __init__.py
│   │   └── config.py
│   ├── db/               # Database setup and session management
│   │   ├── __init__.py
│   │   └── database.py
│   ├── models/           # SQLAlchemy models and Pydantic schemas
│   │   ├── __init__.py
│   │   ├── models.py     # SQLAlchemy models
│   │   └── schemas.py    # Pydantic schemas
│   ├── api/              # API routers and endpoints
│   │   ├── __init__.py
│   │   └── v1/
│   │       ├── __init__.py
│   │       ├── api.py
│   │       └── endpoints/
│   │           ├── __init__.py
│   │           ├── jobs.py
│   │           ├── detections.py
│   │           ├── aoi.py
│   │           ├── protected_zones.py
│   │           └── tiles.py
│   ├── services/         # Business logic layer
│   │   ├── __init__.py
│   │   ├── job_service.py
│   │   ├── queue_service.py
│   │   ├── stac_service.py
│   │   ├── ml_service.py
│   │   ├── storage_service.py
│   │   └── worker_tasks.py
│   └── utils/            # Utility functions
│       ├── __init__.py
│       └── ...
├── data/                 # Local data storage (ignored by Git)
│   ├── raw/
│   ├── processed/
│   └── models/
├── docker/               # Docker related files (if any beyond docker-compose.yml)
├── scripts/              # Utility scripts
├── tests/                # Unit and integration tests
├── venv/                 # Python virtual environment (ignored by Git)
├── .env                  # Environment variables (ignored by Git)
├── .env.example          # Example environment variables
├── .gitignore            # Files/folders to ignore in Git
├── Dockerfile            # Docker image definition for app/worker
├── docker-compose.yml    # Multi-container orchestration
├── requirements.txt      # Python dependencies
└── README.md             # This file
⚙️ Configuration
Environment variables are managed via .env file (not tracked) or directly in docker-compose.yml.

See .env.example for required variables.

🧪 Testing
(Add instructions for running tests once you have them)

📚 API Documentation
Available via Swagger UI when services are running:

App: http://localhost:8000/docs
TiTiler: http://localhost:8001/docs
🤝 Contributing
Fork the repository (if applicable).
Create a feature branch (git checkout -b feature/AmazingFeature).
Commit your changes (git commit -m 'Add some AmazingFeature').
Push to the branch (git push origin feature/AmazingFeature).
Open a Pull Request.
📞 Contact
Your Email ID : collegeprojectt26@gmail.com

Project Link: https://github.com/TeamFour-coder/Major-Project
