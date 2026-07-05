# Language And Output Policy

## Purpose

This policy separates learner-facing conversation language from persistent artifact language.

The default model is:

- communicate with the learner in Chinese;
- preserve repository governance and cross-agent artifacts in English;
- keep professional technical terminology in English when useful.

An output's structure does not determine its language. A structured takeover verdict written in a browser chat is still learner-facing conversation unless the agent is explicitly asked to produce a repository-ready report.

## Default Language Matrix

| Output | Default language | Repository asset |
| --- | --- | --- |
| Learner-facing Teacher conversation | Chinese | No |
| Learner-facing Architect conversation | Chinese | No |
| Learner-facing Codex explanation | Chinese | No |
| Technical teaching and technical assessment | Chinese | Usually no |
| Learning notes | Chinese, English, or mixed | Optional |
| Sprint interview-prep pack | Chinese | Yes |
| Repository-ready governance document | English | Yes |
| Sprint roadmap, closure, failure review, or handover | English | Yes |
| Repository-ready takeover assessment | English | Recommended |
| Cross-agent prompt, including Codex prompt | English | Optional |

The learner may explicitly request another language for a specific conversation or artifact.

## Learner-Facing Conversation

All browser-based Teacher and Architect windows should conduct learner-facing conversation in Chinese by default.

This includes:

- startup and takeover responses;
- readiness reports;
- governance discussion;
- decisions and recommendations explained to the learner;
- clarification and follow-up questions;
- checkpoint teaching and feedback;
- summaries of Codex repository evidence.

English labels such as `READY`, `ACCEPT`, `PASS`, `BLOCKED`, or technical terms may remain in English, but their explanation should be in Chinese.

Do not switch learner-facing conversation to English merely because:

- the attached repository files are written in English;
- the output uses a formal heading or verdict;
- the topic is governance;
- the agent is producing a structured response;
- a cross-agent prompt will be included later in the response.

## Teaching And Assessment

Technical teaching and assessment must be conducted primarily in Chinese unless English communication is an explicit learning objective.

During Chinese teaching, every English technical term, professional phrase, abbreviation, protocol concept, ecosystem-specific label, and Rust, API, library, or tool term must receive an inline Chinese explanation or short Chinese paraphrase when first used in a checkpoint. The trigger is technical English use, not a Teacher judgment that the term is important enough. Literal identifiers, commands, and syntax may remain unchanged, but their role or meaning must still be explained in Chinese on first use.

Preferred introduction form:

`English professional term (Chinese professional translation)`

Terminology should be introduced at the point of use, not as a front-loaded glossary that the learner must remember for later instruction.

After introduction, English technical terms may remain in use, but the surrounding explanation must stay Chinese-first. When several English technical terms appear in one sentence or paragraph, reduce the terminology density, add Chinese scaffolding, or rewrite the passage in Chinese-first form even when some terms were introduced earlier. Repeat a short Chinese explanation or paraphrase when a term is cognitively important, ambiguous, or likely to affect comprehension. Do not force awkward translations.

Later instruction must not depend on memorizing an earlier glossary. Technical English should support technical understanding rather than become an implicit English assessment unless the sprint explicitly selects English training as an objective.

Technical knowledge and English ability must not be assessed together unless the sprint explicitly includes English training.

## Learning Notes

Learning notes may use Chinese, English, or mixed language according to learning effectiveness. Technical terminology may remain in English.

## Persistent Repository Assets

Repository-ready governance assets should be written in English by default for cross-agent interoperability.

This includes:

- `README.md`, `AGENTS.md`, `CONTEXT.md`, and `TODO.md`;
- policies, templates, and runbooks when their established format requires it;
- Master Roadmap and sprint roadmaps;
- specification reviews;
- sprint closures and failure reviews;
- governance decisions and observations;
- handovers;
- formal takeover assessment documents intended for repository storage.

A browser takeover response is not automatically a repository-ready takeover assessment. If the learner later asks to persist it, produce the repository asset in English while continuing the surrounding conversation in Chinese.

The sprint interview-prep pack required by the Teacher execution policy is a learner self-study asset and an intentional Chinese-language exception to the default language for persistent repository assets.

## Cross-Agent Prompts

Prompts intended for Teacher, Architect, Codex, Review Agent, or another AI role should be written in English by default.

Learner-facing explanation before or after the prompt should remain in Chinese. A response may therefore contain Chinese discussion plus an English copy-ready prompt.

## Current Requirements

Check `CONTEXT.md` for current learner-specific overrides, teaching language, terminology expectations, and English-training objectives.

In the absence of an explicit override:

- learner-facing conversation is Chinese;
- repository-ready governance assets are English;
- cross-agent prompts are English;
- technical terminology may remain in English.

## Interaction Efficiency

Communication should remain concise, direct, and action-oriented. Language selection must not create duplicated bilingual reports unless the learner explicitly requests both versions.
