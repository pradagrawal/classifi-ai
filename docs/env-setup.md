# 🔧 ClassiFi Environment Setup Guide

This guide ensures consistent development across local, Colab, Docker, and CI environments.

---

## 🧪 Local Setup (Python 3.10)

```bash
git clone https://github.com/pradagrawal/classifi-ai.git
cd classifi-ai
python3 -m venv .venv
source .venv/bin/activate      # or .venv\Scripts\activate on Windows
pip install -r requirements.txt
```

Use `make run` to start Streamlit or `make test` to validate modules.

---

## ☁️ Google Colab Setup (GPU Runtime)

```python
# In your first Colab cell:
!pip install -r https://raw.githubusercontent.com/pradagrawal/classifi-ai/main/requirements.txt
```

Then run notebooks in `/colab` using GPU backend.

---

## 🐳 Docker Setup

```bash
docker build -t classifi-app .
docker run -p 8501:8501 classifi-app
```

Dockerfile auto-loads `requirements.txt` for consistency.

---

## ✅ GitHub Actions / CI/CD

All workflows rely on `requirements.txt` to sync environments.