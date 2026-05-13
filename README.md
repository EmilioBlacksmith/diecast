# Diecast (WIP)

> **The Anvil for LLM Agents.** Trace trajectories, cast golden standards, and forge cohesive behavior.

---

### WORK IN PROGRESS
**Diecast is currently in active development.** The codebase is shifting rapidly. Expect breaking changes, missing features, and the occasional terminal-melting bug. We are building in public to get early feedback—feel free to watch the progress, but maybe don't trust it with your production pipeline just yet.

---

## What is Diecast?

Most AI tools tell you *what* happened. **Diecast** shows you *how* it happened and lets you **fix it into place.**

When building complex agentic workflows (LangGraph, CrewAI, AutoGen), behavior is probabilistic and "liquid." Diecast allows you to hook into your agent's execution, trace its reasoning in a beautiful TUI, and "cast" a perfect run into a solid, immutable **Die** (a unit test).

Think of it as **Behavior-Driven Development (BDD) for LLMs.**

## Key Features

*   **Zero-Code Instrumentation:** Wrap any command (e.g., `diecast run -- uv run main.py`) to intercept LiteLLM and framework-specific calls without changing a line of source code.
*   **Live TUI Dashboard:** A keyboard-driven Terminal User Interface built with `Textual` to monitor thoughts, tool calls, and costs in real-time.
*   **The "Die" (Golden Standards):** Found a perfect agent response? Press `S` to snapshot the entire trajectory. This becomes your "Golden Record" for future testing.
*   **BYOJ (Bring Your Own Judge):** Use your own tokens and preferred models (local or cloud) to act as the evaluator for your test suites.
*   **Framework Agnostic:** Built-in interceptors for LiteLLM, LangGraph, CrewAI, and more.

## Quick Start

```bash
# Clone and install
git clone https://github.com/EmilioBlacksmith/diecast.git
cd diecast
uv sync

# Run the CLI
diecast --help
```

## The Workflow

1. TRACE: Use the TUI to watch your agent think and interact with tools.
2. CAST: Once you see a perfect, cohesive response, capture it as a Die.
3. HAMMER: Run diecast test in your CI/CD. Diecast will re-run the agent and use your "Judge" model to ensure the output still matches the quality and logic of your original Die.

## Roadmap
[ ] Core sitecustomize.py injector for auto-instrumentation.
[ ] LiteLLM & LangGraph basic event interceptors.
[ ] Initial Textual TUI (Trace View).
[ ] Exporting traces to YAML "Dies".
[ ] LLM-as-a-Judge assertion framework.
[ ] Cloud-sync for team dashboards (Diecast Forge).

## Contributing

We love contributions! Whether you're fixing a bug or adding a new framework interceptor, please read our [Contributing Guidelines](CONTRIBUTING.md) to get started.

---

## License
Distributed under the Apache License 2.0. See LICENSE for more information. This means it's enterprise-ready, patent-protected, and free to use in your own projects.

Built by developers, for developers. Let's make LLM behavior deterministic.

---
**Forged by [EmilioBlacksmith](https://github.com/EmilioBlacksmith)**