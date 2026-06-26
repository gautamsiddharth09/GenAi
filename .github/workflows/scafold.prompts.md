# Scaffold Instructions (AI / Copilot Guardrails)

## Purpose
This repository contains a production-grade backend system. These instructions define how scaffolding, code generation, and AI-assisted development should behave to ensure consistency, safety, and maintainability.

---

## 🚨 Core Guardrails (Strict Rules)

- Do NOT generate code without understanding existing architecture
- Do NOT introduce new frameworks or libraries without explicit approval
- Do NOT refactor large modules unless explicitly requested
- Do NOT duplicate existing logic
- Do NOT bypass authentication, authorization, or validation layers
- Never hardcode secrets, credentials, or environment-specific values
- Avoid creating unnecessary abstractions

---

## 🧱 Scaffolding Principles

- Follow existing project structure strictly
- Reuse existing patterns, utilities, and helpers
- Keep scaffolding minimal and incremental
- Prefer composition over inheritance
- Ensure new modules align with domain boundaries

---

## 🏗️ Architecture Rules

- Follow Domain Driven Design (DDD) where applicable
- Keep services loosely coupled
- Avoid cross-service database access
- Use event-driven communication (Kafka / message broker) when needed
- Each service must own its own data store

---

## 📦 Code Generation Rules

- Generate only what is required for the task
- Always include:
  - Input validation
  - Error handling
  - Logging (structured)
- Ensure functions are small and single-responsibility
- Avoid premature optimization
- Ensure backward compatibility for APIs

---

## 🔐 Security Guardrails

- Validate all external inputs
- Sanitize user-provided data
- Use secure authentication mechanisms (JWT / OAuth2)
- Follow OWASP best practices
- Do not expose stack traces in production responses
- Never log sensitive information (passwords, tokens, PII)

---

## 🧪 Testing Requirements

- Write unit tests for all new business logic
- Add integration tests for APIs
- Ensure test coverage does not degrade existing baseline
- Mock external dependencies (DB, APIs, queues)
- Tests must be deterministic (no flaky behavior)

---

## 🧾 API Design Standards

- Follow REST conventions
- Use consistent naming conventions across endpoints
- Return proper HTTP status codes:
  - 200 OK
  - 201 Created
  - 400 Bad Request
  - 401 Unauthorized
  - 403 Forbidden
  - 404 Not Found
  - 500 Internal Server Error
- Support pagination, filtering, and sorting for list APIs
- Version APIs (/v1, /v2) for backward compatibility

---

## 🗃️ Database Guidelines

- Maintain schema consistency across environments
- Use migrations for all schema changes
- Index frequently queried fields
- Avoid large transactional boundaries
- Prefer read replicas for scaling reads
- Do not store business logic in the database

---

## 📊 Observability Standards

- Use structured logging (JSON format)
- Include correlation/request IDs in all logs
- Log errors with context, not just stack traces
- Emit metrics for key business flows
- Ensure tracing support (OpenTelemetry preferred)

---

## ⚙️ Performance Rules

- Avoid N+1 queries
- Use caching where appropriate (Redis preferred)
- Ensure APIs are optimized for high concurrency
- Do not introduce blocking operations in request paths
- Use async processing for heavy workloads

---

## 🤖 AI / Copilot Behavior Rules

- Always prioritize existing code patterns
- Ask clarifying questions when requirements are ambiguous
- Prefer minimal diffs over large rewrites
- Do not introduce new abstractions without justification
- Ensure generated code is production-ready, not prototype-level
- Do not assume business logic; confirm when unclear

---

## 🚀 Scaffolding Workflow

1. Understand existing module structure
2. Identify required changes or additions
3. Reuse existing patterns and utilities
4. Implement minimal working scaffold
5. Add validation, logging, and error handling
6. Add tests
7. Ensure backward compatibility

---

## 📌 Golden Rule

> “Do not build what is not needed. Extend what already exists.”