# Governance Lifecycle Policy

## Purpose

This policy defines governance review, observation lifecycle, repository update discipline, and governance reporting expectations.

Use this file for:

- governance reviews;
- observation updates;
- governance update requests;
- Architect work;
- workflow or role-boundary issues;
- recurring teaching or validation failures.

## Governance Workflow

Purpose:
Maintain repository governance and learning assets.

Workflow:

Teacher / Architect
-> Governance Decision
-> Codex Prompt
-> Codex Repository Update
-> Human Review and Commit

Examples:

- `AGENTS.md`;
- `CONTEXT.md`;
- `TODO.md`;
- `learning-log.md`;
- `roadmaps/*`;
- `reviews/*`;
- `docs/*`;
- `templates/*`;
- `governance/observations.md`.

Governance Workflow must remain separate from Learning Workflow.

## Governance Update Policy

Governance files should be updated only at meaningful milestones.

Examples:

- assessment completed;
- sprint completed;
- major project milestone completed;
- significant repository change;
- repeated teaching or governance failure requiring policy correction;
- state drift that would mislead future agents;
- reusable templates or operating procedures created.

Avoid updating governance files for every study session.

Governance updates should be incremental when possible, but structural refactors are appropriate when accumulated patches create ambiguity.

## Governance Reporting Mode

When discussion enters governance-review territory, Teachers or Architects should switch from conversational mode to governance-reporting mode.

Examples:

- Governance Feedback;
- Governance Review;
- Governance Observation;
- Governance Update Request;
- Sprint Closure Review;
- Handover.

Expected outputs include:

- Governance Feedback Package;
- Observation Entry;
- Governance Update Request;
- Closure Package;
- Handover Package.

Repository-oriented reporting should be preferred over conversational reflection.

## Observation Lifecycle

Observations should eventually become:

- Accepted;
- Rejected;
- Retired.

Occurrence lifecycle:

- occurrence count 1: Observation
- occurrence count 2 or more: Governance Review Required

Once an issue has appeared multiple times, continued observation is no longer the preferred action.

A governance review should determine whether:

- governance changes are required;
- governance changes are not required;
- an existing rule already covers the issue;
- the observation should be retired.

The goal is to prevent indefinite observation of recurring issues.

## Observation Queue Discipline

`governance/observations.md` should remain small.

Do not use it for general ideas or brainstorming.

New observations should be specific, governance-relevant, and likely to recur.

Historical one-time observations may remain in the file after they are retired.

Each active observation should include:

- title;
- status;
- occurrences;
- first seen;
- most recent, when applicable;
- description;
- decision;
- rationale;
- disposition or next review.

## Architect Responsibilities

Architects should:

- maintain coherence across `AGENTS.md`, `CONTEXT.md`, roadmaps, reviews, observations, docs, templates, and future governance assets;
- preserve role boundaries between Learner, Teacher, Codex, and Architect;
- ensure governance remains transferable across agents and platforms;
- review whether sprint structures align with the Master Roadmap;
- detect recurring governance failures and trigger Governance Review when needed;
- protect Workflow Separation;
- ensure repository assets are created when chat-based knowledge would otherwise be lost;
- prefer small, durable governance updates over broad speculative systems;
- generate complete Codex prompts when repository updates are required.

Architects should avoid:

- becoming the default Teacher during normal learning execution;
- becoming the primary implementer of learning projects;
- changing curriculum stage ordering without a major governance review;
- expanding governance for hypothetical needs without evidence;
- overriding teacher sprint design when the issue is local teaching judgment rather than system governance;
- treating sprint completion as proof that Rust Fundamentals no longer need reinforcement;
- allowing governance discussions to remain only in chat history;
- mixing Governance Workflow with Learning Workflow.

## Handover Requirement

Every AI agent participating in this repository should be capable of generating a handover package.

At minimum, handovers should describe:

- current stage;
- completed work;
- active projects;
- current bottlenecks;
- next priorities;
- important repository changes;
- active risks.

The system should remain maintainable even if the original AI agent is no longer available.
