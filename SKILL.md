---
name: pdf-endnote-ieee-citation-renamer
description: Use when the user provides academic PDF files and wants EndNote .enw/.env import files, IEEE citations, DOI/arXiv/Crossref metadata checking, or systematic literature PDF renaming.
---

# A Skill to Generate EndNote/IEEE Citations From PDF Documents and Rename Them

## Core Contract

For each user-provided literature PDF, produce two deliverables and manage the source file:

- Write an EndNote tagged import file in the same directory as the PDF.
- Output the IEEE citation in chat.
- Rename the PDF to match the EndNote file stem.

Treat the user's `env` wording as EndNote `.enw` unless they explicitly request another extension.

## Metadata Workflow

1. Extract evidence from the PDF first: metadata, title page, DOI line, author block, journal header/footer, dates, volume/issue/pages/article number, arXiv ID, and abstract.
2. Use available local tools: prefer `pypdf`, PyMuPDF/`fitz`, `pdfinfo`, and `pdftotext`; inspect enough pages to avoid missing IEEE/Elsevier footers.
3. Unless the user says not to search, verify DOI/arXiv/publisher records using reliable sources such as Crossref, arXiv, DOI pages, IEEE Xplore, Elsevier, Springer, or publisher metadata.
4. If a preprint has a formal journal record, use the formal record for citation and filename. Preserve preprint differences in `%Z` notes when useful.
5. Never invent missing DOI, author, journal, volume, issue, pages, or date fields. If unavailable, omit or use an honest status label.

## File Naming

Use this stem for both `.pdf` and `.enw`:

```text
FirstInitial_Last+Title_Snippet+Journal_Abbrev_or_Status+YYYY.MM
```

Rules:

- First author format: `F_Last`; use `Unknown_Author` only when the PDF contains no author evidence.
- Title snippet: remove punctuation, join words with `_`, and keep at most the first 8 title words, roughly matching the user's 30-letter brevity preference.
- Segment separator: use `+` between author, title, journal/status, and date.
- Journal segment: use a standard abbreviation when known, with spaces converted to `_`, such as `IEEE_Trans_Power_Syst`; use `arXiv`, `Draft_Manuscript`, or `Unpublished_Manuscript` when appropriate.
- Date segment: prefer official print/issue date; otherwise online date; otherwise arXiv submission date; otherwise PDF creation/modification date. Format `YYYY.MM`.
- Before overwriting an existing target PDF, compare hashes. Do not delete a different file. If the PDF is locked, write the `.enw`, report the lock, and retry after the user closes the viewer.

## EndNote `.enw` Fields

Use EndNote tagged import format. Include only supported facts.

```text
%0 Journal Article
%A Last, Given
%D 2026
%T Title
%J Journal Name
%V Volume
%N Issue
%P Pages or article number
%@ ISSN
%8 Publication date
%9 Article type or status
%R DOI
%U DOI/arXiv/publisher URL
%W Verification source
%Z Notes, such as arXiv/preprint title mismatch
%X Short abstract summary
%F CitationKey
```

Common mappings:

- Journal article: `%0 Journal Article`
- arXiv/preprint: `%0 Electronic Article`, `%J arXiv`, `%N arXiv:id`
- Draft/unpublished manuscript: `%0 Unpublished Work`, status in `%9`
- Authors: one `%A` line per author
- DOI: `%R` without `https://doi.org/` prefix

## IEEE Citation

Output the IEEE citation in chat after file work. Use standard IEEE ordering: authors, quoted title, italicized abbreviated venue, volume/issue/pages or article number, month/year, DOI. Do not hallucinate missing fields.

For article-number journals, prefer:

```text
Z. Ni et al., "Title," Journal, vol. 419, Art. no. 128068, Sep. 2026, doi: ...
```

For unpublished drafts:

```text
Author(s), "Title," unpublished manuscript, Month Year.
```

If no author is present:

```text
"Title," draft manuscript, Month Year.
```

## Final Response

Keep the final concise:

- list the renamed PDF path and `.enw` path;
- provide the IEEE citation;
- mention verification source or any missing/ambiguous metadata.
