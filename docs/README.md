# Documentation Directory

This directory contains durable operating documents for the learning system.

Use this file to decide which documents to load for a specific role or task.

## Directory Layout

```text
docs/
  policies/   Role-specific and workflow-specific governance policies
  agents/     Agent startup, takeover, and bootstrap documents
  runbooks/   Human-facing operating manuals
```

## Policies

`docs/policies/` contains formal policy documents used by agents.

Read only the policy files relevant to the current task.

- `teacher-execution-policy.md` — Teacher execution, checkpoint teaching, startup checklist, learning validation.
- `sprint-governance-policy.md` — Sprint lifecycle, roadmap ownership, closure, failed sprint handling.
- `codex-collaboration-policy.md` — Codex boundaries, repository validation, prompt safety.
- `language-output-policy.md` — Language rules and output classification.
- `governance-lifecycle-policy.md` — Governance review, observations, handovers, update discipline.

## Agents

`docs/agents/` contains documents for creating or bootstrapping specific agent roles.

- `architect-bootstrap-guide.md` — Architect role, governance scope, common failure modes.
- `architect-standard-prompt.md` — Canonical prompt for starting a new Architect Agent.
- `teacher-standard-prompt.md` — Canonical prompt for starting an accepted sprint in a browser-based Teacher window.

## Runbooks

`docs/runbooks/` contains human-facing operating manuals.

- `system-operator-manual-zh.md` — Chinese operating manual for the learner.

## Usage Rule

`AGENTS.md` remains the core governance entry point.

`CONTEXT.md` remains the current-state source.

The files under `docs/` provide role-specific operating detail and should not duplicate short-lived current sprint state.

Canonical rule ownership is defined in `AGENTS.md`. Policies, prompts, templates, runbooks, and roadmaps should reference the canonical owner and add only role-specific or task-specific detail. A duplicated summary is informational and cannot override its canonical source.
