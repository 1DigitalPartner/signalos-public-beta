# Changelog

All notable public-beta changes to SignalOS documentation, testing workflows, and externally visible capabilities will be recorded in this file.

This changelog covers the public beta program and public-facing product milestones. It does not expose private implementation details, credentials, internal infrastructure, or proprietary source code.

The format is inspired by Keep a Changelog and uses calendar-based public beta entries.

---

## [Unreleased]

### Added

- Public beta documentation hub.
- Explorer testing mission.
- Operator execution mission.
- Trust and approval review mission.
- Recommendation quality review mission.
- Design Partner evaluation framework.
- Structured feedback guide.
- Private security reporting policy.
- Product roadmap.
- Public issue and discussion templates.
- Public screenshots and end-to-end execution evidence.

### Planned

- Public beta access request workflow.
- Founding Beta Tester onboarding.
- Public beta cohort management.
- Additional connector test missions.
- Outcome measurement documentation.
- Public release notes tied to verified product changes.

---

## [2026-06-13] — Public beta preparation

### Added

- Official `signalos-public-beta` repository.
- Product positioning for SignalOS by TanziTech.
- Controlled public beta model.
- Public explanation of approval-gated execution.
- `README.md`.
- `GETTING_STARTED.md`.
- `TESTING_GUIDE.md`.
- `FEEDBACK_GUIDE.md`.
- `SECURITY.md`.
- `PRODUCT_ROADMAP.md`.
- `DESIGN_PARTNER_PROGRAM.md`.

### Validated

- GitHub OAuth authorization.
- Encrypted connector credential storage.
- Exact repository, branch, and target-file controls.
- Automatic write-approval revocation after target changes.
- Separate connector and application approvals.
- Isolated execution branch creation.
- Real commit creation.
- Pull request creation.
- Execution metadata normalization.
- Verification only after a real external write.
- Rollback through pull request closure or commit reversion.

### End-to-end evidence

The first complete Premium Agent GitHub execution validation produced:

- an approved recommendation;
- an execution-ready Premium Agent package;
- an approved exact GitHub target;
- an isolated branch;
- a real commit;
- pull request `#1`;
- a verified external-write result;
- complete execution metadata.

No direct write was made to the configured base branch.

---

## Public changelog policy

Entries should describe:

- new public beta capabilities;
- material workflow changes;
- security-model changes;
- connector behavior changes;
- public documentation changes;
- breaking changes;
- deprecations;
- important fixes affecting tester trust or execution safety.

Entries should not include:

- secrets;
- private architecture details;
- customer information;
- private incident data;
- unpatched vulnerability details;
- proprietary source code;
- internal credentials or identifiers.

---

## Change categories

### Added

New capabilities, documentation, workflows, connectors, or public resources.

### Changed

Material changes to existing behavior, user experience, approval flow, or documentation.

### Fixed

Corrections to defects, misleading states, missing metadata, or broken workflows.

### Security

Security improvements that can be described safely after remediation.

### Deprecated

Capabilities that remain available temporarily but are planned for removal or replacement.

### Removed

Capabilities or public resources that are no longer available.

---

## Release note quality standard

A useful release note should explain:

- what changed;
- why it matters;
- who is affected;
- whether user action is required;
- whether the security or approval model changed;
- whether existing beta tests should be repeated.

Weak:

```text
Fixed GitHub.
```

Strong:

```text
Fixed Premium Agent execution metadata so completed GitHub writes now expose the isolated branch and pull request number consistently. The application view now uses the authoritative execution state, preventing a completed write from appearing as not performed.
```

---

## Versioning approach

During controlled public beta, SignalOS may use dated milestones rather than strict semantic versioning for public documentation.

Product releases may later adopt semantic versioning or a release-train model when:

- public API contracts stabilize;
- SDKs or CLI tools are distributed;
- connector schemas become externally consumable;
- compatibility guarantees are introduced.

---

## Feedback-driven updates

Tester feedback may result in:

- documentation clarification;
- revised testing missions;
- changed roadmap priority;
- connector hardening;
- approval-flow improvements;
- recommendation-quality improvements;
- new public examples;
- new safety requirements.

High-impact changes will be reflected in this changelog after validation.
