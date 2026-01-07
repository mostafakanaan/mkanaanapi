# mkanaanapi

A simple Django-based REST API used as a personal backend service.

## Overview

`mkanaanapi` is a lightweight Django REST API built for learning, experimentation, and real-world deployment.  
It is designed to run on a **Raspberry Pi 5** as a local self-hosted service and to **communicate directly with my personal portfolio website**.

The API is intentionally kept small and clean, focusing on reliability, clarity, and easy deployment rather than complexity.

## Architecture

- **Backend:** Django + Django REST Framework  
- **Hosting:** Self-hosted on Raspberry Pi 5  
- **Deployment:** Gunicorn + Nginx + systemd  
- **CI/CD:** GitHub Actions with a self-hosted runner on the Pi  
- **Access:** Served under `/api` (no subdomain, no CORS required)

## Purpose

This project serves multiple goals:

- Backend for personal projects and portfolio features  
- Hands-on experience with self-hosted infrastructure  
- CI/CD automation on low-power hardware (Raspberry Pi)  
- A foundation for future endpoints and integrations  

## Example Endpoint

```http
GET /api/health
```

Response:
```json
{
  "status": "ok"
}
```

## Local Development

```bash
python -m venv .venv
source .venv/bin/activate  # or .venv\Scripts\activate on Windows
pip install -r requirements.txt
python manage.py migrate
python manage.py runserver
```

## Production Notes

- Runs locally on a Raspberry Pi 5
- Reverse-proxied via Nginx
- Managed by systemd
- Automatically deployed on push to `main`

## License

MIT License
