<div align="center">

<img src="assets/cover.png" alt="Richology Agent Guidelines — Clear scope. Focused changes. Verified results." width="100%" />

# Richology Agent Guidelines

### Clear scope. Focused changes. Verified results.

A practical AGENTS.md for vibe coding and everyday collaboration with coding agents.

**English** · [简体中文](README.zh-CN.md)

[![GitHub stars](https://img.shields.io/github/stars/Richology/richology-agent-guidelines?style=flat&color=387458)](https://github.com/Richology/richology-agent-guidelines/stargazers)
[![License: MIT](https://img.shields.io/badge/License-MIT-387458)](LICENSE)
[![Format: Markdown](https://img.shields.io/badge/Format-Markdown-171717)](AGENTS.md)
[![Rules: Chinese](https://img.shields.io/badge/Rules-Chinese-9b7846)](AGENTS.md)

**[Read the rules](AGENTS.md) · [Get started](#get-started) · [Agent setup](#agent-setup) · [中文指南](README.zh-CN.md)**

</div>

[Why](#why-this-exists) · [Who it-is-for](#who-it-is-for) · [Principles](#four-principles) · [Evolution](#origins-and-evolution) · [Contribute](#contribute)

## Why this exists

Describe a goal, then let your agent work within the agreed scope: make necessary changes, verify the result, and explain what is done and what remains uncertain.

These guidelines address recurring collaboration friction: repeated permission questions, plans without execution, unrelated refactoring, unnecessary abstractions, excessive checking, and vague completion reports.

The distinctive choice is **conditional judgment**. Continue when the scope is clear; ask when a missing decision matters. Verify the work; stop expanding checks without a concrete reason. Be concise; retain information needed to judge the result.

This is a plain Markdown instruction template. No runtime, dependencies, API key, or Skill installation is required. The canonical rules are currently in Chinese; this English README explains their purpose and adoption.

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

1. Open [AGENTS.md](AGENTS.md) and read the rules.
2. Choose the instruction file supported by your agent from the table below. Create it if absent; otherwise **merge**, preserving existing project guidance.
3. Add project facts such as the stack, run/test commands, and deployment constraints.
4. Start a fresh session, inspect loaded instructions where your tool supports it, and try a small task. Check actual behavior as well as the agent's acknowledgment.

Use the project-level entry first. Apply rules globally only if you want them across projects. Avoid loading duplicate copies through several rule mechanisms.

### Ask your agent to help install

After providing it with this repository or the rules file, paste:

```text
Read these AGENTS.md guidelines and merge the general collaboration rules
into the project instruction file supported by this agent.

First inspect existing rules and the tool's loading mechanism. Preserve
project-specific stack, commands, architecture, and constraints. Avoid
duplicated or contradictory instructions.

Modify only instruction files. Report the file changed and how to check
that the instructions are loaded.
```

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

## Origins and evolution

1. **Karpathy-inspired foundation — maintainer recollection.** An early version drew on a GitHub guide related to Karpathy. The current [community guide](https://github.com/multica-ai/andrej-karpathy-skills) shares clear principles with this file; the historical revision is not recovered. It is not a guide authored or endorsed by Karpathy.
2. **Astra-oriented revision — maintainer recollection.** The maintainer recalls asking Codex to adapt the existing guide using OpenAI's documentation about Astra's characteristics. Exact documentation links and per-rule changes are not recovered; this is provenance context, not a verified model-specific optimization claim.
3. **Communication revision — documented.** Ideas from [i-have-adhd](https://github.com/ayghri/i-have-adhd) informed clearer handoffs, layered information, and interruption recovery. Sections 1–3 stayed unchanged; section 4 grew from three bullets to eight. Mandatory per-turn recaps, fixed list limits, and forced time estimates were not adopted.

See the [detailed evolution record](docs/EVOLUTION.md) and [source notices](THIRD_PARTY_NOTICES.md).

## Limits and customization

These rules guide behavior; they do not enforce permissions, guarantee correctness, or override higher-priority instructions. Results depend on the model, harness, context, and project rules. The maintainer has observed changes in responses, but no quantitative effectiveness study has been conducted.

Adapt the template to your work. Keep specific commands and project facts alongside it. If a rule causes friction, record the task, observed behavior, and a focused proposed change rather than adding another blanket rule.

## Contribute

[Open an issue](https://github.com/Richology/richology-agent-guidelines/issues) or submit a focused pull request with:

- Agent and model/version, plus how the rules were loaded.
- A small reproducible task, expected behavior, and what happened.
- A proposed wording change and its possible tradeoff.

Compatibility reports, clearer wording, and translations are welcome. Remove private project data and credentials from examples. Do not mark a tool tested without describing what was checked.

## License and acknowledgments

Richology's original contributions are released under the [MIT License](LICENSE). See [third-party notices](THIRD_PARTY_NOTICES.md) for sources and the retained upstream notice. No affiliation or endorsement by the named model or tool vendors is implied.

The README structure is inspired by [Bookleap](https://github.com/Richology/Bookleap). The cover was generated with OpenAI's built-in image generation tool; its [prompt and provenance](docs/COVER.md) are included.

<div align="center">

**Make the next change clear, focused, and verifiable.**

[Read AGENTS.md](AGENTS.md) · [Share feedback](https://github.com/Richology/richology-agent-guidelines/issues) · [Star this project](https://github.com/Richology/richology-agent-guidelines)

</div>
