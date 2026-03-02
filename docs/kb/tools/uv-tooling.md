# UV Tooling Reference: Latium Codex

This document serves as the primary technical reference for managing the Python environment of the Latium Codex compiler and its associated automation scripts using `uv`.

## 1. Project Management (The `compiler/` module)

Use these commands inside the `compiler/` directory to manage the language's core logic.

### Core Commands

* **Initialize:** `uv init --lib` (Creates the structure for a library/compiler).
* **Sync Environment:** `uv sync` (Ensures your `.venv` matches the `uv.lock` exactly).
* **Run Code:** `uv run python -m src.main` (Runs your entry point in the project context).
* **Lock Dependencies:** `uv lock` (Manually refresh the lockfile without installing).

### Dependency Control

* **Add Library:** `uv add <package>` (Adds to `dependencies` in `pyproject.toml`).
* **Add Dev Tool:** `uv add --dev pytest ruff` (Adds to `dev-dependencies`).
* **Remove:** `uv remove <package>`.

---

## 2. Universal Tool Execution (`uvx`)

Use `uvx` (shorthand for `uv tool run`) to run tools without adding them to your project's `pyproject.toml`. This keeps the compiler environment lightweight.

* **Linting:** `uvx ruff check .`
* **Formatting:** `uvx ruff format .`
* **Type Checking:** `uvx mypy src/`
* **One-off Scripts:** `uvx pycowsay "Latium Codex Prototype"`

---

## 3. Python Version Management

`uv` manages Python versions automatically. It will download the required version if it’s missing from your system.

* **List Versions:** `uv python list` (Shows installed and available versions).
* **Install Version:** `uv python install 3.12`.
* **Pin Version:** `uv python pin 3.11` (Creates a `.python-version` file for the directory).

---

## 4. Single-File Scripting (PEP 723)

For automation scripts (e.g., a script to generate Latin documentation), use **Inline Metadata**. This allows a single `.py` file to be completely self-contained.

### Creating a Managed Script

1. **Initialize:** `uv init --script gen_docs.py`
2. **Add Dependencies:** `uv add --script gen_docs.py "rich>=13.0"`
3. **Execute:** `./gen_docs.py` (if shebang is present) or `uv run gen_docs.py`.

**Script Header Example:**

```python
# /// script
# requires-python = ">=3.11"
# dependencies = [
#     "rich",
#     "mako",
# ]
# ///

```

---

## 5. CI/CD Integration (GitHub Actions)

`uv` is optimized for CI. Use the official setup action for the fastest builds.

```yaml
steps:
  - uses: actions/checkout@v4
  - name: Install uv
    uses: astral-sh/setup-uv@v5
    with:
      enable-cache: true
  - name: Run Tests
    run: uv run pytest

```

---

## 6. Best Practices for Latium Codex

* **Always commit `uv.lock**`: This is your guarantee that the transpiler behaves identically on your machine and the CI runner.
* **Use `uv run` for all execution**: Avoid `python main.py`. Using `uv run` ensures you never accidentally use the wrong system Python or missing dependencies.
* **Path-Based Sync**: If you are in the root directory, you can run compiler tests with `uv run --project compiler pytest`.
