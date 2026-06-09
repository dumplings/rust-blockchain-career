# Governance Observation Queue

Observations should eventually become:

- Accepted
- Rejected
- Retired

The queue should remain small.

Do not use this file for general ideas or brainstorming.

Only record recurring governance observations.

---

## GOV-001

Title:
Prerequisite Awareness

Status:
Observing

Occurrences:
1

First Seen:
Sprint-02

Description:

Teacher introduced a Rust API/concept before explicit introduction.

Example:

- into()

Current Decision:

Observation only.

Rationale:

Insufficient data exists to determine whether a governance rule is needed.

Next Review:

After Sprint-03.

---

## GOV-002

Title:
Sprint Transition Rule

Status:
Observing

Occurrences:
1

First Seen:
Sprint-02 Closure

Description:

Sprint closure required additional discussion regarding:

- Closure Package
- Repository Update
- Sprint initiation conditions

Current Decision:

Observation only.

Rationale:

Further sprint data is required before formalizing governance updates.

Next Review:

After Sprint-03.

---

## GOV-003

Title:
Closure Package Requirement

Status:
Observing

Occurrences:
2

First Seen:
Sprint-01 Closure

Most Recent:
Sprint-02 Closure

Description:

Closure Packages were required before repository updates.

Current Decision:

Observation only.

Rationale:

Pattern appears to be emerging but requires additional validation.

Next Review:

After Sprint-03.

---

## GOV-005

Title:
Teaching Mode Balance

Status:
Observing

Occurrences:
1

First Seen:
Sprint-03

Description:

A teacher may overuse guided discovery and Mentor Mode for learners who possess strong general engineering experience but limited Rust engineering experience.

Potential consequence:

- reduced learning velocity;
- excessive effort spent inferring teacher intent;
- insufficient direct Rust knowledge transfer.

Question:

Should learner stage influence the balance between:

- Instructor Mode
- Mentor Mode

Current suggested balance for Rust Foundations:

Instructor Mode:
70-80%

Mentor Mode:
20-30%

Current Decision:

Observing

Rationale:

Insufficient evidence exists to determine whether this should become governance.

Next Review:

After Sprint-04.

---

## GOV-006

Title:
Workflow Context Verification

Status:
Observing

Occurrences:
1

First Seen:
Sprint-03

Description:

Execution issues occurred because the Teacher operated under an incorrect workflow context.

Examples:

- Learning Workflow vs Software-Team Workflow
- Governance Workflow vs Conversation Workflow

Question:

Should future governance require explicit workflow-context verification?

Possible examples:

- Learning Workflow
- Governance Workflow
- Review Workflow
- Takeover Workflow

Current Decision:

Observing

Rationale:

Evidence suggests a workflow-context problem.

However, only one sprint has demonstrated this issue.

Additional evidence is required before modifying startup procedures.

Next Review:

After Sprint-04.
