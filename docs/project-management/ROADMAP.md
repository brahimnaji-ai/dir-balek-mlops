# DirBalek delivery roadmap

## Planning baseline

This roadmap preserves the 10-week Scrumban allocation in the project report. Each sprint is a one-week iteration; the work is grouped into six GitHub milestones. Sprint numbering is relative to the project plan, not a claim that a sprint has already started or finished.

## Milestones

| Milestone | Weeks | Outcome |
|---|---:|---|
| M1 — Requirements, UML & data decision | 1–2 | Approved V1 scope, requirements, UML package, architecture and initial dataset decision |
| M2 — Data engineering | 3 | Reproducible SMS ingestion, preprocessing, feature engineering and DVC/MinIO |
| M3 — ML & MLOps pipeline | 4–5 | Champion model, MLflow registry, strict F1 gate, CI/CD and rollback |
| M4 — Spring Boot backend | 6–7 | PostgreSQL-backed backend, Keycloak/JWT, reports and partner API keys |
| M5 — Integration & operations | 7–8 | FastAPI inference, WhatsApp adapter, Spring integration, drift and observability |
| M6 — Validation & delivery | 9–10 | Automated/E2E tests, performance evidence, Docker Compose, documentation and defense |

## Sprint goals

### Sprint 01 — Requirements and domain baseline (Week 1)
- Freeze V1 scope, FR1–FR10, NFRs and actors.
- Produce the use-case diagram.
- Define the domain model and class diagram.

### Sprint 02 — UML, architecture and dataset decision (Week 2)
- Complete object, sequence, state, activity and communication diagrams.
- Document module boundaries, component/deployment architecture and API contracts.
- Select/profile the initial SMS dataset and document adaptation decisions.

### Sprint 03 — Data engineering (Week 3)
- Implement ingestion, validation, preprocessing and feature engineering.
- Configure DVC with MinIO and verify clean-checkout reproducibility.

### Sprint 04 — Champion model and tracking (Week 4)
- Train TF-IDF character n-gram + Logistic Regression champion.
- Evaluate with class-level metrics and record CPU latency.
- Integrate MLflow experiment tracking and Model Registry.

### Sprint 05 — MLOps automation (Week 5)
- Implement strict candidate F1 > production F1 promotion gate.
- Automate tests/training/evaluation with GitHub Actions.
- Implement safe promotion and rollback.

### Sprint 06 — Backend foundation and security (Week 6)
- Bootstrap Spring Boot and PostgreSQL persistence.
- Integrate Keycloak JWT validation and role-based authorization.
- Implement report creation/review and confirmed-label persistence.

### Sprint 07 — Inference and channels (Week 7)
- Implement FastAPI /predict and /health.
- Integrate Spring Boot with FastAPI.
- Implement partner API-key authentication and WhatsApp sandbox adapter.

### Sprint 08 — Monitoring and reliability (Week 8)
- Generate weekly Evidently drift reports.
- Add structured logs, metrics and health checks.
- Implement anonymization and failure-handling scenarios.

### Sprint 09 — Test and stabilization (Week 9)
- Complete JUnit, pytest, Testcontainers and contract tests.
- Validate end-to-end workflows and measure NFRs.

### Sprint 10 — Delivery (Week 10)
- Verify one-command local startup with Docker Compose.
- Finalize README, runbooks, demo and report.
- Prepare defense material and record limitations.

## Scope control

- The multilingual transformer challenger is optional; the required baseline is TF-IDF character n-grams + Logistic Regression.
- Do not commit model binaries or datasets to Git. Use DVC/MinIO and MLflow.
- Keycloak owns identity/password/token issuance. Spring Security validates JWTs and enforces application authorization.
- Keep the WhatsApp provider behind a channel adapter.
- A candidate model is promoted only when its F1 is strictly greater than the current production model's F1.
- Any scope addition must be recorded as a new issue and explicitly prioritized; it must not silently expand the V1 baseline.
