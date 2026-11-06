# Anambra State: law history in git

Part of [lexifina/global-law](https://github.com/lexifina/global-law), one git history for every country's law: this is the law of Anambra State, Nigeria, which global-law reads at `nigeria/anambra/acts/`.

The Laws of Anambra State (Nigeria) as a git history: one file per section, one paragraph per line, so `git blame`, `git log` and `git diff` work line by line. The text is the English text of the Laws as enacted.

It follows the shared design of [lexifina/global-law](https://github.com/lexifina/global-law).

## What this repository holds

**A first build: Laws as enacted.** The Anambra State Government publishes a small number of Laws as PDFs. Each Law here is one commit holding its text as enacted, dated by its commencement and credited to the Law itself. Amendments made since are not yet in this record.

| Folder | What |
| --- | --- |
| one folder per Law (e.g. `homeland-security-law-2025/`) | the Law as enacted: `000-title.md`, one file per section, then any schedules |

The Laws are added in parts as each is verified. Only PDFs with a text layer are used; scanned copies (pictures of pages) are left out, as are Bills and appropriation (budget) Laws.

Known gaps in the source: The Homeland Security Law 2025 is the printed impression the Clerk of the Legislature certified for the Governor's assent: its Law number and assent date are blank in the copy, and its two Schedules print only their headings. It is dated by the commencement day in its section 1.

## Source

[Anambra State Government](https://anambrastate.gov.ng/document-library/?doc_category=laws): PDFs of the Laws. Each PDF's sha256 is recorded with its version in `data/versions.json`.

## Dates

Each Law is dated by the day it came into force under its own commencement provision, at noon in Lagos time (West Africa Time, UTC+1).

## How it is built

Lexifina reads the sources listed here and records each act's dated versions, and the laws that made each change, in one corpus file. `tools/build.py` writes this repository from that file, and the same corpus always gives the same commit hashes; `REPRODUCE.md` gives the details and the checks. A model (Claude) wrote Lexifina's code; it wrote no legal text, and no model runs when the history is built.

The text layer of each PDF (no OCR) is read with the position of every line: running heads, page numbers and margin notes are set apart by their place on the page, and each section's margin note stands as the first line of its file. Lines wrapped by the printer are joined, so each paragraph is one line. Typing errors stay as printed.

## How it is checked

Every version is read back from git on the day it took effect and must match the corpus. A second, independent reading of every PDF (a different PDF engine) must contain every letter and digit of each Law in the same order, with nothing in the body left out (only page furniture and margin notes may lie between). Results are in `REPRODUCE.md`.

## What "author" means

The author of each commit is the Law that made the change, with an e-mail address that cannot exist; the committer is always Lexifina.

## Limits

Only the Laws listed above, as enacted; later amendments are not applied. The Government's PDFs are not the authoritative text; the Anambra State Official Gazette is.

## Licence

See [LICENSE](LICENSE): official texts of a legislative nature are not eligible for copyright in Nigeria (Copyright Act, 2022, s. 3(b)). Source: Anambra State Government.
