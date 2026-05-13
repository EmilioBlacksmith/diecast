# Contributing to Diecast 

First off, thank you for considering contributing to **Diecast**! We are building the anvil where LLM agents are forged into reliable, deterministic tools. 

By contributing to Diecast, you agree that your contributions will be licensed under its **Apache 2.0 License**.

---

## Technical Architecture

Diecast operates on a **Zero-Footprint** principle. Contributors must ensure that:
1.  **Non-Invasive:** We use `sitecustomize.py` and monkeypatching to intercept events. The user's business logic must remain untouched.
2.  **Performance First:** Interceptors must have near-zero latency. If an interceptor adds >5ms overhead to an LLM call, it must be optimized.
3.  **Async-Safe:** The TUI runs on a separate event loop. All data passing between the "Agent" process and the "TUI" process must be non-blocking.

---

## Development Workflow

We use `uv` for dependency management.

### 1. Setup
```bash
# Fork and clone the repo
git clone [https://github.com/EmilioBlacksmith/diecast.git](https://github.com/EmilioBlacksmith/diecast.git)
cd diecast

# Create environment and install in editable mode with dev dependencies
uv venv
source .venv/bin/activate
uv pip install -e ".[dev]"
```

### 2. Adding a Framework Interceptor

If you are adding support for a new framework (e.g., Agno, PydanticAI):
1. Locate diecast/core/_injector/sitecustomize.py.
2. Implement a lightweight custom_import check.
3. Ensure your patch captures: Prompt, Tools Used, Output, Tokens, and Latency.

### 3. Style Guidelines
- Typing: All new functions must have Python type hints.
- Linting: We use ruff for linting and formatting. Run ruff check . before committing.
- Naming: Use "Metallic" terminology for internal variables where appropriate (e.g., forge, mold, anvil, ingot).

## 📥 Pull Request Process
1. Issue First: For major features, please open an issue first to discuss the approach.
2. Atomic Commits: Keep your commits small and focused.
3. Branch Naming: Use feat/, fix/, or docs/ prefixes (e.g., feat/add-ollama-support).
4. Tests: If you're fixing a bug, add a regression test in the tests/ directory.

## The Metallic Philosophy
- Deterministic > Probabilistic: We build tools that make AI predictable.
- Standardization: A "Die" (test case) should be shareable across different models.
- TUI Craftsmanship: The terminal is a professional workspace. Keep the UI clean, high-contrast, and fast.

Thank you for helping us forge the future of LLM testing!
— EmilioBlacksmith