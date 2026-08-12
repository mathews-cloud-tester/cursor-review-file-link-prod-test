# AGENTS.md

## Cursor Cloud specific instructions

This repository is a **test fixture**, not a runnable software product. It exists to exercise
Cursor's code-review / file-link and CODEOWNERS-ownership tooling against a real GitHub repo.

What it contains:

- `README.md` — a one-line title.
- `src/owned-file.txt` — a file covered by `CODEOWNERS` (`* @mathews-cloud-tester`), used for file-link/ownership tests.
- `stack-active-agent.txt` / `stack-active-manual.txt` — writable marker files used to verify write access.
- `.github/CODEOWNERS` — assigns ownership of all files for review tests.

There is intentionally **no application, package manager, dependency manifest, build system, lint config, or test suite**.

Implications for future agents:

- Nothing to install: there is no `package.json`, `requirements.txt`, `Makefile`, Dockerfile, or CI setup step. The environment update script is a no-op.
- Nothing to lint/build/run: do not hunt for a dev server, build command, or test runner — none exist.
- The only "functionality" is standard git behavior on these text files. Verify changes with `git status` / `git diff` and normal commit/push flow.
- Node.js (v22) and Python 3.12 happen to be preinstalled on the VM, but this repo does not use them.
