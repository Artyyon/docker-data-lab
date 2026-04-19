# ⚙️ Setup Guide

This guide explains how to run the Docker Data Lab project locally.

---

# 📋 Requirements

Make sure you have installed:

- Docker
- Docker Compose

Check versions:

```bash
docker --version
docker compose version
```

---

# 📁 Project Structure

```text
docker-data-lab/
├── jupyter/
├── database/
├── docs/
└── README.md
```

---

# 🌐 Step 1 — Create Shared Network

Both environments use the same Docker network.

Run once:

```bash
docker network create rede_estudo
```

If the network already exists, Docker will show a warning. That is normal.

---

# 📓 Step 2 — Start Jupyter Environment

Go to the Jupyter folder:

```bash
cd jupyter
```

Create local environment file:

```bash
cp .env.example .env
```

Start containers:

```bash
docker compose up -d --build
```

Access:

```text
http://localhost:8888
```

Use the token defined in `.env`.

---

# 🐘 Step 3 — Start Database Environment

Open another terminal and run:

```bash
cd database
docker compose up -d
```

---

# 📊 Access pgAdmin

Open:

```text
http://localhost:5050
```

Login:

- Email: admin@admin.com
- Password: admin

---

# 🗄️ PostgreSQL Connection

Use these settings:

```text
Host: postgres
Port: 5432
User: admin
Password: admin
Database: estudo_db
```

---

# 🛑 Stop Containers

Inside each folder:

```bash
docker compose down
```

---

# 🔄 Rebuild Containers

If you change Dockerfile or dependencies:

```bash
docker compose up -d --build
```

---

# 🧹 Remove Volumes (Danger)

Deletes saved data:

```bash
docker compose down -v
```

---

# 🐛 Troubleshooting

## Port already in use

Check if another service is using:

- 8888
- 5050
- 5433

## Network not found

Create it again:

```bash
docker network create rede_estudo
```

## Permission issues

Try:

```bash
sudo docker compose up -d
```

---

# ✅ Ready

Your local study environment is ready for:

- Python
- SQL
- Data Science
- Docker practice
- Rapid prototyping