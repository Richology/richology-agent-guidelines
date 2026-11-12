<div align="center">

<img src="assets/cover.png" alt="Richology Agent Guidelines — Clear scope. Focused changes. Verified results." width="100%" />

# Richology Agent Guidelines

### Clear scope. Focused changes. Verified results.

Help your coding agent stay on task, ask fewer unnecessary questions, and explain what actually works.

Copyable collaboration rules for vibe coding and everyday AI development.

[简体中文](README.md) · **English**

[![GitHub stars](https://img.shields.io/github/stars/Richology/richology-agent-guidelines?style=flat&color=387458)](https://github.com/Richology/richology-agent-guidelines/stargazers)
[![License: MIT](https://img.shields.io/badge/License-MIT-387458)](LICENSE)
[![Format: Markdown](https://img.shields.io/badge/Format-Markdown-171717)](AGENTS.md)
[![Rules: Chinese](https://img.shields.io/badge/Rules-Chinese-9b7846)](AGENTS.md)

**[Read the rules](AGENTS.md) · [Get started](#get-started) · [Agent setup](#agent-setup) · [中文指南](README.md)**

</div>

[Why](#why-this-exists) · [Who it is for](#who-it-is-for) · [Principles](#four-principles) · [Customize](#make-it-fit-your-project) · [Contribute](#contribute)

## Why this exists

You ask for a button change and get a page refactor. You ask for a fix and get another request to begin. The agent says “done,” but you cannot tell whether it checked anything.

Add this [AGENTS.md](AGENTS.md) to your project to give your agent clear collaboration rules:

- **Less micromanagement.** Resolve routine details within existing authorization and keep working toward completion.
- **Changes you can review.** Focus on the request instead of unrelated cleanup or extra features.
- **Checks that match the stakes.** Verify meaningful behavior without endlessly expanding checks absent a new concern.
- **Results you can act on.** Explain what is complete, what was verified, and where you need to take over.

Start by copying Markdown. No plugin, service, dependency, or API key is required. The canonical rules are currently in Chinese, with English and Chinese adoption guides.

## Who it is for

- **Vibe coders** building products through natural-language requests who want less micromanagement and clearer handoffs.
- **Independent builders** who need focused iterations without unnecessary architecture or cleanup.
- **Product, design, and business people** using agents to build tools and needing understandable results and next steps.
- **Developers and small teams** seeking consistent scope, change, and verification discipline.
- **People switching agents** who want to carry their collaboration preferences across tools.

It complements project-specific architecture, commands, and conventions. It does not replace clear requirements or review of consequential changes.

## Four principles

| Principle | Intended behavior |
| --- | --- |
| Act within the request | Treat clear action requests as authorization; preserve authorization across turns; ask before material scope expansion. |
| Keep implementation simple and changes focused | Use the simplest complete solution; avoid unrelated refactors, speculative features, and unnecessary abstractions. |
| Match checkpoints and verification to risk | Consider consequences and recovery cost; run meaningful checks; stop when sufficient checks pass unless new evidence warrants more. |
| Communicate clearly and delegate selectively | Distinguish completed from verified work; provide concrete handoffs; restore useful context after interruptions. |

### What improvement would look like

These are design goals, not benchmark results.

| Common friction | Desired response |
| --- | --- |
| “Can you fix this?” produces only a plan | Carry out the authorized fix and verify it. |
| Every routine choice becomes a question | Resolve ordinary details within scope. |
| A small fix turns into unrelated cleanup | Keep changes traceable to the request. |
| Testing keeps expanding without new concerns | Finish required verification, then stop. |
| “Done” hides whether anything was checked | Report the result, evidence, and remaining uncertainty. |

## Get started

**Try it in one project first.** [Open the rules](AGENTS.md) or [view the raw text](https://raw.githubusercontent.com/Richology/richology-agent-guidelines/main/AGENTS.md).

1. **Copy the rules.** Put them in your agent's supported project instruction file. Codex and Cursor can use a root `AGENTS.md`; Claude Code uses `CLAUDE.md`. More tools are listed below.
2. **Keep project guidance.** Merge with existing instructions rather than overwriting stack details, commands, or constraints. Create the file if it does not exist.
3. **Try a small task.** Start a fresh session, inspect loaded instructions where supported, and describe your request normally.

For example:

```text
Fix horizontal overflow on this page on mobile while preserving its
current layout style. When finished, explain what changed, what you
checked, and what remains unverified.
```

Look for focused edits, fewer unnecessary questions, and useful verification evidence. You do not need to configure several tools or global defaults for a first trial.

<details>
<summary><strong>Not sure where the rules belong? Ask your agent to install them</strong></summary>

Give this prompt to an agent with access to the repository and your local files:

```text
Read AGENTS.md from https://github.com/Richology/richology-agent-guidelines
and merge its general collaboration rules into the project instruction
file supported by this tool.

First inspect existing rules and the loading mechanism. Preserve the
project's stack, commands, architecture, and constraints. Avoid duplicated
or contradictory instructions. Modify only instruction files.

Report the file changed and how to check that the rules are loaded.
```

If your agent cannot open links, paste the rules directly.

</details>

<details>
<summary><strong>Want the rules across projects?</strong></summary>

After trying them, use your tool's global instruction mechanism if it fits your workflow. For example, Codex personal defaults can live in `~/.codex/AGENTS.md`. Merge with existing instructions and avoid loading duplicate copies through several mechanisms.

</details>

## Agent setup

**Using the rules is different from automatic discovery of a filename.** This table distinguishes personal use from documented entry points. It does not claim equal results across agents. Documentation checked during the initial release on 2026-11-12; behavior can vary by tool version and configuration.

| Agent | Suggested entry | Status |
| --- | --- | --- |
| Codex | Project `AGENTS.md`; personal defaults may live in `~/.codex/AGENTS.md` | Maintainer's actual iteration environment; no controlled benchmark |
| [Claude Code](https://support.claude.com/en/articles/14553240-give-claude-context-claude-md-and-better-prompts) | Merge into `CLAUDE.md` | Documented entry; this guide not independently tested |
| [Cursor](https://cursor.com/docs/rules) | Project-root `AGENTS.md`, or Cursor Rules | Documented entry; this guide not independently tested |
| [GitHub Copilot in VS Code](https://code.visualstudio.com/docs/agents/reference/custom-instructions-reference) | `.github/copilot-instructions.md`, or its supported `AGENTS.md` mechanism | Documented entry; other Copilot surfaces may differ |
| [Gemini CLI](https://geminicli.com/docs/cli/gemini-md/) | Merge into `GEMINI.md` | Documented entry; this guide not independently tested |
| [OpenCode](https://dev.opencode.ai/docs/rules/) | Project `AGENTS.md` | Documented entry; this guide not independently tested |
| [Cline](https://cline.bot/blog/clinerules-version-controlled-shareable-and-ai-editable-instructions) | Create a workspace rule through the Rules interface | Documented entry; this guide not independently tested |
| [DeepSeek Harness](https://www.deepseek.com/harness/en/) | Confirm the installed version's persistent-instruction mechanism before adapting | Candidate integration; loading path and effect not verified |

Other agents with persistent custom instructions may also use these principles. Confirm their loading rules rather than assuming `AGENTS.md` is discovered automatically. Reports for Qwen Code, Kimi Code, and other tools are welcome.


## Make it fit your project

Add your project's run/test commands, directory conventions, and release constraints. Merge and simplify overlapping guidance rather than accumulating duplicate rules.

This guide is refined through everyday Codex use. Other documented entry points have not been individually tested with these rules. Instructions influence behavior; they do not guarantee compliance, replace tool permissions, or remove the need to review consequential changes. The behavior changes described here are design goals, not quantitative evaluation results.

## Contribute

[Open an issue](https://github.com/Richology/richology-agent-guidelines/issues) or submit a focused pull request with:

- Agent and model/version, plus how the rules were loaded.
- A small reproducible task, expected behavior, and what happened.
- A proposed wording change and its possible tradeoff.

Compatibility reports, clearer wording, and translations are welcome. Remove private project data and credentials from examples. Do not mark a tool tested without describing what was checked.

## License and acknowledgments

Released under the [MIT License](LICENSE). Copy, adapt, and use it in your own projects.

The engineering foundation draws on [Karpathy-inspired community guidelines](https://github.com/multica-ai/andrej-karpathy-skills). Later iterations used OpenAI documentation to adapt for Astra and selected ideas from [i-have-adhd](https://github.com/ayghri/i-have-adhd) to improve communication and handoffs.

For design background, see the [evolution record](docs/EVOLUTION.md). Upstream attribution and license notices are in [source notices](THIRD_PARTY_NOTICES.md).

<div align="center">

**Make the next change clear, focused, and verifiable.**

[Read AGENTS.md](AGENTS.md) · [Share feedback](https://github.com/Richology/richology-agent-guidelines/issues) · [Star this project](https://github.com/Richology/richology-agent-guidelines)

</div>
