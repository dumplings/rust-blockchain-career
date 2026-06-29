# Codex Collaboration Policy

## Purpose

This policy defines how Codex and other coding agents should support the learning system.

Codex is a coding assistant, repository steward, reviewer, and validation assistant. Codex should not become the primary author of learning-project implementations unless the learner explicitly requests that mode.

## Preferred Codex Activities

Codex is well-suited for:

- repository inspection;
- code review;
- architecture review;
- test review;
- compiler error analysis;
- implementation guidance;
- scope checking;
- repository governance updates;
- creating or updating repository assets from explicit prompts;
- formal repository validation reports.

## Learning-Project Boundary

During learning-project execution, Codex may:

- review code;
- inspect repository state;
- validate architecture;
- analyze compiler errors;
- review tests;
- explain implementation options.

Codex should not become the primary author of learning-project code unless the learner explicitly requests that mode.

The learner remains the primary implementer of `tx_parser`, `wallet_cli`, `mini_blockchain`, and future learning projects.

## Repository Update Boundary

Codex may update repository files when given an explicit governance or repository-update request.

Typical repository update targets:

- `AGENTS.md`;
- `CONTEXT.md`;
- `TODO.md`;
- `learning-log.md`;
- `roadmaps/*`;
- `reviews/*`;
- `docs/*`;
- `templates/*`;
- `governance/observations.md`.

Codex should keep changes scoped to the request and avoid unrelated refactors.

## Prompt Responsibility

When an agent recommends a Codex repository update, repository validation, roadmap save, closure sync, governance synchronization, or file modification, the requesting agent must provide an executable Codex prompt unless the learner explicitly says no prompt is needed.

The learner's responsibility is:

- forwarding prompts;
- reviewing results;
- asking questions;
- making governance decisions.

The learner should not be expected to design operational prompts that originate from agent workflows.

The Codex prompt should include:

1. Repository root
2. Task purpose
3. Files to inspect
4. Files allowed to modify
5. Files or repositories that must not be modified
6. Authorization status
7. Required validation or report format
8. Expected final response

Preferred workflow:

Identify Action
-> Generate Prompt
-> Execute
-> Review

If an agent identifies a required action but fails to provide an executable prompt, that is a workflow quality issue.

Telling the learner to "have Codex do it" without an executable prompt is a workflow quality failure.

## Formal Repository Validation

Formal repository validation should be reported through Codex rather than through raw learner-reported command output.

Codex repository validation verifies:

- repository state;
- file changes;
- required files and assets;
- architecture compliance;
- scope compliance;
- compiler status;
- test status;
- whether implementation matches sprint requirements.

Teachers should not use pasted learner command output as the primary repository validation path.

### Git Evidence During Validation

Codex may inspect Git status, diffs, and commit history to identify changed files, verify scope, detect accidental cross-repository changes, or clarify repository state after an update. These checks are supporting validation evidence.

This does not make Codex or other agents responsible for the learner's commit timing, commit grouping, push timing, or preservation of personal learning-project work. Codex should report Git state when it affects the requested validation or when the learner explicitly requests repository hygiene help, but should not turn commit management into a standing task.

## One Repository Per Validation Prompt

A Codex validation prompt should validate one repository or project root at a time.

The governance repository and a separate learning-project repository must be validated with separate prompts and separate verdicts.

Examples:

- validate `rust-blockchain-career` governance state in one prompt;
- validate `/Users/dumplings/workspace/wallet_cli` learning-project state in a separate prompt.

Do not combine governance repository validation and learning-project validation into one prompt unless the learner explicitly requests a cross-repository audit.

When a sprint uses a separate learning project, the Teacher should identify:

- validation target;
- working directory;
- files or behavior to inspect;
- commands to run;
- scope constraints;
- expected verdict format.

## Minimum Validation Report Format

A Codex repository validation report should include:

1. Validation target
2. Files inspected
3. Changed files
4. Scope compliance
5. Required behavior or requirement check
6. Commands run
7. Test or compiler result
8. Risks or gaps
9. Final verdict

If a command cannot be run, the report should state why and describe the remaining risk.

## Validation Workflow

Preferred validation workflow:

Student Implementation
-> Student Local Self-Check
-> Teacher-Generated Codex Validation Prompt
-> Codex Repository Validation Report
-> Teacher Learning Validation

This keeps responsibilities separated:

- learner performs implementation and self-checking;
- Codex validates repository state, test status, file changes, architecture, and scope compliance;
- Teacher validates understanding, design reasoning, and concept mastery.

After learner local self-check, a concise confirmation such as "self-check done" may be enough for the Teacher to generate the Codex validation prompt.

The learner should not be required to paste detailed raw command output by default.

The Teacher may ask for specific output when it is needed to diagnose a problem, but learner-reported output should not replace formal Codex repository validation when validation is required.

## Prompt Formatting Safety

When an agent generates a Codex prompt that creates or updates Markdown repository files, the prompt should avoid unsafe nested Markdown code fences.

Agents should not wrap an entire Markdown file body in an outer fenced code block if the file body itself contains fenced code blocks such as `rust`, `bash`, or `text`.

Preferred approaches:

- use plain prompt text without an outer Markdown fence when practical;
- use inline code for short commands such as `cargo check` and `cargo test`;
- avoid unnecessary fenced code blocks inside roadmap, review, or closure content;
- if fenced code blocks are required, ensure the outer delimiter cannot be prematurely closed by inner delimiters.

When a Codex prompt contains repository-ready Markdown content, the agent should make the prompt safe to copy and execute without Markdown truncation or fence escaping errors.

If the learner is unsure whether a Codex prompt is safe to execute, the learner may request Architect prompt-safety review before forwarding it to Codex.
