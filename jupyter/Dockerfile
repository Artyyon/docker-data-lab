###
### Ambiente de desenvolvimento (Jupyter) — Python 3.12
###

# Permite versionar o ambiente via build-arg (também pode vir do docker-compose/.env)
ARG PYTHON_VERSION=3.12

# Imagem base: Python leve (Debian slim)
FROM python:${PYTHON_VERSION}-slim

# Reexpõe o ARG após o FROM (necessário para usar em ENV/LABEL nesta etapa)
ARG PYTHON_VERSION

# Identificação útil do ambiente
LABEL org.opencontainers.image.title="development_environment" \
      org.opencontainers.image.description="Jupyter dev environment" \
      org.opencontainers.image.version="python-${PYTHON_VERSION}"

# Boas práticas:
# - PYTHONDONTWRITEBYTECODE: evita criar .pyc
# - PYTHONUNBUFFERED: logs em tempo real
# - TZ: timezone para logs e notebooks
ENV PYTHONDONTWRITEBYTECODE=1 \
    PYTHONUNBUFFERED=1 \
    TZ=America/Sao_Paulo \
    DEV_PYTHON_VERSION=${PYTHON_VERSION}

# Dependências do sistema:
# - build-essential: compilar dependências Python
# - git: versionamento
# - curl: debug
# - tesseract-ocr: OCR
# - tesseract-ocr-por: idioma português
# - libgl1: OpenCV / libs gráficas
RUN apt-get update && apt-get install -y --no-install-recommends \
    build-essential \
    git \
    curl \
    && rm -rf /var/lib/apt/lists/*

# Diretório de trabalho dentro do container
WORKDIR /workspace

# Atualiza pip
RUN pip install --upgrade pip

# Copia o requirements.txt primeiro (melhora cache do Docker)
COPY notebooks/requirements.txt /workspace/requirements.txt

# Instala dependências Python do projeto
RUN pip install --no-cache-dir -r requirements.txt

# Instala Jupyter Notebook
# (troque por jupyterlab se quiser)
RUN pip install --no-cache-dir notebook

# Porta padrão do Jupyter
EXPOSE 8888

# Comando padrão
# Token será injetado via docker-compose (.env)
CMD ["jupyter", "notebook", "--ip=0.0.0.0", "--port=8888", "--no-browser", "--allow-root"]