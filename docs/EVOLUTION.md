# 演变记录 / Evolution

这是一份回溯记录，不是完整的 Git 历史。首次公开发布之前的版本未在本仓库逐次提交。

- **已确认**：本次整理期间可以通过文件或对话核实。
- **据维护者回忆**：来自维护者提供的背景。
- **待确认**：缺少历史文件、链接或修改记录。

## 1. 卡帕西相关指南：基础原则

据维护者回忆，初版参考了 GitHub 上的卡帕西相关版本。当前可对照的项目是 [andrej-karpathy-skills](https://github.com/multica-ai/andrej-karpathy-skills)，它是社区根据卡帕西的观察整理的指南。

**保留的原则（文本对比支持）：** 编码前处理重要歧义、简单实现、精准修改、以验证判断是否完成。当前第 2 节与其简单性及精准修改原则尤其接近。

**待确认：** 当时具体使用的仓库、提交和文件；是否直接翻译；最初已经改过哪些条款。相似性不能独立证明具体来源关系。

## 2. 参考官方文档，适配 Astra

据维护者回忆，Astra 发布后，曾参考 OpenAI 官方文档对其特点的说明，让 Codex 分析已有卡帕西相关指南如何迭代，以更好地使用 Astra。

**阶段结果已确认：** 最近一轮沟通优化之前，文件已有“请求范围、简单与精准、风险与验证、沟通与委派”四节。

**保留：** 简单实现、精准修改和验证结果等核心原则。

**可观察的差异：** 相比上述社区指南，该版本更明确延续授权、减少重复确认、允许常规细节自主决策、按风险设置检查点，并规定充分验证后的停止条件。

**归属待确认：** 无法将这些差异逐条归因于 Astra 适配。具体官方文档链接、模型描述、修改前后文件和 Codex 分析记录尚未恢复。本项目不声称获得官方背书，也不将“Astra 专属优化”作为已验证的兼容性结论。

## 3. 参考 i-have-adhd，增强沟通

**已确认。** 2026 年 11 月的整理中，阅读 [i-have-adhd](https://github.com/ayghri/i-have-adhd) 后选择性吸收其呈现方式。

**保留：** 标题、开头、第 1～3 节原文；第 4 节标题及子 Agent 条款原文。

**改进：** 第 4 节由 3 条扩展为 8 条，加入按请求类型回答、区分完成与验证、复杂信息分层、明确交接、中断后恢复上下文、直接说明错误及有条件的时间估计。

**没有引入：** 每轮重复状态、固定列表数量上限、强制时间估计、任务完成后仍追加下一步。

## 4. 首次公开整理

2026-11-12：将当前全局 AGENTS.md 原样收录，添加中英文 README、工具接入状态、封面、来源说明和 MIT 许可。本次发布未进一步改写规则正文。

## English summary

The maintainer recalls a Karpathy-related starting point, followed by a Codex-assisted revision informed by OpenAI documentation about Astra. The exact sources and per-line changes for those stages are not recovered. The latest documented revision selectively applies communication ideas from i-have-adhd: sections 1–3 remain unchanged, while section 4 grows from three bullets to eight. The initial public release packages the existing rules without rewriting them.
