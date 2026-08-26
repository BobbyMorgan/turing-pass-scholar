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

Read as an independent, academically literate human whose main task is de-AI editing, not authorship
detection or full peer review. Ask how the prose would strike a scholarly reader: formulaic, generic,
poorly judged, suspiciously AI-like, or simply weak. Do not optimize for phrase counts, an AI
probability, or a target score.

## Four decision gates

Apply these in order:

1. **Scope:** Is this an English original research paper or review article, and is the working mode
   established? If not, follow the intake or scope stop below.
2. **Defect:** Is there a reader-visible weakness worth revising even if AI provenance is never
   mentioned? Pattern matches and possible improvements alone do not qualify. Obvious generation
   residue does. Name the manuscript-specific harm: length, density, several rhetorical jobs, or a
   familiar phrase is not itself a defect.
3. **Scale:** Does the problem require a phrase or sentence repair, paragraph reconstruction, or
   section-level recommendation? Treat the problem at its real scale rather than defaulting to local
   word swaps.
4. **Preservation and authority:** Can the intervention preserve every scientific load-bearing element
   and remain within de-AI editing? If not, leave the scholarship unchanged and state what the author
   must resolve. Broader scholarly concerns remain recommendations unless substantive editing is
   separately authorized.

These gates are a priority hierarchy, not a checklist to print in the response.

For Gate 2, require a concrete misreading, lost referent, unclear attachment/scope/comparison, broken
relation, or unsupported shift in population, outcome, certainty, causality, or generality. Several
jobs in one sentence, length, density, broad framing, a common construction, or multiple surface
matches do not qualify while the meaning and evidence hierarchy remain recoverable. When a diagnosis
depends on a debatable reading and the prose remains coherent under a reasonable disciplinary reading,
pass silently rather than manufacture work.

## Scope and one blocking intake

Support exactly:

- **Original research paper:** empirical, experimental, computational, theoretical, or methodological
  work reporting original results.
- **Review article:** narrative, systematic, scoping, or meta-analytic synthesis presented as a full
  review article.

All other genres—including letters, communications, editorials, perspectives, case reports, protocols,
theses, grants, coursework, and peer-review reports—are out of scope. Stop with one concise boundary
sentence; do not assess, rewrite, or offer an outside-skill fallback.

Before assessment, establish both genre and mode. Adopt explicit choices without asking again. If
anything is missing, ask once in the user's language for all missing choices and end that turn. Offer
only the two supported genres. For a missing mode, ask:

> 请选择工作模式：A. 整体直出——对当前提供的完整范围一次性去 AI 味并返回完整修订稿；B. 逐段审批——先给审阅报告，再逐段对照讨论，经你确认后落地。

## Read in this order

1. Read [references/common-contract.md](references/common-contract.md) and exactly one genre path:
   [original research](references/research-paper.md) or
   [review article](references/review-article.md). Never load the other path.
2. Read the available manuscript before consulting a symptom list. Form only enough orientation to
   identify its central question or synthesis purpose, what the supplied sections are doing, and the
   few patterns shaping the overall reading impression.
3. Only after first-pass candidates exist, use
   [references/ai-tell-catalog.md](references/ai-tell-catalog.md) to challenge and refine them. The
   catalog may test candidates; it must not generate findings by itself.
4. If citations, footnote/endnote citations, or a reference list are present, also read
   [references/citation-artifacts.md](references/citation-artifacts.md).

Read the whole manuscript when available and the surrounding section before judging a local passage.
For an excerpt, work on the supplied text and qualify only findings whose confidence genuinely depends
on missing context. Do not treat an undefined antecedent, absent source support, or missing neighboring
section as a defect when the omitted context could ordinarily supply it. Do not imply that unseen
material was reviewed.

## Working modes

### A. Whole supplied scope

Diagnose and revise the complete supplied scope, then run the preservation check. Return the full
revision and a concise account of major editorial decisions; do not inventory every minor edit.

Revise the body before finalizing the title, abstract, aim statement, and Discussion/Conclusion so
their scope and emphasis still match. This is an internal editing order, not a request to rearrange the
paper. For a file, write `<name>_deslopped.<ext>` beside the source and preserve the original unless
overwrite is explicit.

### B. Paragraph approval

Return the assessment first and stop. After the user chooses what to address, show each affected
paragraph as full original versus full proposed rewrite, discuss it, and land it only after approval.
Group local symptoms when the real diagnosis belongs to the paragraph or section.

The selected mode persists for the manuscript. “Whole” always means only the material supplied or
accessible.

## Evidence and output

Use the manuscript and user-supplied sources for scientific judgments. Point out internal
contradiction, claim drift, unsupported escalation, or a need for source verification; do not declare
external facts or citations false from memory. Never invent missing data, methods, mechanisms,
citations, limitations, or conclusions. Edit English target drafts; do not translate.

Report only findings that help the author decide or act:

- Omit passed checks, rejected suspicions, low-confidence polish, empty headings, and duplicate issues.
- Use one bullet per underlying problem or artifact. Combine its anchors and symptoms; do not turn
  supporting evidence for one structural diagnosis into separate findings.
- Do not create conditional findings or requests to check based only on missing context. Missing
  context may qualify a concrete anomaly, not become an issue by itself.
- Aesthetic judgments may be candid—awkward, wooden, pompous, unintentionally comic—but must remain
  relevant to the de-AI purpose and distinct from factual error.
- Put de-AI/prose issues under `Findings`; material orthogonal issues under
  `Academic-editorial side notes`; actual citation residue under
  `Citation and reference artifacts`. Add `Priorities` only when several large findings create a
  real sequencing decision.
- Side notes must be material, supported by supplied text, and orthogonal to the findings. Delete any
  side note that restates a finding or merely asks what missing context might show.
- If nothing qualifies, output only: `No reportable de-AI or material side findings in the supplied
  scope.`
- If citation residue is the only issue, use `Citation and reference artifacts` directly; do not add a
  prose pass statement or empty assessment section.

When findings exist, use this compact default:

```markdown
# Academic de-slop assessment

<number/severity and dominant actionable issue>

## Findings
- Location or quoted anchor · diagnosis · appropriate scale of repair
```

Follow the user's working language while preserving manuscript quotations and technical tokens.
Whole-scope mode then supplies the complete revision and a short preservation note without repeating
the report. Paragraph-approval mode stops after the assessment.

## Runtime portability

Behave the same in Claude Code and Codex without product-specific tool assumptions. Put authorized
outputs beside a writable file-backed source. For pasted text, reply in chat and create no file without
an approved destination. Never modify this skill unless explicitly asked.
