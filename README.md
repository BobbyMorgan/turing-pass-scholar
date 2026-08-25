# Turing-Pass Scholar

> **Built to pass a human editor, not an AI detector.**

[English](README.md) | [简体中文](README.zh-CN.md)

Academic de-AI editing for **English original research papers and review articles**, packaged as one portable Agent Skill for Claude Code and Codex.

Turing-Pass Scholar reads like a demanding academic editor. It does not guess who or what wrote a manuscript. It asks whether the prose would strike a scholarly reader as formulaic, generic, poorly judged, suspiciously AI-like, or simply weak—and intervenes only when there is a real writing problem to solve.

**Remove the AI impression. Keep the science.**

## What makes it different

### Human judgment, not a blacklist

No banned-word counts, mechanical sentence variation, AI probability, or target score. Familiar patterns are attention cues, not verdicts. A finding must identify a reader-visible weakness that would still deserve revision if AI provenance were never mentioned.

### Rewrite boldly. Preserve precisely.

The right intervention may be one phrase, a paragraph reconstruction, or a section-level recommendation. The skill does not hide structural problems behind synonym swaps—but it treats numbers, statistics, uncertainty, causal strength, terminology, citations, cross-references, mathematics, LaTeX, BibTeX, and authorial stance as load-bearing.

### Two genres, two reading paths

- **Original research papers:** higher tolerance for first person, precise repetition, functional enumeration, dense Results prose, technical signposting, and figure or section references.
- **Review articles:** closer scrutiny of empty synthesis, generic taxonomies, paper-by-paper listing, false consensus, vague attribution, and unsupported claims of comprehensiveness.

This is not a generic “academic mode.” Each genre receives different editorial attention.

### Findings, not busywork

The report contains only issues worth acting on. It does not list checks that passed, praise acceptable conventions, or force edits to demonstrate activity. Clean prose receives a brief pass. Material claim drift, ambiguity, terminology conflict, and citation residue may be flagged when noticed during the same de-AI read, without turning the task into peer review.

## What it catches beyond prose

Reference lists and citations are checked for AI or draft residue such as prompts, private notes, unresolved placeholders, malformed DOI/URL placeholders, and accidental full-width Chinese punctuation. The skill protects legitimate reference-manager metadata and does not enforce APA, Vancouver, or another named style.

It works with complete manuscripts, individual sections, and short excerpts. When context is incomplete, it never implies that unseen material was reviewed.

## Choose how edits land

1. **Whole supplied scope** — diagnose and revise everything supplied, then return the complete edited text with a concise preservation note.
2. **Paragraph approval** — return the editorial assessment first, then discuss and apply affected paragraphs only after approval.

The skill asks once for any missing genre or mode choice before editing.

## Install

```bash
npx skills add BobbyMorgan/turing-pass-scholar
```

## Use

```text
这是 original research paper 的 Discussion 片段。选择 B，只出报告，不要改写。
```

```text
This is a review article. Use whole-supplied-scope mode, preserve every citation,
and return the complete de-AI revision.
```

## Strict boundary

Turing-Pass Scholar supports only English original research papers and review articles. Other academic genres and non-academic writing are out of scope. It does not perform AI-authorship detection, translation, external fact checking, strict reference-style compliance, plagiarism review, or methodology, statistics, ethics, and reporting-guideline review. Tables are audit-only.

## Validation

v1.0.0 was tested in isolated Codex sessions on de-identified pre-generative-AI academic prose, model-generated research and review prose, complete manuscripts and excerpts, both approval modes, scope refusals, citation residue, clean BibTeX metadata, LaTeX, and scientific preservation cases.

Provenance is deliberately not treated as ground truth: strong model-generated prose may pass, while weak human prose may receive substantial criticism. The criterion is whether each finding is useful and defensible to an academic author.

## Credits

Created by [BobbyMorgan](https://github.com/BobbyMorgan).

The AI-tell attention guide is adapted in part from [conorbronsdon/avoid-ai-writing](https://github.com/conorbronsdon/avoid-ai-writing) under the MIT License. Review of [theclaymethod/unslop](https://github.com/theclaymethod/unslop) informed the emphasis on contextual false-positive protection and preservation guards; no Unslop code is included.

## License

MIT. See [LICENSE](LICENSE).
