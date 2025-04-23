# Production-Grade Code: Checklist & Comparison

This document provides a compact overview of what distinguishes production-ready applications from non-production prototypes. Use this as a reference or onboarding guide for building scalable, secure, and maintainable software.

---

### ✅ Production-Grade Code vs Non-Production: Practical Comparison

| Area                     | Production-Readiness Checklist | Tools & Examples | Bad Practices |
|--------------------------|-------------------------------|------------------|----------------|
| Code & Structure         | <strong>Prod:</strong> Clear project structure and naming conventions<br>README.md with setup, usage, and env setup<br>Uses environment variables<br>Uses Git<br><strong>Non-prod:</strong> Ad hoc file organization<br>No documentation<br>Hardcoded values<br>No version control | Git, VSCode, EditorConfig | All code in `main.py`, no folders, no README |
| Testing                  | <strong>Prod:</strong> Unit and integration tests<br>Test coverage >70%<br>CI pipeline for tests<br><strong>Non-prod:</strong> Little to no tests<br>Manual testing<br>No CI setup | pytest, unittest, GitHub Actions | Manually runs app and checks output in terminal |
| Dependencies             | <strong>Prod:</strong> Lockfiles used<br>No vulnerable dependencies<br>Dockerfile/Makefile present<br><strong>Non-prod:</strong> Loose dependency handling<br>Assumes local env is sufficient | pip, requirements.txt, Docker | Dependencies installed ad hoc with no tracking |
| Security                 | <strong>Prod:</strong> No secrets in code<br>Secrets via env or manager<br>HTTPS and validation in place<br><strong>Non-prod:</strong> Hardcoded secrets<br>No HTTPS<br>No input validation | dotenv, AWS Secrets Manager, HTTPS | API keys hardcoded in Python scripts |
| Observability            | <strong>Prod:</strong> Structured logging<br>Error alerts<br>Metrics and optional tracing<br><strong>Non-prod:</strong> print() statements or none<br>No metrics<br>No error tracking | Prometheus, Grafana, Sentry | Only uses `print()` for debugging |
| Deployment & Scalability | <strong>Prod:</strong> Docker/K8s<br>Horizontal scaling<br>Load balancer used<br><strong>Non-prod:</strong> Local-only scripts<br>No scaling<br>Single-server setup | Docker, Kubernetes, NGINX | Runs `python app.py` directly on dev laptop |
| CI/CD & DevOps           | <strong>Prod:</strong> Automated CI/CD<br>Staging before prod<br>Rollback/versioned releases<br><strong>Non-prod:</strong> Manual deployment<br>No rollback<br>No staging | GitHub Actions, ArgoCD, Jenkins | Uploads files to server via SCP or FTP |
| User Experience & Fail-safes | <strong>Prod:</strong> User-friendly errors<br>Timeouts/retries<br>Fallback pages<br>Health checks<br><strong>Non-prod:</strong> Crashes or vague errors<br>No timeouts<br>No health endpoints | FastAPI exception handlers, /health endpoint | Displays "Internal Server Error" with no context |
| Documentation            | <strong>Prod:</strong> Local + prod setup guides<br>API docs<br>Inline comments<br><strong>Non-prod:</strong> No setup guide<br>Undocumented endpoints<br>Spaghetti code | Swagger/OpenAPI, Markdown, docstrings | Only has code comments like "# TODO fix this" |
---
