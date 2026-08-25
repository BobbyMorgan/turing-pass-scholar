# Original research paper path

Infer section function rather than enforcing IMRaD labels. Disciplinary and target-journal conventions
override generic style preferences.

## Higher tolerance for research conventions

- Preserve existing first person in any section (`we show`, `we tested`, `we next examined`,
  `we interpret`). Do not add it where absent, but do not confine it to Methods.
- Preserve functional section/equation/figure/table cross-references, proof roadmaps, and paper
  organization. Flag only empty table-of-contents narration.
- Preserve factual counts of experiments, cohorts, stages, criteria, models, datasets, hypotheses,
  analyses, or proof cases. Only rhetorical counting is an AI-style concern.
- Preserve functional enumeration of distinct assumptions, reasons, properties, cases, or contributions,
  including `First`/`Second`, when each item carries substantive content. A numbered rationale is not
  rhetorical scaffolding merely because prose could be arranged another way.
- Prefer repeated precise terminology over synonym cycling.
- Passive voice, colons, semicolons, signposts, and parallel Results paragraphs are judged in context,
  not treated as violations by themselves.
- Treat repeated author-action/result verbs (`we found`, `we observed`, `we reasoned`, `we tested`) as
  neutral when they identify distinct moves or findings. Do not infer templating from recurrence alone.
- Treat repeated technical terms, including ordinary words used technically, as neutral unless an
  occurrence is vague, internally inconsistent, or performs empty evaluation instead of technical work.
- Treat application or implication sentences as neutral when a concrete result supports them and their
  modality is calibrated. Flag a specific evidential leap, not the fact that the sentence states value.
- Dense sentences are normal when conditions, contrasts, numbers, and interpretation must remain
  connected. Flag density only when syntax makes a referent, attachment, comparison, or scope genuinely
  hard to recover; do not diagnose a sentence as assembled, processed, or overengineered from length.
- Observation and interpretation may share a sentence or paragraph. Flag them only when the boundary is
  unclear enough to misstate evidence or when modality turns interpretation into an observed result.
- Do not call an implication promotional merely because it states usefulness or likely application.
  Identify the particular unsupported jump in scope, certainty, causality, or generality, or pass it.
- Respect discipline-standard figurative verbs for systems, models, algorithms, organisms, and
  mechanisms (`learn`, `encode`, `decode`, `map`, `focus`, `recognize`, and equivalents). Do not call
  them anthropomorphic unless the wording assigns consequential human intention or agency.
- Related metric names, variants, or abbreviations are not an inconsistency merely because they look
  similar. Flag only when the passage treats them as the same quantity, contradicts its own definition,
  or supplies other evidence of a genuine token conflict.
- Introduction paragraphs may establish field context, define a bottleneck, explain a methodological
  choice, and preview the study or datasets. Do not call this multi-job, textbook-like, or overpacked
  unless a specific relation is unreadable or the background remains interchangeable with another topic
  after its technical nouns are removed.

## Section attention

- **Title/Abstract:** compare scope, design, population/system, results, numbers, direction, and conclusion
  with the body. Flag abstract-only findings and stronger abstract conclusions.
- **Introduction:** check alignment among problem, gap, objective/hypothesis, and the work reported.
  Flag generic panoramas, manufactured novelty, false consensus, and citations used as scenery.
- **Methods:** protect chronology, repetition, conditions, parameters, exclusions, software versions,
  decision rules, and operational detail needed for reproducibility. Do not shorten away who did what,
  when, to which material/group, or under which criterion.
- **Results:** preserve observation versus interpretation. Check direction, magnitude, uncertainty,
  labels, time points, and figure/table references. Flag mechanism or importance language not supported
  by the reported observation.
- **Discussion/Conclusion:** distinguish finding, interpretation, comparison, limitation, implication,
  and speculation. Flag causal/generalization/novelty inflation, repetitive summary, and conclusions not
  traceable to the objectives and results. Do not invent limitations or future directions.
- **Theoretical/mathematical/CS work:** definitions, assumptions, quantifiers, boundary conditions,
  proof dependencies, notation, algorithms, complexity claims, benchmarks, and cross-references are
  load-bearing. Precision outranks stylistic variety.

Do not review experimental design, statistical appropriateness, ethics, or reporting completeness unless
the user separately requests a different task.
