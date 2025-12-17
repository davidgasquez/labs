# Repository Guidelines

This is an empty repository meant to serve as a sandbox for small experiments, prototypes, and ad-hoc scripts.

- Design for simplicity (simplest thing that could work, KISS)
- Follow the UNIX Philosophy (do one thing and do it well)
- Keep feedback loops short
- After applying changes, verify they work
- Make debugging easy yourself (clean logging, assertions, ...)
- Don't code defensively. Fail early and often. No need to try-catch
- Prefer functional code with small modular functions and components
- Work in small iterate steps
- Write a `README.md` and keep it up to date
- Always gather context/schemas first (API reponses, dataset shapes, ...)
- Run `curl`, other UNIX tools, or temporary Python scripts to gather information before making decisions

### Python Guidelines

- If `uv` is not installed, install it via `pip install uv`
- Use `uv` for anything Python
- Run scripts with `uv run scrip.py` instead of `python`
- Write `uv` compatible self contained Python scripts (dependencies included)
- Run the scripts with `uv run script.py`
- Check linters and fix things
    - `uvx ruff check`
    - `uvx ty check`

#### Example Python Script Header

Start Python scripts with this comment adapted to the relevant dependencies.

```python
#!/usr/bin/env -S uv run --script
# /// script
# requires-python = ">=3.12"
# dependencies = [
#   "polars",
#   "duckdb",
# ]
# ///
import polars as pl
...
```

Run the script with `uv run script.py`.
