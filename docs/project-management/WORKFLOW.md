# DirBalek GitHub workflow

## Work tracking

- **GitHub Issue:** one actionable task with acceptance criteria.
- **GitHub Milestone:** groups issues toward a project outcome (M1–M6 in ROADMAP.md).
- **GitHub Project:** Kanban view of the full backlog and sprint work.
- **Sprint:** one-week iteration with a goal and demonstrable deliverable.

## Board columns

1. Backlog — known work not yet prepared.
2. Ready — sufficiently specified and selected for the current sprint.
3. In Progress — actively being worked on.
4. In Review — implementation/documentation is awaiting validation.
5. Done — all acceptance criteria and Definition of Done are satisfied.

Keep work-in-progress limited to one major task at a time for this individual project.

## Recommended project fields

| Field | Type | Values |
|---|---|---|
| Status | Status | Backlog, Ready, In Progress, In Review, Done |
| Priority | Single select | P0, P1, P2 |
| Sprint | Iteration | Sprint 01 ... Sprint 10 |
| Module | Single select | API, ML, ML-Service, Infrastructure, UML/Docs |
| Work type | Single select | Feature, Bug, Task, Documentation, Research |

## Labels

Create these repository labels:

| Label | Suggested color | Meaning |
|---|---|---|
| type:feature | #1D76DB | User-visible or system capability |
| type:bug | #D73A4A | Incorrect behavior |
| type:task | #A2EEEF | Engineering task |
| type:documentation | #0075CA | Docs/UML/report |
| type:research | #D4C5F9 | Investigation/decision |
| area:api | #0052CC | Spring Boot backend |
| area:ml | #5319E7 | Training/data pipeline |
| area:ml-service | #0E8A16 | FastAPI inference |
| area:infrastructure | #FBCA04 | Docker, CI/CD, storage, monitoring |
| area:uml | #C2E0C6 | Requirements and diagrams |
| priority:P0 | #B60205 | Critical/blocking |
| priority:P1 | #D93F0B | High |
| priority:P2 | #FBCA04 | Normal |
| status:blocked | #B60205 | Waiting on dependency |

## Issue rules

- One issue should represent one independently verifiable outcome.
- Every issue must have Objective, Context, Scope, Acceptance Criteria and Deliverables.
- Use checkboxes for acceptance criteria.
- Link dependent issues in the body using GitHub issue references after they exist.
- Assign milestone, sprint, module and priority in GitHub Projects.
- Do not mark an issue Done until its acceptance criteria are verified.

## Branch naming

- feature/<issue-number>-<short-name>
- fix/<issue-number>-<short-name>
- docs/<issue-number>-<short-name>
- test/<issue-number>-<short-name>
- chore/<issue-number>-<short-name>

Examples:
- feature/42-report-review
- docs/12-class-diagram
- fix/58-jwt-audience-validation

## Commit convention

Use Conventional Commits:
- feat(api): add report review workflow
- fix(ml-service): return HTTP 400 for malformed payload
- docs(uml): add model lifecycle diagram
- test(ml): cover strict F1 promotion gate
- chore(ci): add Python test workflow

## Pull request lifecycle

Issue → branch → implementation → tests → pull request → CI → review → merge to main.

Every PR should:
- reference its issue (e.g. Closes #42);
- explain what changed and why;
- include test evidence;
- update docs/diagrams when contracts or behavior change;
- contain no credentials, tokens, private SMS data or model/data binaries.

## Definition of Done

- Acceptance criteria are met.
- Relevant tests pass.
- CI checks pass.
- Documentation and UML are updated where needed.
- No secrets or prohibited data/artifacts are committed.
- Change is merged to main.
