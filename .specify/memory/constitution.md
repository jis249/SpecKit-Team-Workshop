# SpecKit-Team-Workshop Constitution

<!--
Sync Impact Report:
- Version change: 1.3.0 → 2.0.0
- Modified principles: 
  * Principle I: Expanded to cover all shared functionality and services (not just UI components)
  * Principle III: Enhanced to include infrastructure and pipeline consistency
  * Principle IV: Expanded to include secrets management and audit trails
  * Principle V: Enhanced with automated validation requirements
- Added sections: 
  * Principle VI: CI/CD Pipeline Discipline (DevOps core)
  * Principle VII: Automated Testing Requirements (DevOps core)
  * Principle VIII: Environment Parity (DevOps core)
  * Principle IX: Configuration Management (DevOps core)
- Removed sections: Infrastructure as Code, Observability & Monitoring, Deployment Safety (simplified to focus on core essentials)
- Templates requiring updates: 
  * plan-template.md (✅ updated - added DevOps & Infrastructure Context section, expanded Constitution Check)
  * spec-template.md (✅ updated - added comprehensive Non-Functional Requirements section)
  * tasks-template.md (✅ updated - added Phase 2.5 DevOps Foundation, expanded deployment tasks, added Production Readiness phase)
- Follow-up TODOs: none
-->

## Core Principles

### I. Component & Service Reuse
All shared functionality MUST use common implementations. No duplication of UI components, services, utilities, or infrastructure modules.

### II. Global CSS
All CSS MUST be defined globally or in shared stylesheets. No hardcoded styles or inline CSS.

### III. Structure Adherence
All code, infrastructure, and documentation MUST follow defined project structure. Deviations require approval.

### IV. Security & Secrets
- No PII/sensitive data in logs or code
- All secrets in secure vaults (never in version control)
- Encryption in transit (TLS 1.2+) and at rest
- Security scanning in CI/CD pipelines

### V. Git Discipline
- Conventional Commits format (feat:, fix:, refactor:, docs:, test:, chore:, ci:)
- Feature branches only (never commit to main/master)
- PR review required before merge
- No secrets, large binaries, or debugging code in commits

### VI. CI/CD Pipelines
- Automated pipelines for all services (lint, test, security scan, build)
- Manual approval gates for production
- Failed builds block merges
- Build time <10 minutes

### VII. Automated Testing
- Unit tests >80% coverage
- Integration, contract, and e2e tests for critical paths
- Tests run in CI on every commit
- Test failures block merges

### VIII. Environment Parity
- Dev, staging, prod maintain parity (topology, versions, dependencies)
- Differences limited to config values (env vars)
- Containerization eliminates "works on my machine"

### IX. Configuration Management
- 12-factor app: all config in env vars or config services
- No hardcoded configuration
- Validated at startup
- Secrets encrypted and access-controlled

## Code Review Requirements

All PRs MUST verify:
- No secrets or sensitive data
- Conventional commit format
- No redundant code
- Structure adherence
- Tests passing
- CI/CD configs valid

## Governance

**Amendments**: Require proposal, team approval, and migration plan.  
**Versioning**: MAJOR (breaking changes), MINOR (additions), PATCH (clarifications).  
**Enforcement**: Warning first, rejection on repeat. Critical violations (security) trigger immediate incident response.  
**Compliance**: Automated checks enforced. Quarterly audits conducted.

**Version**: 2.0.0 | **Ratified**: 2026-02-02 | **Last Amended**: 2026-02-02
