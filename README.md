# Turing-Pass Scholar

[English](README.md) | [简体中文](README.zh-CN.md)

Academic de-AI editing for **English original research papers and review articles**, packaged as one portable Agent Skill for Claude Code and Codex.

Turing-Pass Scholar reads as an academically literate, independent editor. Its job is not to guess who or what wrote a manuscript. It asks a more useful question: would a scholarly reader experience this prose as formulaic, generic, poorly judged, suspiciously AI-like, or simply weak?

**Current release: v1.0.0**

## What it does

- Diagnoses AI-like writing at the scale where the problem actually lives: phrase, sentence, paragraph, section, or rhetorical architecture.
- Preserves numbers, units, statistics, equations, technical terms, negation, uncertainty, causal strength, citations, cross-references, and authorial stance.
- Uses separate paths for original research papers and review articles. Research writing receives higher tolerance for first person, technical repetition, functional enumeration, dense Results prose, and figure/section references. Reviews receive closer scrutiny of empty synthesis, generic taxonomies, paper-by-paper listing, false consensus, and unsupported comprehensiveness.
- Supports complete manuscripts, individual sections, and short excerpts. It never implies that missing sections were reviewed.
- Optionally flags material claim drift, ambiguity, terminology conflict, or section-function problems noticed during the de-AI read without expanding into peer review.
- Audits citations and reference entries for AI/draft residue such as prompts, private notes, placeholders, malformed DOI/URL placeholders, or accidental full-width Chinese punctuation. It does not enforce APA, Vancouver, or another named style.
- Protects LaTeX commands, labels, citation keys, mathematics, BibTeX structure, and legitimate reference-manager metadata.

## Two working modes

The skill establishes one mode before editing:

1. **Whole supplied scope** — diagnose and revise everything the user supplied, then return the complete edited text and a preservation note.
2. **Paragraph approval** — return the assessment first, stop, and revise affected paragraphs only after the user approves them.

If the genre or mode is missing, the skill asks once for all missing choices. Letters, short communications, correspondence, editorials, perspectives, commentaries, case reports, protocols, theses, dissertations, grants, coursework, peer-review reports, and non-academic writing are hard out of scope.

## Why it is different

Most humanizers optimize for generic naturalness or a personal voice. Turing-Pass Scholar keeps the register academic and treats technical precision as load-bearing. Pattern matches are attention cues, not verdicts. A finding must identify a reader-visible defect worth revising even if AI provenance is never mentioned; otherwise it stays out of the report.

The report is findings-only. It does not list checks that passed, explain why normal conventions are acceptable, generate an AI probability, or populate empty sections. A clean excerpt receives a brief pass and nothing else.

## Install

See [INSTALL.md](INSTALL.md) for Windows, macOS, Linux, personal, and project-scoped installation.
The paths and invocation forms follow the current [Claude Code Skills documentation](https://code.claude.com/docs/en/skills) and [OpenAI Skills documentation](https://developers.openai.com/codex/skills).

Quick paths:

| Host | Personal skill location | Explicit invocation |
| --- | --- | --- |
| Claude Code | `~/.claude/skills/academic-deslop/` | `/academic-deslop` |
| Codex | `$HOME/.agents/skills/academic-deslop/` | `$academic-deslop` |

The same `academic-deslop` folder works in both hosts. No scripts, Python packages, network access, external detector, or API key are required.

## Use

```text
这是 original research paper 的 Discussion 片段。选择 B，只出报告，不要改写。
```

```text
This is a review article. Use whole-supplied-scope mode, preserve every citation, and return the complete de-AI revision.
```

```text
这是 research paper 的 LaTeX 稿。选择 A；顺带检查 BibTeX 条目里有没有提示词、私人备注或中文全角标点。
```

## Scope and non-goals

Turing-Pass Scholar supports only English original research papers and review articles. It does not perform AI-authorship detection, translation, external fact checking, strict reference-style compliance, plagiarism review, methodology/statistics/ethics review, reporting-guideline review, journal selection, or invention of missing scholarship.

Tables are audit-only: values and cells are not rewritten. Broader academic-editorial observations remain recommendations unless the user separately authorizes substantive editing.

## Validation

v1.0.0 was behaviorally tested in isolated Codex sessions with de-identified excerpts spanning:

- pre-generative-AI, openly licensed original research and review prose;
- model-generated research and review prose written without deliberately planted errors;
- complete-pass, paragraph-approval, excerpt, scope-refusal, and missing-mode interactions;
- citation residue, clean BibTeX library metadata, LaTeX preservation, numbers, units, statistics, negation, uncertainty, figure references, and citation keys.

The evaluation is qualitative by design. Provenance is not treated as ground truth: good model-generated prose may pass, and human-authored prose may still receive a strong editorial criticism. The acceptance criterion is whether the finding is useful and defensible to an academic author.

## Credits

Created by [BobbyMorgan](https://github.com/BobbyMorgan).

The AI-tell attention guide is adapted in part from [conorbronsdon/avoid-ai-writing](https://github.com/conorbronsdon/avoid-ai-writing) under the MIT License. Review of [theclaymethod/unslop](https://github.com/theclaymethod/unslop) informed the emphasis on contextual false-positive protection and preservation guards; no Unslop code is included.

## License

MIT. See [LICENSE](LICENSE).
