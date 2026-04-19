# 🚀 Docker Data Lab

Ambiente Docker pronto para estudos, desenvolvimento e prototipação de projetos com Python e banco de dados.

Este projeto foi criado para evitar perder tempo configurando tudo do zero sempre que inicio um novo estudo ou experimento.

---

# 📦 Stack incluída

- 🐍 Jupyter Notebook
- 🐘 PostgreSQL
- 📊 pgAdmin
- 🐳 Docker Compose
- 🔗 Rede interna entre serviços
- 💾 Persistência de dados com volumes

---

# 🎯 Objetivo

Fornecer uma base reutilizável para:

- Estudos em Data Science
- Projetos com Python
- Testes com SQL
- Análise de dados
- Prototipação rápida
- Aprendizado com Docker

---

# ⚙️ Como executar

## 1. Clone o repositório

```bash
git clone https://github.com/seuusuario/docker-data-lab.git
cd docker-data-lab
```

## 2. Crie o arquivo .env

Use como base:

```bash
cp .env.example .env
```

Exemplo:

```env
PYTHON_VERSION=3.11
IMAGE_VERSION=1.0
JUPYTER_TOKEN=admin123
```

## 3. Suba os containers

```bash
docker compose up -d --build
```

---

# 🌐 Acessos

## Jupyter Notebook
http://localhost:8888

Token definido no `.env`

## pgAdmin
http://localhost:5050

Login:

- Email: admin@admin.com
- Senha: admin

## PostgreSQL

- Host: postgres
- Porta: 5432
- User: admin
- Password: admin
- Database: estudo_db

---

# 📁 Persistência

Os dados do PostgreSQL e pgAdmin ficam salvos em volumes Docker.

---

# 💡 Possíveis melhorias futuras

- Adicionar Redis
- Adicionar FastAPI
- Adicionar Airflow
- Ambiente para Machine Learning
- VS Code Dev Container
- Testes automatizados

---

# 👨‍💻 Autor

Arthur (Art)  
Desenvolvedor | IA | Automação | Python