# PDF EndNote IEEE Citation Renamer Skill

<p align="right"><strong>English</strong> | <a href="README_zh.md">简体中文</a></p>

A metadata reconciliation skill for academic PDFs, EndNote import records, IEEE citations, and systematic PDF renaming.

This repository is the Git-backed source mirror for the skill. Repository documentation belongs here; lean installed runtime copies should contain only files needed by the skill itself.

## Table Of Contents

- [Purpose](#purpose)
- [Repository Map](#repository-map)
- [How To Use](#how-to-use)
- [Core Contracts](#core-contracts)
- [Resource Index](#resource-index)
- [Validation Commands](#validation-commands)
- [Maintenance Notes](#maintenance-notes)
- [Language Parity](#language-parity)

## Purpose

Use this skill when the task matches the description in [`SKILL.md`](SKILL.md). Read `SKILL.md` first, then follow its routing before opening references, scripts, or assets.

Primary capabilities:

- Extracts and reconciles bibliographic metadata from PDFs and trusted external records when available.
- Generates EndNote ENW fields and IEEE-style citation strings from verified metadata.
- Builds safe, deterministic PDF rename plans without overwriting the original files silently.

## Repository Map

| Path | Role |
|---|---|
| [`SKILL.md`](SKILL.md) | Entry point, hard gates, routing, and verification guidance |
| [`README.md`](README.md) | English repository navigation |
| [`README_zh.md`](README_zh.md) | Simplified Chinese repository navigation |

## How To Use

1. Open [`SKILL.md`](SKILL.md).
2. Use its reference routing table to load only the task-relevant files.
3. Run the deterministic helper or validation command that matches the artifact under review.
4. Before any final, ready, published, submitted, or complete claim, check final gates when the skill provides them.

## Core Contracts

- Do not invent DOI, title, authors, venue, year, pages, arXiv ID, or IEEE fields.
- Report conflicting metadata instead of silently choosing one record.
- Do not rename destructively until the target mapping is explicit.

## Resource Index

No bundled reference, script, or asset directory is present. Use [`SKILL.md`](SKILL.md) as the source of truth.

## Validation Commands

Run checks that match the files changed:

```bash
python path/to/quick_validate.py .
```

## Maintenance Notes

- Keep [`SKILL.md`](SKILL.md) short and route details to references when the skill has them.
- Update README files when hard gates, references, scripts, or expected outputs change.
- Keep repository-only documentation in this Git mirror, not in lean installed runtime copies.
- Update [`README.md`](README.md) and [`README_zh.md`](README_zh.md) in the same commit.

## Language Parity

[`README_zh.md`](README_zh.md) is the Simplified Chinese counterpart of this file. The two READMEs should have the same sections, claims, gates, commands, and maintenance expectations.

