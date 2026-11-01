# How this repository was made (Anambra State)

This file is written by the build on 2026-11-01, the day the source data was retrieved.

## Sources

| Source | Address | Retrieved | Licence |
| --- | --- | --- | --- |
| Anambra State Government: document library, Laws (PDF) | <https://anambrastate.gov.ng/document-library/?doc_category=laws> | 2026-11-01 | Laws of Anambra State, from the copies the Anambra State Government publishes in its document library at anambrastate.gov.ng ("All laws and documents are published by the Anambra State Government"). Official texts of a legislative nature are not eligible for copyright: Copyright Act, 2022 (Nigeria), s. 3(b). |

Every word of law in this repository comes from these sources. Lexifina reads them and records each act's dated versions, and the laws that made each change, in one corpus file. This repository is built from that file.

## What is in it

| Act | Title | Versions | Span |
| --- | --- | ---: | --- |
| `homeland-security-law-2025` | Anambra State Homeland Security Law, 2025 | 1 | 2025-01-17 to 2025-01-17 |

The build made 1 commits:

| Commits | Kind |
| ---: | --- |
| 1 | first version of an act |
| 0 | one law on its in-force day |
| 0 | changes no amendment note explains, credited to the publisher |

Other counts:
- 0 commits on the branch `future`: laws not yet in force on 2026-11-01.
- 0 commits dated 1 January 1970: in force before 1970, with the real day in their `In-force` trailer.
- 1 laws in the record.
- 2 tags.

## Dates

Each commit is dated at noon (Africa/Lagos) on the day the change took effect. The other dates, enacted and published, are trailers.

When a law gives no date of its own, the default rule applies: Each Law here states its own commencement, and its version is dated by it; no general rule is applied. https://anambrastate.gov.ng/document-library/?doc_category=laws

## How the history is built

`tools/build.py` turns the corpus into this history in one pass: one commit per law, on the day it took effect. The same corpus always gives the same commit hashes. `tools/check_repo.py` reads every version back from git and compares it with the corpus. `tools/on.py` shows the law as it stood on any date. The corpus format is described in `tools/SCHEMA.md`.

- Corpus: sha256 `dbfd707e5ae31fb467ae2365527f61dd800d24790e68fb29ec93ba1c4a11402b` (45436 bytes).
- Builder blob hashes (`git hash-object`): `build.py` `0fad90cf931c453951234ecf904d05ee79f3ec7e`, `check.py` `5d719354ea4c62d240c93d2cae446307d81d9e81`, `on.py` `aff48cf1b68d50c7ba8f399ca32261871c301824`.
- Python 3.14.4; git version 2.53.0.

## Checks

1 versions of 1 acts read back from git on the day each took effect and on the day before: 0 mismatches. Trailers: 0 commits whose trailers git cannot parse. Health: 0 merge commits on main, 0 commit dates that go backwards, 0 commits dated after the build.

No second build of this corpus has been compared yet.

## Decisions made by hand

- Homeland Security Law 2025 is dated 2025-01-17, the day section 1 says it "shall come into force on" ("the 17th day of January, 2025").
- Each Law is one version: the text as enacted, credited to the Law itself (first_law) and dated by its commencement. Later amendments are not in this record.
- One file per section. The title lines printed before the enacting formula are "000-title", the enacting formula (where printed) is "001-enacting-formula", and schedules follow the sections. Each section's heading is its printed margin note (or, where there is none, "Section N") and stands as the file's first line; it is not part of the checked text.
- The text layer is read with line positions: running heads, page numbers and margin notes are set apart by their place on the page, and the pieces of one printed row are joined left to right. Lines wrapped by the printer are joined into one paragraph per line; a new paragraph starts at a section number, a bracketed (sub)paragraph letter or number, a quoted definition, a Part heading or a schedule heading. A Part heading printed after a section is placed at the head of the next section. Typing errors in the source stay as printed.

## What AI did and did not do

The scripts that read the sources and build this repository were written by Claude Code running Claude Opus 5.5 (`claude-opus-5-5`) under Lexifina's direction.

No model wrote, translated or corrected legal text. No model runs at build time. Every word of law in this repository comes from the official sources above.

The commit messages are written by `build.py` from the source data.

Model use at data-build time:
- none: the text is the PDF text layer, parsed by rules; no model wrote or corrected legal text.
