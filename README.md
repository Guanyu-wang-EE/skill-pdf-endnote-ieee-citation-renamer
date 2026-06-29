# PDF EndNote IEEE Citation Renamer Skill

A metadata reconciliation skill for academic PDFs, EndNote import records, IEEE citations, and systematic PDF renaming.

This repository is the Git-backed source mirror for the skill. Repository documentation belongs here; installed runtime copies should stay lean and contain only files needed for execution.

## What It Does

- Extracts and reconciles bibliographic metadata from PDFs and trusted external records when available.
- Generates EndNote ENW fields and IEEE-style citation strings from verified metadata.
- Builds safe, deterministic PDF rename plans without overwriting the original files silently.

## When To Use

Use this skill when the task matches the description in `SKILL.md`. Read `SKILL.md` first, then follow its routing table before opening references, scripts, assets, or indexed resources.

Typical use cases:

- Extract candidate metadata from the PDF text and visible first-page information.
- Verify DOI, title, authors, venue, year, pages, and identifiers against available trusted sources.
- Produce ENW content, IEEE citation, and rename mapping with unresolved conflicts clearly marked.

## Repository Contents

- `SKILL.md`

## Operating Contract

- Do not invent DOI, title, authors, venue, year, pages, arXiv ID, or IEEE fields.
- Report conflicting metadata instead of silently choosing one record.
- Do not rename destructively until the target mapping is explicit.

## Validation And Review

- Check `SKILL.md` frontmatter before changing skill discovery metadata.
- Keep `## Hard Gates`, `## Reference Routing`, and `## Verification` aligned with the actual files in this repository.
- If a `references/final-quality-gates.md` file exists, use it before any final, ready, published, submitted, or complete claim.
- If a skill-specific audit script exists, run it after changing routed files or deterministic helpers.

## Maintenance Notes

- Keep `SKILL.md` as the entry point and router.
- Keep detailed domain material in `references/` when the skill has reference files.
- Keep deterministic helpers in `scripts/` or `tools/` and validate them after edits.
- Update `README.md` and `README_zh.md` together so both languages describe the same scope and gates.
- Do not move repository-only documentation into installed runtime copies.

## Language Parity

`README_zh.md` is the Simplified Chinese counterpart of this file. When one README changes, update the other in the same commit.
