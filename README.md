# rdl-python-poetry-tool

Test fixture for the `remove_duplicate_lockfiles` maintenance task.

## Scenario

Python conflict at repo root — `pyproject.toml` has a `[tool.poetry]` section.

Lockfiles:
- `poetry.lock`
- `uv.lock`

## Expected MT behaviour

- **Auto-detects** poetry via the `[tool.poetry]` table in `pyproject.toml` — no user question.
- **Deletes** `uv.lock`, keeps `poetry.lock`.
- **Appends** `uv.lock` to `.gitignore`.
