# SpecKit-Team-Workshop Constitution

<!--
Sync Impact Report:
- Version change: 1.0.0 → 1.1.0
- Modified principles: replaced template with three new non-negotiable principles
- Added sections: Additional Constraints, Development Workflow
- Removed sections: Template placeholders
- Templates requiring updates: plan-template.md, spec-template.md, tasks-template.md (✅ aligned, no direct changes needed)
- Follow-up TODOs: Set original ratification date
-->

## Core Principles

### I. Common Component Reuse (NON-NEGOTIABLE)
All shared UI/functionality MUST use common components. Redundant components are strictly prohibited. Any new component must justify why an existing one cannot be reused.

### II. Global CSS Definition (NON-NEGOTIABLE)
All CSS must be defined globally or in shared stylesheets. Hardcoded CSS values in components or inline styles are strictly forbidden. Styling must be consistent and maintainable across the project.

### III. Structure Adherence (NON-NEGOTIABLE)
All implementations MUST follow the defined project structure. Deviations require explicit approval and rationale. Consistency ensures maintainability and onboarding ease.

## Additional Constraints
All code must avoid duplication, especially for UI and styling. CSS must be managed globally. Project structure is mandatory for all features and modules.

## Development Workflow
Code reviews MUST verify:
- No redundant components
- No hardcoded CSS
- Structure adherence
Any violation requires explicit justification and team approval.

## Governance
This constitution supersedes all other practices for component, CSS, and structure management.
Amendments require documentation, team approval, and migration plan.
All PRs/reviews must verify compliance with these principles.
Versioning follows semantic rules: MAJOR for principle changes/removals, MINOR for additions, PATCH for clarifications.

**Version**: 1.1.0 | **Ratified**: TODO(RATIFICATION_DATE): original adoption date unknown | **Last Amended**: 2026-01-30
