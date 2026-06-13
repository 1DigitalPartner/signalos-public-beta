# SignalOS Public Beta Feedback Guide

This guide explains how to submit feedback that is useful, actionable, safe, and commercially relevant.

The objective is not to collect a large volume of vague comments. The objective is to understand what works, what creates trust, what blocks adoption, and what would make SignalOS valuable enough to use repeatedly or purchase.

---

## Choose the correct feedback channel

Use the channel that best matches your observation.

### Bug report

Use a bug report when:

- a workflow fails;
- the interface shows incorrect information;
- a button or action does not work;
- a scan or execution returns an unexpected error;
- an approval state is wrong;
- a connector behaves differently from the documented model;
- the issue is reproducible.

### Product feedback

Use product feedback when:

- the workflow works but is confusing;
- a recommendation feels generic;
- a report is hard to understand;
- the value is unclear;
- the interface creates hesitation;
- the product solves a problem particularly well;
- a step feels unnecessary or incomplete.

### GitHub connector feedback

Use connector feedback when evaluating:

- OAuth authorization;
- permission clarity;
- repository selection;
- branch selection;
- target-file restrictions;
- write approval;
- approval revocation;
- branch creation;
- commit creation;
- pull request creation;
- execution metadata;
- rollback clarity.

### Premium Agent execution feedback

Use this channel when evaluating:

- execution package quality;
- patch preview accuracy;
- risk classification;
- operator approval;
- external write status;
- verification;
- generated branch, commit, and pull request;
- implementation usefulness.

### Feature or integration request

Use this channel when:

- a missing capability blocks a real use case;
- another connector would materially improve the workflow;
- a new report or execution runtime would create commercial value;
- an existing workflow should support a different target or output.

### Security report

Security-sensitive findings must not be reported in a public issue.

Follow the private process in `SECURITY.md` for:

- unauthorized access;
- secret exposure;
- privilege escalation;
- approval bypass;
- cross-account data exposure;
- unintended external writes;
- connector credential problems;
- vulnerabilities that could be exploited.

---

## Before submitting feedback

Confirm that you can describe:

- what you were trying to achieve;
- which test mission you followed;
- where in the workflow the observation occurred;
- what you expected;
- what actually happened;
- why the difference mattered;
- whether the behavior is reproducible.

Remove or redact:

- tokens;
- passwords;
- cookies;
- private email addresses;
- customer data;
- internal identifiers;
- private repository names;
- confidential source code;
- non-public URLs;
- service credentials;
- screenshots containing sensitive information.

---

## Recommended feedback structure

Use this structure whenever possible.

### Context

Describe:

- your role;
- your testing path;
- your general use case;
- the asset or repository type;
- the goal you were trying to achieve.

Do not provide confidential company or customer information.

### Workflow

State:

- the test mission;
- the page or feature;
- the exact step;
- the action you performed.

### Expected result

Explain what you believed should happen.

### Actual result

Explain what happened instead.

### Impact

Describe the consequence:

- blocked completion;
- reduced trust;
- extra work;
- unclear value;
- incorrect execution;
- confusing state;
- lost time;
- commercial limitation.

### Evidence

Include only safe evidence:

- redacted screenshots;
- browser and operating system;
- timestamps;
- sanitized error messages;
- public pull request links from a dedicated test repository;
- safe reproduction steps.

### Suggested improvement

A suggestion is optional, but useful when you have a concrete idea.

---

## Product clarity feedback

SignalOS should be understandable to users who are not specialists.

Evaluate:

- whether the product purpose is clear within 60 seconds;
- whether dashboard labels are understandable;
- whether scan results use plain language;
- whether findings explain why they matter;
- whether recommendations explain what to do next;
- whether technical terms are defined;
- whether users can distinguish analysis from execution.

Useful questions:

- What did you believe SignalOS would do before your first scan?
- Did the report match that expectation?
- Which label or section was unclear?
- Which recommendation required additional explanation?
- What information was missing when you had to make a decision?

---

## Recommendation quality feedback

For each reviewed recommendation, assess:

- specificity;
- evidence;
- commercial relevance;
- implementation clarity;
- priority;
- risk;
- verification quality;
- expected value.

Recommended score:

```text
1 = unusable
2 = weak
3 = acceptable
4 = strong
5 = excellent
```

Useful comments explain why.

Weak:

```text
The recommendation was generic.
```

Strong:

```text
The recommendation identified a missing newsletter capture path, but it did not reference the existing report CTA or explain the best placement. The business problem was valid, but the implementation guidance was not specific enough to apply without additional analysis.
```

---

## Trust and approval feedback

SignalOS uses separate control layers. Feedback should evaluate whether those layers are understandable.

Review:

- connector authorization;
- exact target configuration;
- target write approval;
- individual application approval;
- external write state;
- verification state.

Questions:

- Was it clear that authorizing GitHub did not automatically approve a write?
- Was the repository, branch, and target file visible before approval?
- Did you understand why changing the target revoked write approval?
- Was it obvious when the real external write would occur?
- Could you tell whether the write had been performed?
- Did the verified state correspond to real external evidence?
- Did the workflow feel too restrictive, too permissive, or appropriate?

---

## Commercial value feedback

We need to understand whether SignalOS creates value beyond technical novelty.

Evaluate:

- time saved;
- quality improvement;
- reduced handoff work;
- clearer priorities;
- faster implementation;
- safer execution;
- better client delivery;
- better reporting;
- improved conversion or pipeline outcomes.

Questions:

- Which workflow created the most value?
- Which workflow created little or no value?
- What would you use every week?
- What would you pay for?
- What result would justify a monthly subscription?
- Which missing capability blocks adoption?
- Which integration matters most?
- Who in your organization would own the product?
- Who would approve the purchase?
- What would prevent renewal?

---

## Severity classification

### Critical

Use for:

- unauthorized external write;
- approval bypass;
- privilege escalation;
- secret exposure;
- cross-account data exposure;
- direct unapproved production modification.

Report privately.

### High

Use for:

- wrong repository modified;
- wrong branch modified;
- wrong target file modified;
- verification without a real write;
- target approval not revoked after target change;
- connector authorization attached to the wrong account.

### Medium

Use for:

- workflow failure with a workaround;
- incorrect metadata;
- incomplete audit history;
- misleading approval state;
- broken onboarding step;
- recommendation payload missing important implementation detail.

### Low

Use for:

- copy error;
- visual inconsistency;
- minor documentation problem;
- non-blocking usability issue;
- unclear but recoverable label.

---

## High-quality bug report example

```text
Title:
Write approval remains active after changing the target file

Mission:
Operator execution test

Context:
Dedicated public test repository with a Markdown target file

Steps:
1. Authorize GitHub
2. Configure repository A, branch main, file docs/test-a.md
3. Approve writes
4. Change the file to docs/test-b.md
5. Return to the application page

Expected:
Write approval should be revoked because the exact target changed.

Actual:
The connector still appears ready for external writes.

Impact:
This reduces trust because a prior approval appears reusable against a different target.

Reproducible:
Yes, repeated twice.

Evidence:
Redacted screenshot attached.
```

---

## High-quality product feedback example

```text
Area:
Scan report — Next Steps

Observation:
The recommendations are understandable, but the report does not clearly distinguish immediate fixes from longer-term improvements.

Impact:
As a founder, I understood the problems but was unsure which action should be completed first.

Suggested improvement:
Add an explicit priority reason and estimated implementation effort to each recommendation.
```

---

## High-quality commercial feedback example

```text
Use case:
Agency website audit and implementation handoff

Current process:
Approximately four hours for audit review, recommendation writing, and developer handoff.

SignalOS result:
The initial scan and implementation package reduced the preparation work to approximately 90 minutes.

Highest value:
Structured recommendations and reviewable execution packages.

Adoption blocker:
No client workspace separation yet.

Willingness to pay:
Potentially yes, if client workspaces and exportable reports are available.
```

---

## Screenshots and recordings

Before attaching visual evidence:

- crop unrelated browser content;
- remove personal email addresses;
- remove UUIDs where unnecessary;
- remove private repository names;
- remove tokens and cookies;
- remove customer data;
- verify that browser developer tools do not expose secrets;
- use a dedicated test environment.

A screenshot should show enough context to understand the issue without exposing unrelated data.

---

## Response expectations

Submitting feedback does not guarantee:

- immediate implementation;
- public disclosure of security fixes;
- a specific release date;
- acceptance of every feature request;
- continued beta access.

Reports may be:

- confirmed;
- prioritized;
- converted into roadmap work;
- closed as duplicates;
- declined with an explanation;
- moved to a private security process.

---

## Recognition

High-quality beta contributions may be recognized through:

- Founding Beta Tester acknowledgement;
- release note credit;
- early access to new connectors;
- design partner invitations;
- direct product review sessions;
- preferential early-access pricing.

Recognition is optional and will not expose a tester's identity without permission.

---

## Final checklist

Before submitting:

- [ ] I selected the correct feedback channel.
- [ ] I removed sensitive information.
- [ ] I described the test mission and workflow.
- [ ] I included expected and actual behavior.
- [ ] I explained the impact.
- [ ] I added safe evidence when useful.
- [ ] I used the private process for security-sensitive findings.
