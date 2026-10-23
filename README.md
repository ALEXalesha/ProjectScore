# ProjectScore

**Planned.** A local web page that takes a project (a folder, a repository link or a ZIP) and gives it a detailed
score: tests and branch coverage, mutation testing, code quality, security and personal data, how the app looks,
build and release, speed and memory. Strengths, weaknesses and a list of findings with file and line.

[Русская версия](README.ru.md)

[![License](https://img.shields.io/badge/license-MIT-blue)](LICENSE)
[![Status](https://img.shields.io/badge/status-planned-lightgrey)](docs/superpowers/specs/2026-10-24-projectscore-design.md)

[![Built with Claude Code](https://img.shields.io/badge/Built_with-Claude_Code-D97757?logo=claude&logoColor=white)](https://claude.com/claude-code)

Code, tests and docs are written by Claude (Anthropic) in Claude Code. Ideas, testing and decisions - Alexey.

## Status

There is no code yet. The design note
([docs/superpowers/specs/2026-10-24-projectscore-design.md](docs/superpowers/specs/2026-10-24-projectscore-design.md),
in Russian) waits for Alexey's go-ahead. This README describes the plan, not a working program.

## What it will check

| Section | Weight | What |
|---|---|---|
| Tests | 35 | Test run, slow and flaky tests, branch coverage (core logic and all non-UI code), mutation testing, repeated start without memory growth |
| Code | 20 | Complexity, long files and functions, duplicates, dead code, linter warnings, a tile map of risky places |
| Security | 15 | Secrets in code and git history, personal data, vulnerable and outdated packages |
| Look | 10 | Headless screenshots in both themes and three sizes, readability rules, accessibility |
| Build and release | 10 | Builds, version consistency, tags and releases, CI status, mirrors in sync |
| Docs | 5 | README in two languages, header, screenshots, license, changelog, fresh numbers, texts and translation |
| Speed | 5 | Start time, memory, build size |

Languages in the first version: Python, JavaScript (Electron and web), C# WPF, Lua game mods.

## How it will work

- A small Node server on the PC and a page in the browser (five themes, Russian and English, phone-friendly).
- One click scores every project and shows a ranking; each score is saved, so you see the history.
- The same check runs from the command line, so a coding agent can score its own work before handing it in.
- Reports are saved as Markdown and HTML outside the repositories.

## License

MIT - see [LICENSE](LICENSE).
