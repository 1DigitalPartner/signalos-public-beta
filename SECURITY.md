# Security Policy

SignalOS is a commercial TanziTech product currently available through a controlled public beta.

Security is a core product requirement because SignalOS can connect to external systems, prepare execution packages, and perform approval-gated writes through supported connectors.

This document explains how to report vulnerabilities safely and what information must not be disclosed publicly.

---

## Supported security scope

Security reports are currently accepted for:

- the hosted SignalOS platform at `https://app.tanzitech.com`;
- authentication and account boundaries;
- authorization and role enforcement;
- asset and report access controls;
- credit and entitlement enforcement;
- connector authorization;
- encrypted connector credential handling;
- OAuth state and callback handling;
- repository, branch, and target-file restrictions;
- operator approval controls;
- approval revocation after target changes;
- external write execution;
- branch, commit, and pull request generation;
- verification logic;
- audit records;
- cross-account or cross-tenant data isolation;
- accidental disclosure of sensitive information.

This public repository contains documentation and beta resources. The production application source code is maintained separately.

---

## Report privately

Do not create a public GitHub issue for any finding involving:

- unauthorized access;
- authentication bypass;
- privilege escalation;
- cross-account data exposure;
- cross-tenant data exposure;
- leaked secrets or credentials;
- OAuth token exposure;
- connector credential exposure;
- approval bypass;
- write-authorization bypass;
- writes to an unapproved repository, branch, or file;
- direct unapproved modification of a protected branch;
- verification without a real external write;
- remote code execution;
- injection vulnerabilities;
- sensitive internal infrastructure disclosure;
- exploitable rate-limit or abuse-prevention failures.

Public disclosure before remediation may place users, repositories, data, or connected systems at risk.

---

## Private reporting channel

Send security reports to:

`security@tanzitech.com`

Suggested subject:

`[SignalOS Security] Brief vulnerability title`

If this address is temporarily unavailable, contact:

`info@tanzitech.com`

and use the same subject prefix.

Do not attach executable files unless requested.

Do not send access tokens, passwords, private keys, session cookies, or complete customer datasets by email.

---

## Information to include

A useful security report should include:

- a clear vulnerability summary;
- the affected SignalOS area;
- the affected URL or workflow;
- the account role used during testing;
- prerequisites;
- exact reproduction steps;
- expected behavior;
- actual behavior;
- security impact;
- whether the issue was reproduced more than once;
- sanitized screenshots or logs;
- a suggested mitigation, when available.

Include the minimum evidence required to validate the issue.

---

## Evidence handling

Before sending evidence:

- redact passwords;
- redact access tokens;
- redact OAuth codes;
- redact session cookies;
- redact service credentials;
- redact private keys;
- redact unrelated customer information;
- redact confidential source code;
- redact unnecessary internal identifiers;
- crop screenshots to the affected area.

When a token or credential was exposed during testing, revoke it immediately and state that it has been revoked.

Never commit vulnerability evidence to a public repository.

---

## Safe testing rules

Security research must:

- use accounts and assets you control;
- use dedicated test repositories;
- avoid production customer data;
- avoid service disruption;
- avoid destructive actions;
- avoid persistence after testing;
- avoid accessing data beyond what is necessary to prove the issue;
- stop testing once unauthorized access is demonstrated;
- preserve evidence without expanding the impact;
- allow reasonable time for remediation before disclosure.

Do not:

- perform denial-of-service testing;
- send high-volume automated traffic;
- test third-party infrastructure without authorization;
- access another user's data beyond a minimal proof;
- modify or delete another user's data;
- merge generated pull requests in repositories you do not own;
- publish secrets or active exploit instructions;
- use the beta to deliver malware or malicious payloads.

---

## High-priority security invariants

The following behaviors are considered critical security invariants.

### Account isolation

A user must not be able to access or modify another user's:

- assets;
- scans;
- reports;
- fixes;
- applications;
- connector authorizations;
- execution records;
- credit records;
- administrative data.

### Connector isolation

Connector credentials must:

- remain encrypted at rest;
- never be returned to the browser in plaintext;
- never appear in public logs;
- remain associated with the correct account or authorization context;
- be revocable.

### Exact-target authorization

A connector write approval must apply only to the approved:

- provider;
- repository;
- base branch;
- target file;
- authorization context.

Changing a protected target should revoke prior write approval.

### Separate approvals

Connector authorization must not automatically approve an application-level external write.

Each controlled write must require an explicit operator decision.

### Protected base branch

The GitHub runtime should create an isolated branch and pull request.

It must not silently write directly to the configured base branch.

### Real-write verification

A GitHub execution must not be marked verified unless a real external write has occurred and verifiable execution metadata exists.

### Auditability

A successful external write should record enough information to identify:

- provider;
- repository;
- base branch;
- preview branch;
- target path;
- commit;
- pull request;
- execution status;
- verification status;
- relevant timestamps.

---

## Severity guidance

### Critical

Examples:

- unauthenticated account takeover;
- arbitrary cross-account access;
- exposed production secrets;
- unrestricted connector token disclosure;
- approval bypass leading to an unauthorized external write;
- arbitrary repository write;
- direct unapproved protected-branch modification;
- remote code execution.

### High

Examples:

- wrong repository, branch, or file modified;
- connector authorization attached to the wrong user;
- write approval remains valid after a protected target change;
- verification succeeds without a real write;
- persistent cross-account metadata exposure;
- sensitive audit data exposed publicly.

### Medium

Examples:

- limited authorization inconsistency;
- security-relevant information disclosure with low exploitability;
- incomplete audit metadata that weakens incident investigation;
- missing revocation feedback;
- rate-limit weakness with bounded impact.

### Low

Examples:

- non-sensitive version disclosure;
- security copy inconsistency;
- missing hardening header without a demonstrated exploit;
- minor privacy or redaction defect.

Final severity is determined after validation and impact analysis.

---

## Response process

After receiving a valid report, TanziTech aims to:

1. acknowledge receipt;
2. confirm whether the report is reproducible;
3. assess severity and affected scope;
4. contain immediate risk when necessary;
5. prepare and test remediation;
6. deploy the correction;
7. verify the fix;
8. coordinate disclosure when appropriate.

Response time depends on severity, reproducibility, and operational impact.

Beta status does not reduce the priority of valid security findings.

---

## Disclosure

Do not publicly disclose a vulnerability until:

- TanziTech confirms remediation;
- affected credentials have been revoked;
- affected users have been protected where necessary;
- a reasonable disclosure date has been coordinated.

Security fixes may be described without publishing exploit details that would put users at risk.

---

## Recognition

Researchers who submit clear, responsible, and valid reports may be acknowledged with permission.

Possible recognition includes:

- security contributor credit;
- release-note acknowledgement;
- Founding Beta Tester recognition;
- early access to security-related improvements.

SignalOS does not currently promise a monetary bug bounty.

Do not perform testing based on an assumption that compensation will be provided.

---

## Out of scope

Generally out of scope unless a concrete security impact is demonstrated:

- missing features;
- general usability problems;
- recommendations that are not commercially useful;
- documentation errors;
- self-XSS;
- clickjacking without a sensitive action;
- rate-limit observations without abuse impact;
- findings requiring compromised user credentials;
- vulnerabilities only in unsupported third-party software;
- social engineering;
- physical attacks;
- denial-of-service testing;
- automated scanner output without manual validation.

Product defects should use the public issue templates rather than the private security channel.

---

## Legal and good-faith statement

Good-faith security research that follows this policy should:

- avoid privacy violations;
- avoid data destruction;
- avoid service disruption;
- remain limited to authorized assets and accounts;
- provide TanziTech a reasonable opportunity to remediate.

This policy does not authorize testing against systems, repositories, accounts, or data that you do not own or have explicit permission to assess.

---

## Final reminder

When uncertain whether a finding is security-sensitive, report it privately first.

Do not include secrets in GitHub issues, Discussions, pull requests, screenshots, or public comments.
