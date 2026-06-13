# SignalOS Public Beta Testing Guide

This guide defines the official test missions for the SignalOS controlled public beta.

The goal is not only to confirm that features work. We want to evaluate whether SignalOS is understandable, useful, trustworthy, safe, and commercially relevant.

---

## Testing principles

Every tester should follow these rules:

- test only assets and repositories you are authorized to use;
- do not upload secrets, customer data, credentials, or confidential source code;
- use a dedicated GitHub test repository for connector testing;
- review every proposed action before approval;
- do not merge generated pull requests without human review;
- report security issues privately;
- include reproducible evidence when reporting defects.

---

## Mission 01 — Explorer evaluation

### Objective

Determine whether a new user can understand SignalOS, add an asset, run a scan, and identify commercially useful recommendations.

### Recommended tester

- founder;
- marketer;
- consultant;
- agency operator;
- non-technical business owner.

### Estimated time

20–30 minutes.

### Required

- controlled beta access;
- one public website or digital asset you are authorized to evaluate;
- no GitHub connector required.

### Steps

1. Sign in to SignalOS.
2. Open the dashboard.
3. Add a public asset.
4. Run a scan.
5. Open the completed report.
6. Review the score, evidence, findings, and next steps.
7. Select the three recommendations that appear most valuable.
8. Open one recommendation in detail.
9. Review its implementation package and verification requirements.
10. Submit structured feedback.

### Evaluation questions

- Did you understand what SignalOS does within 60 seconds?
- Was asset onboarding clear?
- Did the scan complete without confusion?
- Were the findings specific or generic?
- Did the evidence support the recommendation?
- Were priorities commercially sensible?
- Did the recommended actions feel implementable?
- Which recommendation would you act on first?
- Which result would you pay for?
- Where did you hesitate or become blocked?

### Completion evidence

A completed Explorer mission should include:

- one completed scan;
- one reviewed report;
- one recommendation reviewed in detail;
- one product feedback submission.

---

## Mission 02 — Operator execution test

### Objective

Validate the approval-gated GitHub workflow from connector authorization through verified pull request creation.

### Recommended tester

- developer;
- technical marketer;
- automation specialist;
- product operator;
- agency technical lead.

### Estimated time

30–45 minutes.

### Required

- controlled beta access;
- access to Premium Agent testing;
- a GitHub account;
- a dedicated non-production test repository;
- a safe Markdown target file.

### Safe repository example

```text
signalos-test-repository/
├── README.md
└── docs/
    └── signalos-beta-test.md
```

### Safe target example

```text
Repository: your-account/signalos-test-repository
Base branch: main
Target file: docs/signalos-beta-test.md
```

### Steps

1. Complete Mission 01.
2. Open a recommendation that supports a Premium Agent execution package.
3. Review the generated package.
4. Confirm the target type, patch type, risk, content, tracking, and rollback instructions.
5. Open the GitHub connector setup.
6. Authorize GitHub.
7. Select the dedicated test repository.
8. Select `main` as the pull request base.
9. Set the safe Markdown target file.
10. Save the connector target.
11. Approve the exact target for controlled writes.
12. Return to the Premium Agent application.
13. Review the patch preview.
14. Approve the individual application.
15. Apply the external write.
16. Confirm that SignalOS created:
    - an isolated branch;
    - one real commit;
    - one pull request;
    - external execution metadata;
    - rollback instructions.
17. Review the generated pull request on GitHub.
18. Return to SignalOS.
19. Verify the result.
20. Submit connector and execution feedback.

### Required safety assertions

Confirm all of the following:

- no direct commit was made to `main`;
- the preview branch is separate;
- the pull request base is correct;
- only the approved file changed;
- the generated content matches the approved preview;
- no unrelated file was modified;
- changing repository, branch, or file requires renewed write approval;
- verification was unavailable before the real external write;
- the application records branch, commit, and pull request metadata;
- the generated change can be rolled back by closing the pull request or reverting the commit.

### Completion evidence

A completed Operator mission should include:

- one authorized test connector;
- one approved exact target;
- one approved application;
- one isolated branch;
- one real commit;
- one open or closed pull request;
- one verified SignalOS application;
- one structured execution feedback submission.

---

## Mission 03 — Trust and clarity review

### Objective

Evaluate whether the approval model is understandable enough for a user to trust the system.

### Estimated time

10–20 minutes.

### Review areas

Assess:

- connector authorization language;
- repository, branch, and file target controls;
- distinction between connector approval and application approval;
- patch preview clarity;
- external write status;
- verification status;
- rollback instructions;
- audit information;
- warnings and locked states.

### Evaluation questions

- Was it obvious when a real external write would happen?
- Did you understand what the connector was authorized to do?
- Was the exact target visible before approval?
- Did changing the target clearly revoke prior approval?
- Was the individual application approval distinct from connector approval?
- Was the generated patch understandable before execution?
- Could you identify the created branch, commit, and pull request?
- Did the verified state feel justified?
- Did any label or button create false confidence?
- What would make you trust the workflow more?

---

## Mission 04 — Recommendation quality review

### Objective

Evaluate whether SignalOS produces recommendations that are commercially useful rather than generic.

### Review at least five recommendations

For each recommendation, score:

- specificity;
- evidence quality;
- business relevance;
- implementation clarity;
- prioritization;
- verification clarity;
- expected value.

Use a 1–5 scale:

```text
1 = unusable
2 = weak
3 = acceptable
4 = strong
5 = excellent
```

### Questions

- Does the recommendation describe a real observable problem?
- Is the evidence connected to the problem?
- Is the proposed fix specific enough to implement?
- Is the expected impact credible?
- Is the priority appropriate?
- Is the verification plan objective?
- Is the recommendation materially different from generic AI advice?

---

## Mission 05 — Design Partner evaluation

### Objective

Assess SignalOS against a real commercial workflow and determine whether it creates measurable value.

### Recommended participant

- B2B company;
- agency;
- consultancy;
- growth team;
- revenue operations team;
- technical marketing team.

### Evaluation period

One to four weeks.

### Required use case

Choose one real goal, for example:

- improve website conversion;
- identify missing audience capture;
- improve campaign routing;
- repair analytics coverage;
- standardize client audits;
- convert recommendations into implementation packages;
- reduce manual handoff between marketing and development.

### Capture before and after

Document:

- original problem;
- baseline process;
- time normally required;
- tools normally used;
- SignalOS findings;
- approved actions;
- implementation result;
- measurable or observable outcome;
- time saved;
- missing integrations;
- willingness to pay.

### Commercial feedback

Provide:

- the most valuable workflow;
- the least valuable workflow;
- the feature that would justify payment;
- preferred pricing model;
- expected monthly value;
- adoption blockers;
- required security or compliance controls;
- required integrations.

---

## Bug reporting standard

A useful bug report should contain:

- a clear title;
- the test mission;
- the page or workflow;
- exact reproduction steps;
- expected behavior;
- actual behavior;
- browser and operating system;
- screenshots with sensitive information removed;
- relevant timestamps;
- whether the issue is reproducible;
- business or testing impact.

Do not publish:

- access tokens;
- cookies;
- passwords;
- private repository contents;
- customer data;
- service-role keys;
- OAuth secrets;
- private internal URLs;
- unredacted identifiers that expose user or system data.

---

## Severity guide

### Critical

- unauthorized external write;
- secret exposure;
- privilege escalation;
- direct unapproved production modification;
- bypass of approval controls.

Report Critical issues privately through the process in `SECURITY.md`.

### High

- incorrect repository, branch, or file modified;
- verification shown without a real write;
- approval state not revoked after target change;
- cross-account data exposure;
- persistent connector authorization failure.

### Medium

- broken workflow with a workaround;
- incorrect recommendation metadata;
- incomplete execution audit;
- confusing approval state;
- broken beta onboarding.

### Low

- copy issue;
- visual inconsistency;
- minor documentation defect;
- non-blocking usability issue.

---

## Feedback quality standard

Useful feedback is:

- specific;
- based on an actual test;
- tied to a workflow or result;
- clear about expected behavior;
- honest about uncertainty;
- focused on user or business impact.

Weak feedback:

```text
It does not work.
```

Strong feedback:

```text
During Mission 02, after changing the approved target file, the interface still showed the connector as authorized for writes. I expected write approval to be revoked. This reduced trust because the application appeared ready to execute against a changed target.
```

---

## Test completion checklist

### Explorer

- [ ] Account access received
- [ ] Asset added
- [ ] Scan completed
- [ ] Report reviewed
- [ ] Recommendation reviewed
- [ ] Product feedback submitted

### Operator

- [ ] Explorer mission completed
- [ ] Test repository prepared
- [ ] GitHub connector authorized
- [ ] Exact target configured
- [ ] Target write approval granted
- [ ] Patch preview reviewed
- [ ] Application approved
- [ ] External write applied
- [ ] Branch confirmed
- [ ] Commit confirmed
- [ ] Pull request confirmed
- [ ] Result verified
- [ ] Execution feedback submitted

### Design Partner

- [ ] Real use case defined
- [ ] Baseline documented
- [ ] Evaluation period completed
- [ ] Outcomes recorded
- [ ] Workflow feedback submitted
- [ ] Commercial feedback submitted

---

## Final reminder

SignalOS is a controlled execution system, not a replacement for human accountability.

Review every recommendation, approval, generated change, and pull request before using the result in a production environment.
