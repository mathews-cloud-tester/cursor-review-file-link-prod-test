# AGENTS.md

## Cursor Cloud specific instructions

This repository is a **minimal test fixture** (internally: "Cursor Review file link
production test"), not a runnable product. The tracked contents are:

- `README.md` — a single title line
- `.github/CODEOWNERS`
- `src/owned-file.txt` — a plain text file
- (on some fixture branches only) `snippet_mismatch_fixture.py` — a small standalone
  Python snippet used as a review/diff fixture

There is **no application, no dependency manifest, no build system, no test suite, and
no lint configuration**. As a result:

- There is **nothing to install** — the startup update script is intentionally a no-op.
- There is **no application to build or run**, and **no lint/test commands** to execute.
- The environment's baseline toolchain (git, `python3`, `node`) is sufficient for any
  ad-hoc work on the fixture files; no project-specific setup is required.

If real application code is added later (e.g. a `package.json` or `requirements.txt`
appears), update the startup script and this section accordingly.

### Optional GitHub OAuth browser session

For browser-based testing that needs a **fully authenticated GitHub OAuth session**,
use the Desktop pane login external action (`desktop_login`) when needed. This is
**optional**: a seeded local browser session may already be enough, and CLI `gh`
auth (token in `~/.config/gh`) is separate from browser cookies and does not
satisfy OAuth UI flows. Session/cookie persistence in VM snapshots depends on
GitHub and may expire or be invalidated.
