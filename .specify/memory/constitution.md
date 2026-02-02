# SpecKit-Team-Workshop Constitution

<!--
Sync Impact Report:
- Version change: 1.2.0 → 1.3.0
- Modified principles: none
- Added sections: Principle V on Git Commit Mandatory Practices
- Removed sections: none
- Templates requiring updates: plan-template.md, spec-template.md, tasks-template.md (✅ already aligned)
- Follow-up TODOs: Set original ratification date
-->

## Core Principles

### I. Common Component Reuse (NON-NEGOTIABLE)
All shared UI/functionality MUST use common components. Redundant components are strictly prohibited. Any new component must justify why an existing one cannot be reused.

### II. Global CSS Definition (NON-NEGOTIABLE)
All CSS must be defined globally or in shared stylesheets. Hardcoded CSS values in components or inline styles are strictly forbidden. Styling must be consistent and maintainable across the project.

### III. Structure Adherence (NON-NEGOTIABLE)
All implementations MUST follow the defined project structure. Deviations require explicit approval and rationale. Consistency ensures maintainability and onboarding ease.

### IV. Customer Data Security (NON-NEGOTIABLE)
Personally Identifiable Information (PII), email addresses, phone numbers, and all sensitive customer data MUST NOT be logged, exposed in debug output, or hardcoded in development code. All data handling MUST follow secure practices: encryption in transit, secure storage, and restricted access. Violations require immediate remediation and post-incident review.

### V. Git Commit Mandatory Practices (NON-NEGOTIABLE)
All commits MUST have meaningful, descriptive messages (minimum 5 words) following Conventional Commit format (feat:, fix:, refactor:, docs:, test:, style:). Commits MUST be small, logical units of work. Branch discipline is mandatory: never commit to main/master, always use feature branches (feature/*, fix/*, refactor/*). Code review before push is required. Prohibited: sensitive data, large binaries, force pushes to shared branches, commented-out code, and debugging statements. Violations require warning and amendment on first occurrence; repeated violations result in code review rejection.

## Additional Constraints
All code must avoid duplication, especially for UI and styling. CSS must be managed globally. Project structure is mandatory for all features and modules.

## Development Workflow
Code reviews MUST verify:
- No PII/sensitive data in logs, comments, or test fixtures
- Secure data handling practices implemented
- Git commit message quality and format (Conventional Commits)
- Branch discipline (no direct commits to main/master)
- Small, logical commit units
- No redundant components
- No hardcoded CSS
- Structure adherence

Any violation requires explicit justification and team approval.

## Governance
This constitution supersedes all other practices for component, CSS, structure, data security, and git commit management.
Amendments require documentation, team approval, and migration plan.
All PRs/reviews must verify compliance with these principles.
Versioning follows semantic rules: MAJOR for principle changes/removals, MINOR for additions, PATCH for clarifications.

**Version**: 1.3.0 | **Ratified**: TODO(RATIFICATION_DATE): original adoption date unknown | **Last Amended**: 2026-02-02
