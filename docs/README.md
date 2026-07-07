# Documentation Directory

This directory contains durable operating documents for the learning system.

Use this file to decide which documents to load for a specific role or task.

## Directory Layout

```text
docs/
  policies/   Lifecycle, learning-execution, and repository-validation policies
  runbooks/   Human-facing operating manuals
```

## Policies

`docs/policies/` contains formal policy documents used by agents.

Read only the policy files relevant to the current task.

- `lifecycle-policy.md` — Sprint and governance states, transitions, closure, failure, reviews, observations, and handovers.
- `learning-execution-policy.md` — Teacher startup, Chinese-first teaching, checkpoints, prerequisites, and learning validation.
- `repository-validation-policy.md` — Codex boundaries, repository bridge, formal validation, Git evidence, and prompt safety.

Architect, Teacher, and Codex startup cards live in `AGENTS.md`; checked-in
role-prompt copies are intentionally not maintained.

## Runbooks

`docs/runbooks/` contains human-facing operating manuals.

- `system-operator-manual-zh.md` — Chinese operating manual for the learner.

## Usage Rule

`AGENTS.md` remains the core governance entry point.

`CONTEXT.md` remains the current-state source.

The files under `docs/` provide workflow detail and must not duplicate live sprint state.

Canonical rule ownership is defined in `AGENTS.md`. Policies, prompts, templates, runbooks, and roadmaps should reference the canonical owner and add only role-specific or task-specific detail. A duplicated summary is informational and cannot override its canonical source.
