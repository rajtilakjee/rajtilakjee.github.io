---
date: 2026-09-04
authors:
  - rajtilak
categories:
  - Meta
  - Developer tools
---

# Hello from the new site

A short first post to prove the blog pipeline works — and to leave a
place for notes on Python, APIs, and the tools I actually use.

<!-- more -->

This site is built with [Material for MkDocs](https://squidfunk.github.io/mkdocs-material/).
The goal is simple: a home page, a resume, and a blog that I can update
without standing up a custom frontend.

## What I plan to write about

- Shipping small developer tools
- Python packaging and CLI design
- Full-stack notes from day-to-day work
- Occasional machine-learning write-ups when a project earns one

## A tiny example

Most of my Python work starts the same way: a virtual environment, a
lockfile, and a command that is boring on purpose.

```bash
uv sync
uv run mkdocs serve
```

!!! tip "Local preview"
    Run `uv run mkdocs serve` from the repo root, then open the URL
    printed in the terminal. Posts in `docs/blog/posts/` show up on the
    blog index automatically.

If you found this because you were looking for the resume, it is
[right here](../../resume/index.md).
