# Production-Grade Code: Checklist & Comparison

This document provides a compact overview of what distinguishes production-ready applications from non-production prototypes. Use this as a reference or onboarding guide for building scalable, secure, and maintainable software.

---

### Production-Grade Code vs Non-Production: Practical Comparison

| Area                     | Production-Readiness Checklist | Tools & Examples | Bad Practices |
|--------------------------|-------------------------------|------------------|----------------|
| Code & Structure         | • Clear project structure and naming conventions<br>• README.md with setup, usage, and env setup<br>• Uses environment variables<br>• Uses Git | • Git<br>• VSCode<br>• EditorConfig | • Flat scripts (e.g., all code in `main.py`), no structure or README<br>• Hardcoded values and no version control |
| Testing                  | • Unit and integration tests<br>• Test coverage >70%<br>• CI pipeline for tests | • pytest<br>• unittest<br>• GitHub Actions | • Relies on manual checks with minimal or no tests<br>• No CI pipeline for validation |
| Dependencies             | • Lockfiles used<br>• No vulnerable dependencies<br>• Dockerfile/Makefile present | • pip<br>• requirements.txt<br>• Docker | • Untracked or ad hoc dependency installs<br>• Relies on inconsistent local environments |
| Security                 | • No secrets in code<br>• Secrets via env or manager<br>• HTTPS and validation in place | • dotenv<br>• AWS Secrets Manager<br>• HTTPS | • Hardcoded secrets (e.g., API keys in code)<br>• No HTTPS or input validation |
| Observability            | • Structured logging<br>• Error alerts<br>• Metrics and optional tracing | • Prometheus<br>• Grafana<br>• Sentry | • No structured logging; relies on print statements or lacks any logging<br>• No metrics or error tracking implemented |
| Deployment & Scalability | • Docker/K8s<br>• Horizontal scaling<br>• Load balancer used | • Docker<br>• Kubernetes<br>• NGINX | • Runs `python app.py` directly on dev laptop<br>• Local-only scripts<br>• No scaling<br>• Single-server setup |
| CI/CD & DevOps           | • Automated CI/CD<br>• Staging before prod<br>• Rollback/versioned releases | • GitHub Actions<br>• ArgoCD<br>• Jenkins | • Uploads files to server via SCP or FTP<br>• Manual deployment<br>• No rollback<br>• No staging |
| User Experience & Fail-safes | • User-friendly errors<br>• Timeouts/retries<br>• Fallback pages<br>• Health checks | • FastAPI exception handlers<br>• /health endpoint | • Displays "Internal Server Error" with no context<br>• Crashes or vague errors<br>• No timeouts<br>• No health endpoints |
| Documentation            | • Local + prod setup guides<br>• API docs<br>• Inline comments | • Swagger/OpenAPI<br>• Markdown<br>• docstrings | • Only has code comments like "# TODO fix this"<br>• No setup guide<br>• Undocumented endpoints<br>• Spaghetti code |
