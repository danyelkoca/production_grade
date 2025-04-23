# Production-Grade Code: Checklist & Comparison

This document provides a compact overview of what distinguishes production-ready applications from non-production prototypes. Use this as a reference or onboarding guide for building scalable, secure, and maintainable software.

---

### ✅ Production-Grade Code vs Non-Production: Practical Comparison

| Area                     | Production-Readiness Checklist | Tools & Examples | Bad Practices |
|--------------------------|-------------------------------|------------------|----------------|
| Code & Structure         | • Clear project structure and naming conventions<br>• README.md with setup, usage, and env setup<br>• Uses environment variables<br>• Uses Git | • Git<br>• VSCode<br>• EditorConfig | • All code in `main.py`, no folders, no README<br>• Ad hoc file organization<br>• No documentation<br>• Hardcoded values<br>• No version control |
| Testing                  | • Unit and integration tests<br>• Test coverage >70%<br>• CI pipeline for tests | • pytest<br>• unittest<br>• GitHub Actions | • Manually runs app and checks output in terminal<br>• Little to no tests<br>• Manual testing<br>• No CI setup |
| Dependencies             | • Lockfiles used<br>• No vulnerable dependencies<br>• Dockerfile/Makefile present | • pip<br>• requirements.txt<br>• Docker | • Dependencies installed ad hoc with no tracking<br>• Loose dependency handling<br>• Assumes local env is sufficient |
| Security                 | • No secrets in code<br>• Secrets via env or manager<br>• HTTPS and validation in place | • dotenv<br>• AWS Secrets Manager<br>• HTTPS | • API keys hardcoded in Python scripts<br>• Hardcoded secrets<br>• No HTTPS<br>• No input validation |
| Observability            | • Structured logging<br>• Error alerts<br>• Metrics and optional tracing | • Prometheus<br>• Grafana<br>• Sentry | • Only uses `print()` for debugging<br>• print() statements or none<br>• No metrics<br>• No error tracking |
| Deployment & Scalability | • Docker/K8s<br>• Horizontal scaling<br>• Load balancer used | • Docker<br>• Kubernetes<br>• NGINX | • Runs `python app.py` directly on dev laptop<br>• Local-only scripts<br>• No scaling<br>• Single-server setup |
| CI/CD & DevOps           | • Automated CI/CD<br>• Staging before prod<br>• Rollback/versioned releases | • GitHub Actions<br>• ArgoCD<br>• Jenkins | • Uploads files to server via SCP or FTP<br>• Manual deployment<br>• No rollback<br>• No staging |
| User Experience & Fail-safes | • User-friendly errors<br>• Timeouts/retries<br>• Fallback pages<br>• Health checks | • FastAPI exception handlers<br>• /health endpoint | • Displays "Internal Server Error" with no context<br>• Crashes or vague errors<br>• No timeouts<br>• No health endpoints |
| Documentation            | • Local + prod setup guides<br>• API docs<br>• Inline comments | • Swagger/OpenAPI<br>• Markdown<br>• docstrings | • Only has code comments like "# TODO fix this"<br>• No setup guide<br>• Undocumented endpoints<br>• Spaghetti code |
---
