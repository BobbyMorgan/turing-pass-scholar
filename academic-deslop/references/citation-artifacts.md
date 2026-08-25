# Citation and reference AI-artifact audit

Inspect citations only for AI/draft residue and internal anomalies, not compliance with APA, Vancouver,
Chicago, or another named style.

First distinguish rendered manuscript references from a source-library database. In `.bib` or exported
reference-manager data, fields such as `file`, `abstract`, `keywords`, `annote`, `urldate`, and other
library metadata may be private and intentionally absent from the rendered bibliography. Do not flag
them merely for existing. Inspect them only when they leak into submitted/rendered text, contain an
obvious AI instruction likely to leak, or the user explicitly asks to clean the database. A BibTeX
`note` field may be legitimate and may render, so judge its content and destination rather than banning it.

## Look for

- unresolved instructions or placeholders: `[insert citation]`, `[citation needed]`, `[add DOI]`,
  `Author, year?`, `REF`, `XXX`, `待补文献`, `请核对`, `此处引用`, `replace with actual source`;
- private notes in entries: `use this paper for`, `supports the claim above`, `verify title`,
  `find page range`, `translated title?`, `complete later`, and equivalents;
- dummy or alternative authors/titles, question marks used as editing notes, truncated fields, prose
  appended to an entry, repeated numbering, stranded markers, or duplicated/near-duplicated entries;
- full-width Chinese punctuation (`，。；：【】（）`) accidentally embedded in an otherwise English entry;
- in-text citations lacking a matching entry, uncited entries, or conflicting keys/numbers when the
  complete manuscript and reference list are available;
- visibly malformed or placeholder DOI/URL syntax. Do not infer whether a plausible DOI or source exists.

Protect punctuation inside genuine Chinese-language titles, authors, bilingual bibliographies, or
journal-required original-language fields. Protect legitimate publication statuses such as `in press`,
`preprint`, `manuscript in preparation`, `unpublished data`, and repository/version labels when clearly
used as bibliographic information.

Preserve citation tokens and placement during prose rewriting. Do not delete, invent, relocate, or
renumber citations without approval.

In LaTeX/BibTeX inputs, preserve `\cite`, `\citet`, `\citep`, `\ref`, `\label`, bibliography commands,
their keys, entry keys, braces, and field syntax. Report residue in field values without corrupting the
database structure.

Report visible prompts/placeholders/private notes as artifacts. Report possible duplicates, malformed
metadata, questionable annotations, or citation-claim relationships as requiring author/source
verification. Missing context limits inventory conclusions. Never call a citation fabricated or
unsupported without checking the actual source; external verification is a separate authorized task.
If no artifact or concrete anomaly is found, omit the citation section entirely; do not report that the
check passed.
