---
name: python
description: Instructions for using python, pip, virtualenv, and running python scripts
---

Always use `uv` when running or managing Python. Never run "naked" python, pip, or virtualenv commands.

### Execution
- **Running a script:** Use `uv run script.py` instead of `python script.py`.
- **One-liners:** Use `uv run python -c "..."` instead of `python -c "..."`.
- **Standard modules:** Use `uv run python -m <module>` (e.g., `uv run python -m http.server`) instead of `python -m <module>`.

### Environment & Packages
- **In a UV project (with `pyproject.toml`):** Use `uv add <package>` instead of manual installation.
- **For ad-hoc/legacy virtual environments:** Use `uv pip install <package>` instead of `pip install` (always run inside a `.venv`).
- **One-off commands with dependencies:** Use `uv run --with <package> <command>` (e.g., `uv run --with requests script.py`) without installing globally.
- **Running CLI tools:** Use `uvx <tool>` (e.g., `uvx ruff check`) instead of installing globally.

### Single-file Scripts with Dependencies (PEP 723)
If a script requires external dependencies, prefer adding an inline metadata block instead of manual installation:
```python
# /// script
# dependencies = [
#   "requests",
# ]
# ///
import requests
```
Then run it directly with `uv run script.py`.
