# 🚀 Docker Data Lab

Modular Docker environment for studies, development, and rapid prototyping.

This repository provides two independent and reusable environments:

- 📓 Jupyter Notebook for Python studies and experiments
- 🐘 PostgreSQL + pgAdmin for database practice and local development

---

# ✨ Features

- Separate Docker Compose stacks
- Custom Jupyter image
- PostgreSQL database ready to use
- pgAdmin web interface
- Internal Docker network
- Persistent volumes
- Reusable project structure
- Fast local setup

---

# 📁 Project Structure

```text
docker-data-lab/
├── jupyter/
│   ├── docker-compose.yml
│   ├── Dockerfile
│   ├── .env.example
│   └── notebooks/
│
├── database/
│   └── docker-compose.yml
│
├── docs/
│   └── setup.md
│
├── .gitignore
└── README.md
```

---

# 📓 Jupyter Environment

Includes:

- Jupyter Notebook
- Custom Python image
- Mounted local notebooks folder
- Token authentication

## Run

```bash
cd jupyter
cp .env.example .env
docker compose up -d --build
```

## Access

http://localhost:8888

Use the token defined in `.env`.

---

# 🐘 Database Environment

Includes:

- PostgreSQL
- pgAdmin
- Persistent storage
- Shared Docker network

## Run

```bash
docker network create rede_estudo
cd database
docker compose up -d
```

## Access pgAdmin

http://localhost:5050

### Default Credentials

**pgAdmin**
- Email: admin@admin.com
- Password: admin

**PostgreSQL**
- Host: postgres
- Port: 5432
- User: admin
- Password: admin
- Database: estudo_db

---

# 🧠 Use Cases

- Data Science studies
- SQL learning
- Python experiments
- Rapid prototypes
- Docker practice
- Local database environment

---

# 🔮 Future Improvements

- Redis support
- FastAPI service
- Airflow integration
- Automated tests
- CI/CD pipeline
- Dev Containers

---

# 👨‍💻 Author

Arthur Paes Leme Stiegler (Art)

Computer Science | AI | Automation | Python