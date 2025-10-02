# Repository Guidelines

## Scope
These rules apply to the entire repository unless a subdirectory provides a more specific `AGENTS.md` file.

## General Expectations
- Follow the project's existing coding style and conventions. Use explicit type hints and keep functions focused and well-documented.
- Prefer small, focused commits with clear messages that explain the *why* as well as the *what*.
- Avoid editing files in `pydantic/v1/` unless a task explicitly calls for it; that subtree is kept for legacy compatibility.

## Python Code
- Format and lint Python with Ruff. Run `ruff check --fix <paths>` followed by `ruff format <paths>` on files you touch.
- Target Python 3.8+ behaviour. Use `typing_extensions` for features that are not available in Python 3.8.
- Keep public APIs type-safe. Add or update annotations as needed and prefer `from __future__ import annotations` in new modules.

## Tests
- Tests are written with `pytest`. Place new tests under `tests/` and give them descriptive names.
- Run `pytest` (or the most specific subset) locally before opening a PR whenever feasible.
- If you add optional-dependency behaviour, mark tests that require it with the appropriate `pytest.importorskip` call.

## Documentation
- Documentation lives in the `docs/` folder and uses MkDocs with the Material theme. Keep page titles in sentence case and add entries to `mkdocs.yml` when creating new pages.
- Prefer linking to the public docs (`https://docs.pydantic.dev`) when referencing existing material.

## Changelog
- Significant user-facing changes should be recorded in the docs changelog per existing patterns. Follow any instructions in more specific `AGENTS.md` files when editing release notes.
