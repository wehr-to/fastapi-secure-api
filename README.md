# ⚡ FastAPI: Security Headers + Rate-Limited Secure API

## 🔐 Purpose
Build a secure FastAPI app that protects sensitive user data with strict access controls, header enforcement, and rate-limiting to demonstrate a modern hardened API.

## 🔧 Tech Stack
- **Framework**: FastAPI
- **Security Focus**:
  - Rate limiting
  - Security headers
  - Token-based auth (API key)
  - CORS controls

## 🔍 OWASP Mapped Protections
- **A04**: Insecure Design — Enforced architecture for secure access
- **A08**: Software/Data Integrity Failures — Hardened endpoints and header validation
- **A09**: Logging & Monitoring Failures — Logging of access attempts and abuse

## 🔨 Features
- Require `X-API-KEY` header with valid token
- Enforce rate limit per IP (e.g., 10 requests/minute)
- Set security headers:
  - `Cache-Control`
  - `X-Content-Type-Options`
  - `Strict-Transport-Security`
- Log suspicious behavior to a file
- Expose `/security/logs` for audit trail access (restricted)
- Dockerized for local testing

## 🚀 Getting Started
```bash
# Clone the repo
$ git clone https://github.com/yourusername/fastapi-secure-api.git
$ cd fastapi-secure-api

# Run using Docker
$ docker-compose up --build

# Or run locally
$ python3 -m venv venv && source venv/bin/activate
$ pip install -r requirements.txt
$ uvicorn app.main:app --reload
```

## 📬 API Access
- Add header: `X-API-KEY: your-secret-key`

## ✅ To Do
- [ ] Replace memory rate limit with Redis backend
- [ ] Add IP blacklist for abuse
- [ ] Add log rotation
- [ ] Secure `/security/logs` with role-based access

## 📄 License
MIT
