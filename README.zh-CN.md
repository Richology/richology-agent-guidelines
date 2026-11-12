<div align="center">

<img src="assets/cover.png" alt="Richology Agent Guidelines：明确范围、精准修改、验证结果" width="100%" />

# Richology Agent Guidelines

### 明确范围，精准修改，验证结果。

给 Vibe Coding 和日常 AI 编程的一份 AGENTS.md。

[English](README.md) · **简体中文**

[![GitHub stars](https://img.shields.io/github/stars/Richology/richology-agent-guidelines?style=flat&color=387458)](https://github.com/Richology/richology-agent-guidelines/stargazers)
[![License: MIT](https://img.shields.io/badge/License-MIT-387458)](LICENSE)
[![Format: Markdown](https://img.shields.io/badge/Format-Markdown-171717)](AGENTS.md)
[![Rules: Chinese](https://img.shields.io/badge/Rules-Chinese-9b7846)](AGENTS.md)

**[阅读完整规则](AGENTS.md) · [开始使用](#开始使用) · [接入不同-agent](#接入不同-agent) · [演变记录](docs/EVOLUTION.md)**

</div>

[为什么需要](#为什么需要这份指南) · [适合谁](#适合谁用) · [四项原则](#四项原则) · [来源](#来源与演变) · [参与贡献](#参与贡献)

## 为什么需要这份指南

用自然语言描述目标后，让 Agent 在明确范围内持续推进，只修改必要内容，完成适当验证，并把结果交代清楚。

这份指南针对实际协作中的摩擦：反复请求确认、只给计划不执行、顺手重构、过度设计、检查迟迟不结束，以及“说完成了，却不知道验证了什么”。

它的特色是**给规则加上适用条件**：范围明确时继续推进，重要决策缺失时询问；完成必要验证，没有新疑点就结束；简洁表达，同时保留判断结果所需的信息。

它是一份纯 Markdown 指令模板，无需安装依赖、运行服务、配置 API Key 或启用 Skill。当前规则正文为中文；英文 README 提供项目介绍和使用说明。

## 适合谁用

- **Vibe Coders**：用自然语言做产品，希望减少逐步指挥，让需求更顺畅地落实。
- **独立开发者和个人项目维护者**：需要快速迭代，也希望改动简单、集中、容易检查。
- **借助 AI 编程的产品、设计和业务人员**：希望看懂完成情况、重要限制，以及何时需要自己接手。
- **开发者和小团队**：希望减少无关重构、不必要抽象、重复确认和过度检查。
- **在多个 Agent 之间切换的用户**：希望保留一致的协作原则，再加入不同项目的规范。

它提供通用工作方式；技术栈、目录结构、测试命令和发布要求仍需按项目补充，也不能替代清楚的需求和对重要改动的审阅。

## 四项原则

| 原则 | 希望促成的行为 |
| --- | --- |
| 在请求范围内行动 | 识别行动请求，延续已有授权，自行处理常规细节；重要歧义或明显扩大范围时询问。 |
| 保持简单，精准修改 | 采用最简单的完整实现，避免额外功能、推测性抽象和无关改动。 |
| 让检查点和验证与风险相称 | 结合后果和恢复成本检查；验证有意义的行为，充分检查后适时结束。 |
| 清晰沟通，按需委派 | 区分完成、验证和不确定性；明确交接，中断后恢复必要上下文。 |

### 期待看到什么变化

以下是设计目标，尚无量化实验验证。

| 常见摩擦 | 期待的行为 |
| --- | --- |
| “可以帮我修复吗？”只得到方案 | 落实已授权的修复并验证结果。 |
| 每个常规选择都要求确认 | 在范围内自行决定并推进。 |
| 修一个问题顺带重构多个模块 | 改动能追溯到当前请求。 |
| 检查不断扩大，任务迟迟不结束 | 完成必需检查，没有新疑点就结束。 |
| “完成了”，却看不出验证情况 | 说明结果、证据和仍未确定的事项。 |

## 开始使用

1. 打开并阅读 [AGENTS.md](AGENTS.md)。
2. 根据下表选择工具支持的规则入口。没有文件就创建，已有文件就**合并**，保留原有项目规范。
3. 补充技术栈、运行与测试命令，以及部署等操作的具体约束。
4. 开启新会话，通过工具提供的入口检查规则是否加载，再用一个小任务观察实际行为。Agent 口头确认不等于效果已验证。

建议先在单个项目试用；确实希望所有项目都采用时，再放入全局配置。避免通过多种入口重复加载同一套规则。

### 让 Agent 帮你接入

向 Agent 提供本仓库或规则文件，再复制下面的提示词：

```text
请阅读这份 AGENTS.md，并将其中的通用协作规则合并到当前
Agent 支持的项目规则文件中。

先检查已有规则和当前工具的加载方式，保留项目原有的技术栈、
命令、架构说明和约束，避免重复或矛盾。

只修改规则文件。完成后说明修改位置，以及如何确认规则已加载。
```

## 接入不同 Agent

**规则可迁移，不代表所有工具都会自动读取同名文件。** 以下区分实际使用环境、文档支持的入口和待验证项，不承诺不同模型上的效果一致。文档入口于 2026-11-12 首次发布时核对，具体行为可能随版本与配置变化。

| 工具 | 建议入口 | 当前状态 |
| --- | --- | --- |
| Codex | 项目 `AGENTS.md`；个人通用配置可放在 `~/.codex/AGENTS.md` | 维护者实际迭代环境，未做对照实验 |
| [Claude Code](https://support.claude.com/en/articles/14553240-give-claude-context-claude-md-and-better-prompts) | 合并到 `CLAUDE.md` | 官方文档支持入口，本规则未独立实测 |
| [Cursor](https://cursor.com/docs/rules) | 项目根目录 `AGENTS.md` 或 Cursor Rules | 官方文档支持入口，本规则未独立实测 |
| [GitHub Copilot（VS Code）](https://code.visualstudio.com/docs/agents/reference/custom-instructions-reference) | `.github/copilot-instructions.md` 或其支持的 `AGENTS.md` 机制 | 官方文档支持入口，其他 Copilot 客户端可能不同 |
| [Gemini CLI](https://geminicli.com/docs/cli/gemini-md/) | 合并到 `GEMINI.md` | 官方文档支持入口，本规则未独立实测 |
| [OpenCode](https://dev.opencode.ai/docs/rules/) | 项目 `AGENTS.md` | 官方文档支持入口，本规则未独立实测 |
| [Cline](https://cline.bot/blog/clinerules-version-controlled-shareable-and-ai-editable-instructions) | 在 Rules 界面创建工作区规则 | 官方文档支持入口，本规则未独立实测 |
| [DeepSeek Harness](https://www.deepseek.com/harness/en/) | 先确认当前版本持久指令的加载方式，再接入 | 候选接入工具，具体路径及效果待验证 |

其他支持持久化自定义指令的 Agent 也可能使用这些原则，但应先确认加载机制。欢迎提交 Qwen Code、Kimi Code 等工具的接入与使用记录。

## 来源与演变

1. **卡帕西相关指南提供基础——据维护者回忆。** 初版参考了 GitHub 上的相关版本。当前可对照的[社区指南](https://github.com/multica-ai/andrej-karpathy-skills)与本文件共享简单、精准、可验证的原则，具体历史版本尚未恢复。它并非卡帕西本人发布或背书的指南。
2. **参考官方文档适配 Astra——据维护者回忆。** 曾让 Codex 根据 OpenAI 官方文档对 Astra 特点的说明，分析并调整已有规则。具体文档和逐条改动归属待确认，不将其表述为已验证的模型专属优化。
3. **参考 i-have-adhd 增强沟通——有明确记录。** 从 [i-have-adhd](https://github.com/ayghri/i-have-adhd) 中选择性吸收交接、分层呈现和上下文恢复的思路。第 1～3 节未变，第 4 节从 3 条扩展为 8 条，没有引入每轮重复状态、固定列表上限或强制时间估计。

详见[完整演变记录](docs/EVOLUTION.md)和[来源说明](THIRD_PARTY_NOTICES.md)。

## 已知限制与定制

这份文件是行为指导，不会强制执行权限、保证正确性或覆盖更高优先级指令。实际效果取决于模型、Agent 工具、上下文和项目规则。维护者已主观感受到回复变化，但尚未进行量化效果评估。

可以按自己的工作方式修改。项目事实和具体命令与通用规则一起维护；遇到规则造成的摩擦，先记录任务、实际表现和有针对性的改法，再决定是否增加约束。

## 参与贡献

欢迎[提交 Issue](https://github.com/Richology/richology-agent-guidelines/issues)或小范围 PR，说明：

- Agent、模型与版本，以及规则的加载方式。
- 可复现的小任务、期待行为和实际表现。
- 建议修改的措辞，以及可能引入的取舍。

欢迎兼容性记录、表达改进和翻译。示例中请去除私有项目数据及凭据；标记工具“已测试”时需说明测试内容。

## 许可与致谢

Richology 的原创贡献采用 [MIT 许可](LICENSE)。参考来源及保留的上游许可声明见 [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md)。项目与所提到的模型或工具厂商不存在由本文声明的关联或背书。

README 结构参考 [Bookleap](https://github.com/Richology/Bookleap)。封面使用 OpenAI 内置生图工具生成，[提示词与制作记录](docs/COVER.md)一并公开。

<div align="center">

**让下一次改动更清楚、更集中、更容易验证。**

[阅读 AGENTS.md](AGENTS.md) · [反馈使用体验](https://github.com/Richology/richology-agent-guidelines/issues) · [给项目一个 Star](https://github.com/Richology/richology-agent-guidelines)

</div>
