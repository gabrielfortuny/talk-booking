.PHONY: ci lint typecheck test sync

ci: lint typecheck test

sync:
	uv sync --locked --all-extras --dev

lint: sync
	uv run ruff check .
	uv run ruff format --check .

typecheck: sync
	uv run mypy .

test: sync
	uv run pytest --cov=web_app --cov-report=term-missing
