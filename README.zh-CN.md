<div align="center">

<img src="assets/cover.png" alt="Richology Agent Guidelines：明确范围、精准修改、验证结果" width="100%" />

# Richology Agent Guidelines

### 明确范围，精准修改，验证结果。

让 AI 少跑偏、少反复确认，把任务做完并交代清楚。

给 Vibe Coding 和日常 AI 编程的一份可复制的协作规则。

[English](README.md) · **简体中文**

[![GitHub stars](https://img.shields.io/github/stars/Richology/richology-agent-guidelines?style=flat&color=387458)](https://github.com/Richology/richology-agent-guidelines/stargazers)
[![License: MIT](https://img.shields.io/badge/License-MIT-387458)](LICENSE)
[![Format: Markdown](https://img.shields.io/badge/Format-Markdown-171717)](AGENTS.md)
[![Rules: Chinese](https://img.shields.io/badge/Rules-Chinese-9b7846)](AGENTS.md)

**[复制规则](AGENTS.md) · [开始使用](#开始使用) · [选择你的 Agent](#接入不同-agent)**

</div>

[为什么需要](#为什么需要这份指南) · [适合谁](#适合谁用) · [四项原则](#四项原则) · [定制](#按你的项目调整) · [参与贡献](#参与贡献)

## 为什么需要这份指南

你想改一个按钮，AI 却重构了整页；你已经说“帮我修复”，它仍然问要不要开始；它说“完成了”，你却不知道有没有运行检查。

如果这些情况让你疲惫，可以把这份 [AGENTS.md](AGENTS.md) 加入项目，让 Agent 有一套明确的协作规则：

- **减少反复指挥。** 在已有授权内处理常规细节，持续推进任务。
- **让改动更容易检查。** 聚焦当前需求，减少无关重构和额外功能。
- **把检查花在值得的地方。** 按风险验证结果，避免没有新疑点还不断扩大检查。
- **看懂结果，接得上下一步。** 分清完成了什么、验证了什么，以及哪些事情需要你处理。

复制 Markdown 即可开始，无需安装插件、运行服务或配置 API Key。当前规则正文为中文，配有中英文使用说明。

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

**先在一个项目里试用。** [打开规则文件](AGENTS.md)，或[查看纯文本](https://raw.githubusercontent.com/Richology/richology-agent-guidelines/main/AGENTS.md)。

1. **复制规则。** 将内容放入你的 Agent 支持的项目规则文件；Codex 和 Cursor 可使用项目根目录的 `AGENTS.md`，Claude Code 使用 `CLAUDE.md`。更多工具见下表。
2. **保留项目规范。** 已有规则文件时合并内容，不覆盖原有的技术栈、运行命令和约束。没有规则文件时直接创建。
3. **开始一个小任务。** 开启新会话，检查规则是否加载，再按平时的方式描述需求。

例如：

```text
请修复这个页面在手机上的横向溢出，保持现有布局风格。
完成后告诉我改了什么、做了哪些检查，还有什么没验证。
```

观察 Agent 是否聚焦这项修改、减少无关询问，并给出可判断的验证结果。首次试用不必同时配置多个工具或全局规则。

<details>
<summary><strong>不知道规则文件放哪里？让 Agent 帮你接入</strong></summary>

把下面的提示词发给可以访问仓库和本地文件的 Agent：

```text
请读取 https://github.com/Richology/richology-agent-guidelines
中的 AGENTS.md，将其通用协作规则合并到当前工具支持的
项目规则文件中。

先检查已有规则与加载方式。保留项目原有的技术栈、命令、
架构说明和约束，避免重复或矛盾。只修改规则文件。

完成后说明修改位置，以及如何确认规则已加载。
```

如果工具不能访问链接，直接把规则正文粘贴给它。

</details>

<details>
<summary><strong>想在多个项目中使用？</strong></summary>

确认适合自己的工作方式后，可使用工具支持的全局指令入口。例如，Codex 的个人通用规则可放入 `~/.codex/AGENTS.md`。已有文件仍应合并，不要覆盖；避免通过多个入口重复加载相同内容。

</details>

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


## 按你的项目调整

通用规则之外，建议补充项目的运行与测试命令、目录约定和发布约束。若已有同类规则，优先合并精简。

这份指南在 Codex 的日常使用中持续打磨；表中的其他接入入口按官方文档整理，尚未逐一实测。它通过指令引导行为，不能保证每次都被正确执行，也不能代替工具权限或重要改动的审阅。页面中的行为变化是设计目标，尚无量化效果评估。

## 参与贡献

欢迎[提交 Issue](https://github.com/Richology/richology-agent-guidelines/issues)或小范围 PR，说明：

- Agent、模型与版本，以及规则的加载方式。
- 可复现的小任务、期待行为和实际表现。
- 建议修改的措辞，以及可能引入的取舍。

欢迎兼容性记录、表达改进和翻译。示例中请去除私有项目数据及凭据；标记工具“已测试”时需说明测试内容。

## 许可与致谢

采用 [MIT 许可](LICENSE)，欢迎复制、修改并用于自己的项目。

基础原则受到[卡帕西相关社区指南](https://github.com/multica-ai/andrej-karpathy-skills)启发；之后参考 OpenAI 官方文档适配 Astra，并借鉴 [i-have-adhd](https://github.com/ayghri/i-have-adhd) 改进沟通与交接。

想了解设计背景，可阅读[演变记录](docs/EVOLUTION.md)。上游归属与许可声明见[来源说明](THIRD_PARTY_NOTICES.md)。

<div align="center">

**让下一次改动更清楚、更集中、更容易验证。**

[阅读 AGENTS.md](AGENTS.md) · [反馈使用体验](https://github.com/Richology/richology-agent-guidelines/issues) · [给项目一个 Star](https://github.com/Richology/richology-agent-guidelines)

</div>
