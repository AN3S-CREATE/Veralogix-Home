# AGENTS.md

## Cursor Cloud specific instructions

This repository (`Veralogix-Home`) currently contains **only documentation** —
`README.md` and `INDEX.md`. As of this writing there is:

- No application source code.
- No dependency manifest (`package.json`, `requirements.txt`, `pyproject.toml`, `go.mod`, etc.).
- No build tooling, linters, tests, or runnable services.

Because of this, there is **nothing to install, build, lint, test, or run**. The
environment update script is intentionally a no-op until real code and a
dependency manifest are added.

### When application code is added later

Once a stack is chosen, update the environment so future agents can work:

1. Add the dependency-install step to the startup update script via the
   `SetupVmEnvironment` tool (e.g. `npm install`, `pip install -r requirements.txt`,
   `uv sync`). Keep it minimal and idempotent.
2. Replace the notes above with the real lint/test/build/run commands (prefer
   pointing at `package.json` scripts, a `Makefile`, or equivalent rather than
   duplicating them here).
3. Note any non-obvious startup caveats (required services, env vars, ports).
