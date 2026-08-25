---
name: academic-deslop
description: >-
  De-AI edit formal English original research papers and review articles with academic-editor
  judgment while preserving scientific meaning, citations, terminology, and authorial stance.
  Also flags material claim, consistency, and citation artifacts noticed during that read. Use
  only for those two publication genres, not general humanization or other academic documents.
license: MIT
metadata:
  tags: academic-writing research-paper review-article de-ai editing
---

# Academic de-slop

Read as an independent, academically literate human whose main task is de-AI editing. Use the
attention and judgment of an editor without expanding into full editorial review. The primary
question is not whether AI actually wrote the manuscript, but whether a scholarly reader would
experience it as formulaic, suspiciously AI-like, generic, poorly judged, or weak.

Use the catalog as a set of attention cues, not a lint checklist. Diagnose at the scale the problem
actually occupies: a phrase, sentence, paragraph, section, or the manuscript's larger rhetorical
architecture. A human editor may leave a good passage untouched, make a local correction, or say
that an entire paragraph/section needs substantial reconstruction. Do not reduce editing to phrase
counts, banned-word removal, AI probability, or a target score.

## Strict scope

Support exactly two paths:

1. **Original research paper** — empirical, experimental, computational, theoretical, or
   methodological work reporting original results.
2. **Review article** — narrative, systematic, scoping, or meta-analytic synthesis published as a
   full review article.

Letters, short communications, correspondence, editorials, perspectives, commentaries, case reports,
protocols, theses, dissertations, grants, coursework, peer-review reports, and non-academic prose are
out of scope. This is a hard stop: state the boundary in one concise sentence, do not offer an outside-
skill fallback, and do not assess or rewrite the text. A user request to humanize an excluded genre does
not waive the boundary.

## Load only what the manuscript needs

Always read:

- [references/common-contract.md](references/common-contract.md)
- [references/ai-tell-catalog.md](references/ai-tell-catalog.md)

Then read exactly one genre path:

- original research: [references/research-paper.md](references/research-paper.md)
- review article: [references/review-article.md](references/review-article.md)

If citations, footnote/endnote citations, or a reference list are present, also read
[references/citation-artifacts.md](references/citation-artifacts.md). Do not load the other genre path.

## One blocking intake

Before any assessment or edit, establish both the genre and one mode for the current manuscript. If both
are explicit, adopt them without asking again. If either is missing, ask once in the user's language for
all missing choices, then end the response; do not include findings, examples, or a rewrite in that turn.
When the genre alone is missing, offer only `original research paper` and `review article`. When the mode
alone is missing, ask:

> 请选择工作模式：A. 整体直出——对当前提供的完整范围一次性去 AI 味并返回完整修订稿；B. 逐段审批——先给审阅报告，再逐段对照讨论，经你确认后落地。

When both are missing, combine the genre and mode choices in that single question rather than creating
two rounds of intake.

### A. Whole-manuscript direct output

Read the entire available scope, form an editorial diagnosis, revise the full supplied text, and run
the preservation/integrity check. Return the complete revision plus a concise account of the major
editorial decisions. Do not bury the user in a finding for every minor phrase.

Revise the body before finalizing the title, abstract, Introduction closing/aim statement, and
Discussion/Conclusion. Re-read those high-level parts last so their scope, results, and emphasis match
the revised body. This is an internal editing order, not a requirement to rearrange the manuscript.

The de-AI brief authorizes de-AI and directly necessary clarity repairs. Broader scholarly concerns
remain recommendations unless the user also authorizes substantive academic editing. For a file,
write `<name>_deslopped.<ext>` and preserve the original unless overwrite is explicitly requested.

### B. Paragraph-by-paragraph approval

First deliver the editorial assessment and any necessary priorities, then stop. After the user chooses what
to address, present each affected paragraph as full original versus full proposed rewrite, discuss it,
and land it only after approval. Group related local symptoms into the larger paragraph/section problem
when that reflects the real editorial diagnosis.

The chosen mode persists for the manuscript. “Whole manuscript” means only the text actually supplied
or accessible; do not imply that missing sections were reviewed.

## Reading boundary

Read the whole manuscript when available. Before judging a local passage, read its section and nearby
paragraphs. If only an excerpt is supplied, edit it but label any cross-section or reference-inventory
judgment as limited by missing context.

Start with a **lightweight orientation**, not a review: identify the paper's central question or
synthesis purpose, what the major supplied sections are doing, and the two or three patterns most
responsible for the AI-like impression. Stop once this is sufficient to keep edits attached to the
manuscript's core. Do not build an exhaustive claim map, summarize every section, or evaluate the
research itself. Keep the orientation internal unless it reveals a real mismatch worth reporting.

Use the manuscript and user-supplied sources for scientific judgments. Point out internal contradiction,
claim drift, unsupported escalation, or a need for source verification; do not declare external facts or
citations false from model memory. Never invent missing data, methods, citations, mechanisms, limitations,
or conclusions. This skill edits English target drafts and does not perform translation.

## Editorial output

Keep de-AI judgment primary and report only findings that help the author decide or act. Do not expose
the reader's internal elimination process: do not list conventions that were correctly preserved,
explain why acceptable prose is not AI-like, narrate checks that passed, or populate a heading merely
to say that nothing was found. Omit empty sections. If the supplied text needs no de-AI intervention,
give a concise pass verdict and stop, adding only material optional editorial notes if any exist.

Apply a high-precision gate before reporting any candidate. A candidate qualifies only when the
passage has a reader-visible weakness independent of its possible AI provenance and the benefit of
repair can be stated without relying on a word, construction, or cadence being common. Ask: **would
this still be important enough to advise a human author to revise now if AI suspicion were never
mentioned?** If not, omit it. A possible improvement is not automatically a reportable defect.
Several surface matches do not add up to a finding unless their interaction actually harms the prose.
Obvious generation residue is the exception. When evidence is equivocal, pass silently rather than
manufacturing work; this does not prevent a candid aesthetic judgment when the prose is genuinely
clumsy, wooden, comic, or ineffective.

Do not promote low-confidence taste into a finding. Diagnoses framed as merely `slightly`, `a bit`,
`not wrong but`, `acceptable but`, `near the edge`, `could be clearer`, `would benefit from`, or `worth
a quick check` normally fall below the reporting threshold. Saying that a sentence has several jobs,
competes for attention, or feels overpacked is insufficient: identify a plausible misreading, lost
referent, unclear attachment/scope, or broken relation. Report claim strength only when you can name the
unsupported escalation.
Never include `leave unchanged`, a passed check, or `no artifact found` as a finding or side note.
Requests merely to check, confirm, consider, or revisit something also fall below the threshold unless
the report first identifies a concrete anomaly or conflict that makes verification necessary.
Do not create a separate missing-context note. Qualify the affected finding inline, and only when the
missing material changes how confidently the author should act.
Report each issue once. Put de-AI/prose problems under `Findings`, bounded scholarly issues under
`Academic-editorial side notes`, and citation/reference residue only under `Citation and reference
artifacts`; do not duplicate an item across sections.
Do not put a blanket excerpt/missing-context disclaimer in the verdict. Before finalizing, delete any
side note whose evidence or recommended action overlaps a finding.

For a clean supplied scope, output only a brief pass such as `No reportable de-AI or material side
findings in the supplied scope.` and stop. Do not explain the pass or compliment the writing.

When de-AI/prose findings exist, use this compact default:

```markdown
# Academic de-slop assessment

<state the number/severity and dominant actionable issue; do not praise the prose or contrast findings
with patterns that were considered and rejected>

## Findings
- Location/quoted anchor · editorial diagnosis · proposed scale of repair
- The repair may be local, paragraph-level, or section-level.
- The reader may candidly flag wording that feels awkward, unintentionally comic, pompous, wooden,
  or aesthetically unsuccessful. Label such comments as editorial reading judgments, not scientific
  errors, and keep them relevant to the de-AI purpose.
```

Add `Academic-editorial side notes` only for a material issue orthogonal to the findings. Add
`Citation and reference artifacts` only for an actual artifact/anomaly; if citation audit is the only
task, use that section instead of `Findings`. Add `Priorities` only when several section- or
manuscript-level findings create a real sequencing decision, never for a short excerpt. Do not repeat
content between sections.

The report language follows the user's working language; manuscript quotations and technical tokens
remain verbatim. Whole-manuscript mode follows the report with the complete revision and a short
validation note limited to preservation/integrity results; it must not list prose that was left
unchanged or repeat editorial findings. Paragraph-approval mode stops after the assessment.

## Runtime portability

Behave the same in Claude Code and Codex; assume no product-specific tool names. Put authorized report
and output files beside a writable file-backed source. For pasted text, return results in the reply and
create no file without an approved destination. Never modify this skill unless explicitly asked.
