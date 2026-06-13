# Getting Started with SignalOS

This guide explains how to join the controlled public beta, prepare a safe test environment, and complete your first SignalOS evaluation.

## 1. Choose your testing path

SignalOS supports three beta testing paths.

### Explorer

Choose this path if you want to evaluate:

- onboarding;
- asset setup;
- scan quality;
- report clarity;
- recommendation usefulness;
- commercial relevance.

No GitHub connection is required.

### Operator

Choose this path if you also want to evaluate:

- GitHub authorization;
- repository target controls;
- approval-gated execution;
- patch previews;
- isolated branches;
- commits and pull requests;
- verification and rollback information.

A dedicated GitHub test repository is strongly recommended.

### Design Partner

Choose this path if you represent:

- a B2B company;
- an agency;
- a consultancy;
- a growth team;
- a technical operations team.

Design partners evaluate SignalOS on real workflows and provide deeper product and commercial feedback.

---

## 2. Request beta access

The hosted SignalOS beta may remain invite-only while we validate capacity, safety, abuse prevention, and connector reliability.

Request controlled beta access at [app.tanzitech.com/beta](https://app.tanzitech.com/beta). Applications are reviewed manually and submission does not guarantee access.

When requesting access, be prepared to provide:

- your role;
- your company or project type;
- the testing path you want to follow;
- the type of asset you plan to evaluate;
- whether you intend to test GitHub execution;
- the result you hope SignalOS can help you achieve.

Do not include passwords, API keys, access tokens, customer records, or confidential source code.

---

## 3. Prepare a test asset

For the Explorer path, prepare one public website or digital asset you are authorized to evaluate.

Good beta assets include:

- your company website;
- a personal business site;
- a public landing page;
- a public product site;
- a public agency site;
- a non-sensitive staging website.

Do not submit an asset that you are not authorized to test.

---

## 4. Create your SignalOS account

After receiving access:

1. Open the hosted SignalOS platform.
2. Create or confirm your account.
3. Review the available beta allowance.
4. Open the dashboard.
5. Add your first asset.

Hosted platform:

`https://app.tanzitech.com`

---

## 5. Run your first scan

From the asset dashboard:

1. Select the asset you added.
2. Start a new scan.
3. Wait for the scan to complete.
4. Open the generated report.
5. Review the score, findings, evidence, and next steps.
6. Identify the three most important recommendations.

Evaluate whether:

- the findings are specific;
- the evidence is understandable;
- the priorities make commercial sense;
- the next steps are actionable;
- the language is clear to a non-expert.

---

## 6. Review a recommended fix

Open one recommendation and assess:

- the problem being described;
- the expected business impact;
- the proposed implementation;
- the target surface;
- the risk classification;
- the verification requirements;
- the rollback guidance.

Only approve a recommendation if you understand the proposed action and consider it appropriate for your test environment.

---

## 7. Generate an execution package

Depending on the recommendation and your beta access level, SignalOS may offer:

- a manual implementation package;
- a guided terminal playbook;
- a Premium Agent execution package;
- an external connector runtime.

Before continuing, review:

- the execution title;
- the intended target;
- the generated payload;
- the implementation content;
- the tracking requirements;
- the verification plan;
- the rollback instructions.

Do not continue if the proposed action, destination, or expected result is unclear.

---

## 8. Prepare a safe GitHub test repository

This section applies only to Operator testers.

Use a dedicated repository containing no production secrets, customer information, or confidential source code.

Recommended structure:

```text
signalos-test-repository/
├── README.md
└── docs/
    └── signalos-beta-test.md
```

Recommended controls:

- create the repository specifically for testing;
- use `main` only as the pull request base;
- authorize one safe Markdown or documentation file;
- do not authorize environment files;
- do not authorize deployment configuration;
- do not include credentials;
- do not include proprietary customer material;
- do not merge generated changes without reviewing them.

Safe target example:

```text
Repository: your-account/signalos-test-repository
Base branch: main
Target file: docs/signalos-beta-test.md
```

---

## 9. Test controlled GitHub execution

When testing the GitHub runtime:

1. Authorize the GitHub connector.
2. Review the requested permissions.
3. Select the exact repository.
4. Select the base branch.
5. Enter the approved target file.
6. Save the connector target.
7. Approve the target for controlled writes.
8. Return to the Premium Agent application.
9. Review the patch preview.
10. Approve the individual application.
11. Apply the external write.
12. Confirm that SignalOS created:
    - an isolated branch;
    - a real commit;
    - a pull request;
    - execution metadata;
    - rollback information.
13. Verify the result from SignalOS.

Changing the repository, branch, or file should require renewed write approval.

SignalOS should never commit directly to the base branch.

---

## 10. Review the generated pull request

Before merging anything, verify:

- the repository is correct;
- the base branch is correct;
- the preview branch is isolated;
- only the expected file changed;
- the content matches the approved preview;
- no secret or unrelated file was modified;
- the commit is attributable to the controlled workflow;
- rollback remains possible.

Closing a test pull request without merging is a valid completion path.

---

## 11. Submit structured feedback

After completing your test:

- use the bug report template for reproducible defects;
- use product feedback for clarity and value observations;
- use the GitHub connector template for authorization or execution feedback;
- use the Premium Agent template for end-to-end execution results;
- use Discussions for broader ideas and use cases;
- use the private security channel for vulnerabilities.

Never publish:

- access tokens;
- passwords;
- cookies;
- private URLs;
- internal identifiers;
- customer information;
- security-sensitive logs;
- private repository contents.

---

## 12. What a successful beta test looks like

### Explorer completion

A successful Explorer test produces:

- one completed asset scan;
- one reviewed report;
- an assessment of recommendation quality;
- structured product feedback.

### Operator completion

A successful Operator test additionally produces:

- an authorized test connector;
- an approved exact target;
- an isolated GitHub branch;
- a real commit;
- an open or closed pull request;
- a verified SignalOS application;
- structured execution feedback.

### Design Partner completion

A successful Design Partner evaluation produces:

- a real commercial use case;
- a measurable or observable outcome;
- workflow feedback;
- pricing and value feedback;
- prioritized integration requirements.

---

## Support and responsibility boundaries

SignalOS is currently a beta product.

Beta access does not guarantee:

- uninterrupted availability;
- production suitability;
- compatibility with every repository;
- suitability for regulated data;
- legal or compliance approval;
- automatic deployment safety.

Do not use beta execution features as a substitute for:

- human code review;
- access control;
- backups;
- deployment approval;
- legal review;
- security review;
- operational monitoring.

You remain responsible for reviewing and approving every change made to systems you control.

---

## Next step

Continue with the full [Testing Guide](TESTING_GUIDE.md) when it becomes available.

For security-sensitive findings, follow the private reporting process documented in [SECURITY.md](SECURITY.md).
