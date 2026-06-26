# 系统操作手册

本文档面向学习系统的人工操作者，也就是 Learner。

它的目的不是教 Rust，也不是给 AI Agent 的内部规范，而是帮助你在 Teacher、Codex 或 Architect 不稳定、不可用、需要替换时，仍然可以继续运行这个学习系统。

## 1. 系统目标

这个学习系统的目标是帮助你尽快具备 entry-level Rust + Blockchain 开发岗位所需的实际工程能力。

当前长期方向：

1. 优先 Solana development
2. 其次 general blockchain fundamentals
3. 最后扩展 broader Rust blockchain ecosystem

当前阶段以 `CONTEXT.md` 为准。本文档中的阶段描述如果与 `CONTEXT.md` 冲突，应以 `CONTEXT.md` 为准。

这一阶段的重点不是“看完多少资料”，而是你是否能：

- 写出小型 Rust 项目；
- 理解 ownership、borrowing、Result、error propagation、module boundary；
- 跑通 cargo check / cargo test；
- 解释自己的设计选择；
- 在 Teacher 和 Codex 的辅助下逐步建立独立工程能力。

系统的核心判断标准是 capability growth，而不是任务完成速度。

## 2. 系统角色

### Learner

Learner 是你本人。

你负责：

- 写学习项目代码；
- 先自己运行测试和调试；
- 判断学习方式是否有效；
- 审核 Teacher、Codex、Architect 的输出；
- 决定是否接受 governance update；
- 最终 commit repository changes。

你是学习进度和仓库资产的最终负责人。

### Teacher

Teacher 负责教学和学习执行。

Teacher 负责：

- 设计 sprint；
- 创建 sprint roadmap；
- 讲解 Rust / blockchain 概念；
- 评估你的理解；
- 引导 review；
- 在需要 repository update 时生成可执行的 Codex prompt。

Teacher 不应该默认替你写 learning project 代码。

当前要求：

- 技术教学主要使用中文；
- technical terminology 可以保留英文；
- English training 只有在明确作为学习目标时才加入。

### Codex

Codex 是 coding assistant 和 repository steward。

Codex 适合做：

- repository inspection；
- code review；
- compiler error 分析；
- test review；
- architecture review；
- governance document update；
- 根据 Teacher 或 Architect 提供的 prompt 修改仓库文件。

Codex 不应该默认成为 learning project 的主要实现者。

### Architect

Architect 负责系统级治理设计。

Architect 负责：

- 维护 role boundaries；
- 维护 workflow separation；
- 检查 governance 是否可交接；
- 判断 recurring observations 是否需要 governance review；
- 检查 sprint structure 是否符合 Master Roadmap；
- 在需要仓库治理更新时生成 Codex prompt。

Architect 不应该默认代替 Teacher 进行日常教学，也不应该替 Learner 写学习项目代码。

## 3. 如何启动一个新的 Sprint

启动 Sprint 前，先确认当前系统状态。

### 需要准备的文件

建议至少准备这些文件：

- `AGENTS.md`
- `CONTEXT.md`
- `TODO.md`
- `roadmaps/master-roadmap.md`
- 和当前角色相关的 `docs/policies/*policy.md`
- 最近一个 sprint roadmap，例如 `roadmaps/sprint-02.md`
- 最近一个 sprint review，例如 `reviews/sprint-02-review.md`
- 如果存在失败或治理问题，加入相关 review，例如 `reviews/sprint-03-failure-review.md`
- `governance/observations.md`
- `docs/agents/architect-bootstrap-guide.md`
- `docs/runbooks/system-operator-manual-zh.md`

### 需要上传什么文件

如果你在 ChatGPT Project 或新的 AI 会话中启动 Teacher，优先上传：

1. `AGENTS.md`
2. `CONTEXT.md`
3. `roadmaps/master-roadmap.md`
4. `docs/policies/teacher-execution-policy.md`
5. `docs/policies/sprint-governance-policy.md`
6. `docs/policies/language-output-policy.md`
7. 最近的 sprint review
8. 当前或即将创建的 sprint roadmap
9. 与当前问题相关的 governance / docs 文件

不要一次上传所有历史文件，除非新 Agent 明确需要。

### 应该创建什么类型的 Agent

启动 sprint 时，通常创建 Teacher Agent。

Teacher Agent 的任务是：

- 读取当前 repository context；
- 确认 Current Sprint；
- 确认 Current Milestone；
- 确认 Teaching Language = Chinese；
- 确认 Governance Language = English；
- 确认 Sprint Scope Constraints；
- 创建或执行 sprint roadmap；
- 在学习过程中保持 learner-first workflow。

如果当前问题是治理系统设计，而不是教学执行，才创建 Architect Agent。

## 4. 如何关闭一个 Sprint

Sprint 关闭不是简单说“完成了”。

一个正常 Sprint Closure 至少包括四层。

### Review

Review 需要确认：

- repository state 是否符合 sprint 要求；
- cargo check / cargo test 是否已经由 Learner 运行；
- Codex 是否完成 repository validation；
- Teacher 是否完成 learning validation；
- Learner 是否能解释关键设计和错误处理。

### Closure Package

Closure Package 应该记录：

- sprint 是否完成；
- 完成了哪些目标；
- 未完成哪些目标；
- 学到的能力；
- 仍然薄弱的点；
- 下一 sprint 的建议；
- 是否出现 governance observation。

Closure Package 可以由 Teacher 生成。

### Repository Update

如果 closure 产生了持久资产，需要让 Codex 更新 repository。

常见更新包括：

- `reviews/sprint-XX-review.md`
- `CONTEXT.md`
- `TODO.md`
- `learning-log.md`
- `governance/observations.md`
- 新的 roadmap 或 handover 文档

Teacher 或 Architect 应该提供完整 Codex prompt。

你负责把 prompt 转发给 Codex，并审核结果。

### 治理更新

不是每次 sprint closure 都需要 governance update。

只有在以下情况出现时，才考虑治理更新：

- 发现 recurring failure；
- 现有 workflow 不够清晰；
- role boundary 反复混乱；
- observation 出现两次或以上；
- 重要知识如果不写入仓库就会丢失；
- sprint failure review 产生了系统级教训。

治理更新应该小而明确，不要为了“更完整”而扩张系统。

## 5. 如何创建一个 Teacher

Teacher 用于日常教学、sprint planning、sprint execution、sprint review。

### 推荐 Prompt

可以使用下面的 prompt 创建新的 Teacher：

```text
You are the Teacher Agent for my rust-blockchain-career learning system.

Please read the uploaded repository governance files before teaching.

Startup requirements:

1. Verify Current Sprint.
2. Verify Current Milestone.
3. Verify Teaching Language = Chinese.
4. Verify Governance Language = English.
5. Verify Sprint Scope Constraints.
6. Confirm that the learner remains the primary implementer.
7. Follow the approved Master Roadmap and current sprint roadmap.

Teaching requirements:

- Teach primarily in Chinese.
- Keep technical terms such as ownership, borrowing, Result, trait, module, PDA, account model in English when useful.
- Follow the current stage recorded in CONTEXT.md. Continue reinforcing prior Rust fundamentals when relevant, but do not override the active stage objective.
- Prefer project-driven learning.
- Do not assign implementation work to Codex unless I explicitly request that mode.
- When performing Specification Review, follow the repository's sprint workflow contract and use `templates/specification-review-template.md` when a formal review package is needed.
- When asking me to forward work to Architect, Codex, or another agent, provide a complete cross-agent action request instead of an informal summary.
- When repository updates are needed, generate a complete executable Codex prompt.

Please begin by summarizing the current sprint context and asking only the minimum necessary questions.
```

### 需要同步哪些文件

创建 Teacher 时，优先同步：

- `AGENTS.md`
- `CONTEXT.md`
- `TODO.md`
- `roadmaps/master-roadmap.md`
- `docs/policies/teacher-execution-policy.md`
- `docs/policies/sprint-governance-policy.md`
- `docs/policies/codex-collaboration-policy.md`
- `docs/policies/language-output-policy.md`
- `templates/specification-review-template.md`
- 当前 sprint roadmap
- 最近 sprint review
- 如果相关，`reviews/sprint-03-failure-review.md`
- 如果相关，`governance/observations.md`

如果 Teacher 要做 closure，也同步：

- 当前 sprint 期间的学习记录；
- Codex review 结果；
- relevant code files；
- test output summary。

## 6. 如何创建一个 Architect

Architect 用于系统治理、角色边界、workflow、roadmap structure、agent replacement 设计。

不要用 Architect 做普通 Rust 教学。

### 推荐 Prompt

可以使用下面的 prompt 创建新的 Architect：

```text
You are the Architect Agent for my rust-blockchain-career learning system.

Your job is system governance, not normal teaching execution.

Please read the uploaded repository governance files and assume responsibility for maintaining the learning system's transferability, role boundaries, workflow separation, and governance lifecycle.

Architect responsibilities:

- Maintain coherence across AGENTS.md, policy documents, CONTEXT.md, roadmaps, reviews, observations, and docs.
- Protect the separation between Governance Workflow and Learning Workflow.
- Review whether sprint structures align with the Master Roadmap.
- Detect recurring governance failures and trigger Governance Review when needed.
- Preserve the learner as the primary implementer.
- Generate complete Codex prompts when repository governance updates are required.
- Prefer small, durable governance updates over broad speculative systems.

Constraints:

- Do not become the default Teacher unless explicitly requested.
- Do not write learning project implementations.
- Do not change stage ordering without major governance review.
- Keep governance documents in English by default.
- Keep learner-facing operational explanations in Chinese when requested.

Please begin by summarizing the current governance state, active risks, and the next recommended governance action.
```

### 需要同步哪些文件

创建 Architect 时，优先同步：

- `AGENTS.md`
- `CONTEXT.md`
- `roadmaps/master-roadmap.md`
- `governance/observations.md`
- `docs/policies/governance-lifecycle-policy.md`
- `docs/policies/sprint-governance-policy.md`
- `docs/policies/codex-collaboration-policy.md`
- `docs/policies/language-output-policy.md`
- `docs/agents/architect-bootstrap-guide.md`
- `docs/runbooks/system-operator-manual-zh.md`
- 最近的 sprint review
- 如果相关，`reviews/sprint-03-failure-review.md`
- 当前或计划中的 sprint roadmap

Architect 如果需要生成 Codex prompt，应明确说明：

- 要创建或修改哪些文件；
- 每个文件的目的；
- 输出格式；
- 是否需要 English / Chinese；
- 不能加入哪些内容。

## 7. 如何使用 Codex

Codex 适合处理 repository-facing 工作。

### 什么时候应该找 Codex

适合找 Codex 的情况：

- Teacher 或 Architect 给了 repository update prompt；
- 需要按照 `docs/policies/codex-collaboration-policy.md` 做 repository validation；
- 需要创建 governance document；
- 需要更新 `CONTEXT.md`、`TODO.md`、review、roadmap；
- 需要检查代码是否符合 sprint requirements；
- 需要 review Rust code；
- 需要分析 compiler error；
- 需要验证 cargo check / cargo test 输出；
- 需要检查 repository structure 是否一致。

### 什么时候不应该找 Codex

不适合直接找 Codex 的情况：

- 你还没有先尝试写 learning project 代码；
- 你希望 Codex 直接替你完成 learning exercise；
- 当前问题是概念理解，应该先问 Teacher；
- 当前问题需要 learning validation，应该交给 Teacher；
- governance decision 还没有形成，只是想让 Codex 猜系统应该怎么改。

一个简单判断：

- 学习和理解：找 Teacher。
- 仓库更新和代码审查：找 Codex。
- 系统治理和角色边界：找 Architect。

## 8. 常见工作流

### Sprint 启动

正常顺序：

1. 读取 `CONTEXT.md` 和 `roadmaps/master-roadmap.md`。
2. 查看最近 sprint review。
3. 创建 Teacher Agent。
4. Teacher 完成 startup checklist。
5. Teacher 做 Specification Review，并在需要正式评审时使用 `templates/specification-review-template.md`。
6. 如果需要 Architect、Codex 或其它 agent 参与，Teacher 应提供完整 cross-agent action request。
7. Teacher 创建或确认 sprint roadmap。
8. 如果 roadmap 需要入库，Teacher 生成 Codex prompt。
9. Codex 更新 repository。
10. 你 review 并 commit。
11. Sprint execution 开始。

### Sprint 关闭

正常顺序：

1. Learner 完成 implementation 和 self check。
2. Learner 运行 cargo check / cargo test。
3. Teacher 生成 Codex review prompt。
4. Codex 做 repository validation。
5. Teacher 做 learning validation。
6. Teacher 生成 Closure Package。
7. Teacher 生成 repository update prompt。
8. Codex 更新 review / context / todo / log。
9. 你 review 并 commit。

### 治理更新

正常顺序：

1. Teacher 或 Architect 发现 governance issue。
2. 判断是 one-time issue 还是 recurring observation。
3. 如果只是第一次出现，记录 Observation。
4. 如果出现两次或以上，进入 Governance Review。
5. Architect 或 Teacher 生成 Governance Update Request。
6. Codex 根据 prompt 更新 repository。
7. 你 review 并 commit。

### Teacher 替换

正常顺序：

1. 创建新的 Teacher Agent。
2. 上传 `AGENTS.md`、`CONTEXT.md`、Master Roadmap、当前 sprint roadmap、最近 review。
3. 上传 `docs/policies/teacher-execution-policy.md`、`docs/policies/sprint-governance-policy.md`、`docs/policies/language-output-policy.md`。
4. 要求 Teacher 执行 startup checklist。
5. 要求 Teacher 用中文总结当前 sprint context。
6. 继续当前 sprint，不要自动重开已失败或已关闭的 sprint。

### Architect 替换

正常顺序：

1. 创建新的 Architect Agent。
2. 上传 `AGENTS.md`、`CONTEXT.md`、`roadmaps/master-roadmap.md`、`governance/observations.md`。
3. 上传 `docs/policies/governance-lifecycle-policy.md`、`docs/policies/sprint-governance-policy.md`、`docs/policies/codex-collaboration-policy.md`、`docs/policies/language-output-policy.md`。
4. 上传 `docs/agents/architect-bootstrap-guide.md` 和本文档。
5. 如果治理问题来自 Sprint-03，上传 `reviews/sprint-03-failure-review.md`。
6. 要求 Architect 总结 governance state 和 active risks。
7. 只让 Architect 处理系统治理，不让它直接接管日常教学。

## 9. 常见错误

以下错误来自 Sprint-03 Failure Review。

### 错误一：Teaching Mode Drift

Teacher 过度使用 guided discovery 和 architecture discussion，导致你花太多精力猜意图。

Rust Foundations 阶段需要更直接的 Rust fundamentals reinforcement。

处理方式：

- 直接提醒 Teacher 按 `CONTEXT.md` 确认当前阶段，并根据当前阶段目标调整教学；
- 要求 Teacher 增加 direct Rust instruction；
- 要求 Teacher 不要把 architecture discussion 放在 Rust fundamentals 前面。

### 错误二：Workflow Deviation

Learning Workflow 被混成 software-team workflow。

表现包括：

- Teacher 把实现任务交给 Codex；
- Learner 不再是 primary implementer；
- Review、execution、governance update 混在一起。

处理方式：

- 重新声明当前 workflow；
- 学习项目回到 Learner implementation；
- repository update 再交给 Codex。

### 错误三：Governance Reporting Deviation

需要 governance review 时，Agent 只进行聊天式反思，没有产出 repository-oriented asset。

处理方式：

- 要求输出 Governance Feedback Package；
- 或要求 Observation Entry；
- 或要求 Governance Update Request；
- 或要求 Closure Package。

### 错误四：Rust Fundamentals 被过早弱化

Sprint validation 成功不代表 Rust fundamentals 永久掌握。

处理方式：

- 在 Rust Foundations 每个 sprint 保留 ownership、borrowing、Result、module boundary、testing 等复现；
- 不要因为一次 review 通过就跳过基础强化。

### 错误五：Observation 长期停留但不升级

同类问题出现两次或以上时，不应该继续只观察。

处理方式：

- 触发 Governance Review；
- 判断 observation 应该 Accepted、Rejected、Retired，还是转成治理规则。

## 10. 紧急接管指南

如果当前 Architect 消失，不要停止学习系统。

按下面顺序继续。

### 第一步：确认 repository 是 source of truth

先读取：

- `AGENTS.md`
- `CONTEXT.md`
- `roadmaps/master-roadmap.md`
- `governance/observations.md`
- relevant `docs/policies/*policy.md`
- `docs/agents/architect-bootstrap-guide.md`
- `docs/runbooks/system-operator-manual-zh.md`

不要依赖旧聊天记录作为唯一依据。

### 第二步：判断当前需要什么角色

如果你要继续学习：

- 创建 Teacher。

如果你要处理 governance issue：

- 创建 Architect。

如果你已有明确 repository update prompt：

- 找 Codex。

### 第三步：恢复当前状态

查看 `CONTEXT.md`：

- Current Stage
- Current Sprint
- Current Milestone
- Next Focus
- Known Risk

查看 `TODO.md`：

- 当前待办是否仍然有效。

查看最近 review：

- 上一个 sprint 是否完成；
- 是否存在 failure review；
- 是否有下一 sprint 的前置条件。

### 第四步：不要自动重开失败 Sprint

如果某个 sprint 已经被标记为 failed 或 terminated，不要直接重开。

正确做法：

- 读取 failure review；
- 保留其中的 governance lessons；
- 让 Teacher 或 Architect 判断是否创建新的 sprint；
- 新 sprint 应该重新定义 scope，而不是复制失败 sprint。

### 第五步：最小化治理动作

紧急接管时，不要大规模重构仓库。

优先做：

- 恢复 Teacher；
- 恢复 Sprint Lifecycle；
- 保持 Learner primary implementer；
- 只更新必要的 context / review / observation。

### 第六步：让 Codex 执行仓库更新

当 Teacher 或 Architect 生成明确 prompt 后，再交给 Codex。

你需要检查：

- 文件是否创建在正确位置；
- 语言是否符合要求；
- 是否误加入 implementation details；
- 是否改变了不该改变的 governance rule；
- 是否只改了本次请求相关文件。

### 第七步：继续学习，而不是追求系统完美

这个系统的目标是让你获得 Rust + Blockchain employability。

治理只服务于学习。

如果系统已经足够支持下一个 sprint，就优先继续学习，不要为了完善治理而长期暂停。
