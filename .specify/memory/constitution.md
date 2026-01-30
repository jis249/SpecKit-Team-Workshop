# SpecKit-Team-Workshop Constitution

<!--
Sync Impact Report:
- Version change: 1.1.0 → 1.2.0
- Modified principles: None
- Added sections: Principle IV (Branching Policy), expanded Development Workflow with branching rules
- Removed sections: None
- Templates requiring updates:
  - plan-template.md ✅ (Branch field already exists, aligned with new policy)
  - spec-template.md ✅ (Feature Branch field aligned)
  - tasks-template.md ✅ (No branch references, aligned)
- Follow-up TODOs: Set original ratification date
-->

## Core Principles

### I. Common Component Reuse (NON-NEGOTIABLE)
All shared UI/functionality MUST use common components. Redundant components are strictly prohibited. Any new component must justify why an existing one cannot be reused.

### II. Global CSS Definition (NON-NEGOTIABLE)
All CSS must be defined globally or in shared stylesheets. Hardcoded CSS values in components or inline styles are strictly forbidden. Styling must be consistent and maintainable across the project.

### III. Structure Adherence (NON-NEGOTIABLE)
All implementations MUST follow the defined project structure. Deviations require explicit approval and rationale. Consistency ensures maintainability and onboarding ease.

### IV. Branching Policy (NON-NEGOTIABLE)
All development MUST follow the Git Flow branching model with industry-standard conventions.

**Protected Branches**:
- `main` — Production-ready code. Direct commits are FORBIDDEN. Only accepts merges from `release/*` or `hotfix/*` branches via approved Pull Requests.
- `develop` — Integration branch for features. Direct commits are FORBIDDEN except for minor documentation updates.

**Branch Naming Conventions**:
All branch names MUST follow this pattern: `<type>/<ticket-id>-<short-description>`

| Branch Type | Pattern | Purpose | Merges To |
|-------------|---------|---------|-----------|
| `feature/`  | `feature/ABC-123-add-login` | New features | `develop` |
| `bugfix/`   | `bugfix/ABC-456-fix-null-pointer` | Non-critical bug fixes | `develop` |
| `hotfix/`   | `hotfix/ABC-789-critical-security` | Critical production fixes | `main` AND `develop` |
| `release/`  | `release/v1.2.0` | Release preparation | `main` AND `develop` |
| `docs/`     | `docs/update-readme` | Documentation only | `develop` |
| `refactor/` | `refactor/ABC-101-cleanup-utils` | Code refactoring (no behavior change) | `develop` |
| `test/`     | `test/ABC-102-add-unit-tests` | Test additions only | `develop` |

**Merge Rules**:
- Feature branches MUST be up-to-date with `develop` before merge.
- All merges to `develop` and `main` MUST go through Pull Request with at least 1 approval.
- Squash merges are REQUIRED for feature branches to maintain clean history.
- Merge commits are REQUIRED for release and hotfix branches to preserve branch history.
- Branches MUST be deleted after successful merge.

**Rationale**: Consistent branching enables parallel development, clear release management, and traceable production deployments. This policy prevents merge conflicts, ensures code review, and maintains audit trails for compliance.

## Additional Constraints
All code must avoid duplication, especially for UI and styling. CSS must be managed globally. Project structure is mandatory for all features and modules. Branch names must include ticket/issue references for traceability.

## Development Workflow

### Code Review Requirements
Code reviews MUST verify:
- No redundant components
- No hardcoded CSS
- Structure adherence
- Correct branch naming convention
- Branch targets correct base branch
Any violation requires explicit justification and team approval.

### Branching Workflow
1. Create branch from `develop` (or `main` for hotfixes) following naming convention.
2. Implement changes with atomic commits referencing ticket ID.
3. Ensure branch is up-to-date with target branch before PR.
4. Submit Pull Request with description, testing notes, and linked issue.
5. Obtain required approvals and pass CI checks.
6. Merge using appropriate strategy (squash for features, merge commit for releases).
7. Delete source branch after successful merge.

### Release Process
1. Create `release/vX.Y.Z` branch from `develop`.
2. Perform release testing and version bumps on release branch.
3. Merge to `main` with merge commit and tag `vX.Y.Z`.
4. Back-merge to `develop` to sync release changes.
5. Delete release branch.

### Hotfix Process
1. Create `hotfix/TICKET-description` branch from `main`.
2. Implement minimal fix with tests.
3. Merge to `main` with merge commit and tag `vX.Y.Z+1`.
4. Back-merge to `develop` immediately.
5. Delete hotfix branch.

## Governance
This constitution supersedes all other practices for component, CSS, structure, and branching management.
Amendments require documentation, team approval, and migration plan.
All PRs/reviews must verify compliance with these principles.
Versioning follows semantic rules: MAJOR for principle changes/removals, MINOR for additions, PATCH for clarifications.

**Version**: 1.2.0 | **Ratified**: TODO(RATIFICATION_DATE): original adoption date unknown | **Last Amended**: 2026-01-30
