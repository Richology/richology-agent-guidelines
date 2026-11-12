# 为什么这些规则会变成现在这样

让 Agent 更主动，可能带来范围失控；让它更谨慎，又可能变成每一步都询问。这份指南经过三轮迭代，希望让你减少重复指挥，同时仍能掌握改动范围、判断结果，并顺利接手。

[直接使用规则](../AGENTS.md) · [返回使用指南](../README.zh-CN.md)

## 第一轮：让 AI 把改动集中在你的需求上

**你可能遇到的问题：** 只想修一个 bug，Agent 却重构了相邻模块、加入未要求的配置，甚至删除了它认为没用的代码。结果是改动更多，检查和返工也更多。

最初参考卡帕西相关社区指南，确立了简单实现、精准修改和验证结果的基础原则：

- 实现你提出的需求，避免额外功能和推测性抽象。
- 遵循已有项目惯例，不顺手修改无关代码或格式。
- 保留原有死代码，只清理本次修改造成且确认不再需要的内容。
- 用验证结果判断工作是否完成。

**对你的帮助：** 更容易看清这次到底改了什么，以及每处改动与需求的关系。尤其适合维护已有项目，或在 Vibe Coding 中持续追加小需求。

这些原则保留在当前指南的第 2 节，并与第 3 节的验证要求配合使用。

## 第二轮：减少反复确认，让 Agent 在范围内持续推进

**你可能遇到的问题：** 已经明确让 Agent 修复问题，它仍反复询问要不要开始；常规细节也全部交给你决定；或者检查不断增加，任务始终没有结束。

Astra 发布后，参考 OpenAI 官方文档对其特点的说明，由 Codex 分析已有指南如何调整，以更好地使用模型的能力。简单、精准、可验证的原则继续保留，协作方式进一步围绕请求范围和具体风险完善。

这一阶段形成的规则强调：

| 情况 | 指南希望 Agent 如何处理 |
| --- | --- |
| 你明确提出行动请求 | 在已有授权内完成工作，不只停留在建议或计划。 |
| 遇到普通实现细节 | 根据项目惯例自行决定，不把每个选择都交给你。 |
| 缺失信息会影响重要决策 | 说明需要你决定什么，同时继续独立且已授权的工作。 |
| 操作后果严重或难以恢复 | 核实授权范围，说明影响与恢复方式，执行适用的保障措施。 |
| 必需检查已经通过 | 没有新改动、失败或具体疑点时，不再无端扩大验证。 |

**对你的帮助：** 常规工作少打断，重要决策仍由你掌握。检查投入随任务风险变化，让小修改能及时结束，让重要操作获得足够关注。

这些要求主要体现在当前指南的第 1、3 节。它们描述通用协作方式，使用这份指南不以选择 Astra 为前提。

## 第三轮：让你看懂结果，也知道何时需要接手

**你可能遇到的问题：** Agent 写了很长的回复，你仍不知道任务是否完成、有没有验证；隔了一段时间回来，也很难接上之前的工作。

参考 i-have-adhd 对信息呈现和行动引导的思路，这一轮保留前 3 节，将第 4 节从 3 条扩展为 8 条，让沟通更贴合实际任务。

| 改进 | 对你的帮助 |
| --- | --- |
| 按行动、解释、比较等请求组织回答 | 要执行时看到结果，要理解时获得解释，要选择时看清取舍。 |
| 区分已完成、已验证和仍不确定 | 能判断“改好了”背后有哪些证据，不把推测当结论。 |
| 复杂信息分层，操作步骤明确 | 先看到当前最重要的信息，需要时再深入细节。 |
| 交接时给出具体动作和成功标志 | 知道在哪里操作、输入什么，以及如何判断成功。 |
| 中断后按需恢复上下文 | 回到任务时能迅速了解已完成什么、还缺什么。 |

**对你的帮助：** 减少读完回复后的二次追问。尤其适合不熟悉全部实现细节、同时处理多个任务，或需要亲自验收结果的用户。

这轮没有加入每轮重述进度、固定列表长度或强制时间估计。普通问答无需套流程；需要充分解释时，也不应为了简短删掉关键内容。

## 你可以怎样使用这些设计

当前版本把三轮迭代组合为四部分：范围、修改、验证和沟通。建议先在一个项目中使用完整规则，再根据具体摩擦做小幅调整。

例如，若 Agent 仍在反复确认，先检查任务范围是否清楚、是否存在工具本身的审批要求；若回答仍难以接手，检查它是否提供了具体操作和成功标志。观察实际任务表现，比仅让 Agent 承诺遵守规则更有帮助。

这些是规则的设计意图，不保证每个模型都能稳定执行。欢迎在 [Issue](https://github.com/Richology/richology-agent-guidelines/issues) 中提供任务、Agent 版本和实际表现，帮助后续改进。

## 参考来源

- [Karpathy-inspired community guidelines](https://github.com/multica-ai/andrej-karpathy-skills)：简单实现、精准修改和可验证目标。
- OpenAI 官方文档：Astra 适配阶段对模型特点的参考。
- [i-have-adhd](https://github.com/ayghri/i-have-adhd)：信息分层、行动引导和上下文恢复。

归属与许可声明见[来源说明](../THIRD_PARTY_NOTICES.md)。

## English overview

The guide evolved around three user problems: changes that drift beyond the request, unnecessary interruptions during execution, and results that are hard to understand or act on. Karpathy-inspired principles established focused, simple, verifiable work. A later Astra-oriented revision refined autonomy within scope and checks proportional to risk. Ideas from i-have-adhd then improved communication and handoffs while preserving the earlier engineering rules. These are design intentions; actual behavior depends on the agent and task.
