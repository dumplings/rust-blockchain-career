# 系统操作手册

本文档面向 Learner，说明如何操作学习系统。它不是 Agent policy，也不应作为任何 Agent 的默认启动输入。

出现规则冲突时，按 `AGENTS.md` 的 Canonical Rule Ownership 判断；当前状态始终以 `CONTEXT.md` 为准。

页面端 Teacher 和 Architect 通常不能访问本地仓库。对这些窗口，“加载文件”表示由 Learner 上传附件或粘贴内容。需要 Git、diff、本地源码或仓库验证时，由 Codex 提供 scoped evidence report。

页面端 Teacher、Architect 和 Codex 与 Learner 的对话默认使用中文。英文用于 repository-ready governance documents 和 cross-agent prompts。结构化 takeover verdict 仍然是 learner-facing conversation，不应因为形式正式而自动切换成英文。

## 1. 系统目标与课程顺序

系统目标是建立参与 Rust + Blockchain 开发所需的知识、工程能力和可验证项目经验。

Solana 是主要职业 specialization，但不是第一门课程。学习顺序按前置能力组织：

1. Rust capability；
2. general blockchain foundations；
3. deeper Solana development；
4. broader blockchain engineering and job preparation。

具体阶段和退出条件由 `roadmaps/master-roadmap.md` 决定。

## 2. 角色选择

| 需求 | 默认角色 | 主要责任 |
| --- | --- | --- |
| 学习、解释、练习、学习验证 | Teacher | 教学与 assessment |
| Sprint specification 和 roadmap 教学设计 | Teacher | 目标、checkpoint、练习、密度、验证设计 |
| Roadmap 的阶段、范围或治理风险审查 | Architect | alignment、scope、workflow、governance review |
| Governance、角色边界、系统一致性 | Architect | 系统治理 |
| 代码审查、编译错误、仓库验证 | Codex | repository-facing support |
| 已批准的仓库文件更新 | Codex | scoped repository update |
| 学习项目实现 | Learner | primary implementation |

Learner 拥有最终方向、roadmap 接受、Sprint 启动和仓库变更接受权，但不承担详细 curriculum QA。Teacher 对教学质量负责，Architect 对治理一致性负责。

## 3. 文件职责

- `AGENTS.md`：系统原则、角色边界、canonical ownership、startup bundles。
- `CONTEXT.md`：现在是什么状态、什么被阻塞、下一次允许的 transition。
- `TODO.md`：当前可执行且有完成条件的任务。
- `roadmaps/master-roadmap.md`：课程阶段、顺序和退出条件。
- `roadmaps/sprint-XX.md`：当前 Sprint 特有执行合同。
- `docs/policies/*`：对应角色或 workflow 的 reusable rules。
- stage coverage artifact：当前阶段的知识覆盖和缺口。
- `reviews/*`：closure、failure、handover 和治理决策证据。
- `learning-log.md`：按时间记录学习历史。

历史 roadmap、review、handover 和 learning log 是条件性证据，不是每个窗口的默认输入。

本地文件路径只能帮助识别文件，不能代替上传。页面端 Agent 不应声称读取了未提供的本地文件。

## 4. 设计一个 Sprint Roadmap

正常顺序：

1. 正式关闭前一个 Sprint，并保存三层验证和 closure。
2. 同步 `CONTEXT.md`、相关 coverage artifact 和必要的 learning log。
3. Teacher 根据 Master Roadmap、当前状态、coverage gap 和 learner feedback 完成 Specification Review。
4. Learner 确认候选方向。
5. Teacher 起草 sprint-specific roadmap。
6. 出现 stage、scope、workflow 或 governance 风险时，由 Architect 审查。
7. Learner 接受 roadmap；此时状态是 accepted-but-not-started。

Roadmap 应保存目标、scope、non-goals、learner decisions、checkpoints、项目边界、Sprint 特有验证和完成条件。通用执行规则应引用 policy，不应复制到每个 roadmap。

## 5. 启动 Sprint

启动前必须同时具备：

- 已接受的 current sprint roadmap；
- `AGENTS.md` 中的 Teacher sprint execution bundle；
- Learner 明确的 execution-start command；
- Teacher startup checklist 通过。

Roadmap 接受、文件更新、TODO 顺序和 startup checklist 本身都不会启动 Sprint。

使用唯一的 canonical Teacher launch artifact：

`docs/agents/teacher-standard-prompt.md`

Architect 可以根据当前 Sprint 准备该 Prompt、附件清单和条件性证据，但不能代表 Learner 创建执行授权。Learner 有意发送其中的 explicit start sentence，才构成 execution-start command。

如果只想创建窗口但暂不启动，使用该文件中的 readiness-only 变体。Teacher 此时只能报告 readiness。

## 6. 关闭 Sprint

正常顺序：

1. Learner 完成实现、自检和必要测试。
2. Teacher 生成 learning-project Codex validation prompt。
3. Codex 独立验证目标仓库。
4. Teacher 完成 Teacher Learning Validation。
5. Teacher 生成 closure package。
6. Codex 根据已批准 prompt 更新治理仓库。
7. Learner review 并决定是否接受或 commit。

Closure 应记录实际完成内容、能力增长、未完成内容、遗留问题和三层验证结果。它不能因为代码编译或测试通过而自动 PASS。

## 7. 创建或替换 Architect

使用唯一的 canonical launch artifact：

`docs/agents/architect-standard-prompt.md`

把该文件中的 Prompt 复制到新窗口，并上传 `AGENTS.md` 定义的 Architect / governance bundle。不要从本手册复制另一个 Architect 规则版本。

如果当前任务依赖未提交变更、Git diff 或本地仓库检查，先让 Codex 生成 evidence report，再把报告与必要的 canonical files 一起交给 Architect。handover、Master Roadmap、observations 和历史 review 仍然只按任务需要补充。

## 8. 使用 Codex

适合交给 Codex：

- repository inspection；
- code、test、architecture review；
- compiler error diagnosis；
- formal repository validation；
- 为页面端 Teacher 或 Architect 生成 Git、diff 和本地文件 evidence report；
- 执行已经形成决策的治理文件更新。

不应默认交给 Codex：

- 替 Learner 完成 learning exercise；
- Teacher Learning Validation；
- 在没有治理决策时猜测应该修改什么；
- 用一个 prompt 同时验证治理仓库和独立 learning-project repository。

## 9. 治理更新

治理更新只在规则不清、职责冲突、反复失败、状态漂移或重要知识可能丢失时进行。

处理顺序：

1. 找到该问题的 canonical owner。
2. 判断是执行错误、规则缺口还是重复规则。
3. 优先修改 canonical owner 并删除或缩短重复表述。
4. 只有无法归入现有职责时才新增文件或规则。
5. 保存简洁的决策证据。
6. 由 Learner review 最终结果。

## 10. 恢复与接管

Agent 丢失或聊天窗口失效时：

1. 读取 `AGENTS.md`、`CONTEXT.md` 和当前任务。
2. 判断需要 Teacher、Architect 还是 Codex。
3. 加载对应 canonical bundle。
4. 只在 scope、coverage、failure 或 authority 问题需要时读取历史文件。
5. 不自动重开 failed、stopped 或 closed Sprint。
6. 不把旧聊天摘要当作 authority。

治理服务于学习。系统已经足以继续学习时，不要为了追求文件形式完美而阻塞课程执行。
