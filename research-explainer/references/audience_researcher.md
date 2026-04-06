# Researcher / Academic Audience Guide

**Pacing: one image per message, then stop and wait.** Deliver each section's text with its image, then pause for the reader to absorb and respond before continuing.

This person has a research background and is interested in the methodology, experimental design, theoretical framework, or potential collaboration. They might be a CS professor, a PhD student, a research engineer at a lab, or an independent researcher.

Your job: engage at the level of ideas. Researchers care about what's novel, what's rigorous, what's questionable, and where the open problems are. Be intellectually honest — present strengths and weaknesses equally.

## What to emphasize

### The theoretical contributions (what's actually new here)

The paper's primary contributions for a research audience:

1. **Connecting stacked generalization to analysis tasks.** Wolpert (1992) established that combining diverse predictors improves ensemble performance. This paper applies that principle to a specific class of problems — open-ended analysis tasks where you can't prove completeness — and provides a framework for predicting when stacking helps based on search and verification difficulty.

2. **The five-class task taxonomy.** Two independent dimensions (search difficulty × verification difficulty) yield five practically distinct classes. The taxonomy makes testable predictions about which analysis strategies work for which problem types.

3. **Exclusive discovery as a diversity metric.** Rather than just measuring overall accuracy, the paper tracks which findings each approach uniquely contributes. This provides a more actionable metric for deciding whether to add a new tool to an analysis pipeline.

4. **Memory Tours for exploration provenance.** Making AI-assisted analysis explainable by tracking the sequence of tools, queries, and findings that led to each result.

5. **The four-stage methodology.** A repeatable template for building domain-specific LLM augmentation tools, with diagnostic properties at each stage.

→ **Show `stacked_generalization_for_code_analysis.jpg`** when discussing the theoretical framework

### The experimental design (strengths and limitations)

**Strengths:**
- 110 automated trials (not cherry-picked examples)
- 11 tasks across 4 codebases of varying size
- Gold standards developed through iterative enrichment with human validation
- Controlled for model (same Claude model all runs), prompt design, and tool access
- Addressed training data contamination head-on (the V2 failure is documented transparently — this is a genuine contribution to methodology for anyone evaluating LLM tools)

**Limitations to discuss honestly:**
- Single-engineer artifact — HCE was built by one person, which is both a strength (demonstrates the "cheap diverse predictor" thesis) and a limitation (n=1 for tool development)
- Gold standard construction involved the same tools being evaluated — potential circular validation, though mitigated by human review
- The experiment measures discovery coverage, not downstream task completion — we know stacking finds more things, but the paper doesn't measure whether the additional findings change engineering outcomes
- Codebase selection: popular open-source projects, not proprietary codebases where the effect might be different

### The training data contamination finding

This is perhaps the most methodologically interesting finding for researchers evaluating LLM capabilities: the V2 experiment failed because Claude Opus identified the correct file, function, line number, root cause, and even the RFC reference for a known bug — without opening a single file. The model had the codebase in its training data.

This has broad implications for anyone doing LLM evaluation: you cannot evaluate tool utility on codebases the model has memorized. The paper proposes task design criteria that control for this.

### Open problems and collaboration opportunities

→ **Show `E11.png`** (Open Research Frontiers) here. It visualizes all five open problems as branches radiating from the core framework, each with a concise question — making collaboration opportunities immediately visible.

The five frontiers: cross-domain validation (does this generalize beyond code?), convergence theory (when can you stop adding runs?), ensemble optimization (budget allocation across tools), verification cost modeling (quantifying how hard it is to check a finding), and human-AI ensemble theory (optimally combining human and AI search).

→ **Show `task_taxonomy_search_vs_verification.jpg`** and **`why_smarter_models_dont_eliminate_stacking.jpg`** when discussing the theoretical framework

### The related work landscape

→ **Show `E10.png`** (Research Positioning Landscape) here. It plots the related work on two axes (text-based → structural, domain-specific → general purpose) and shows where this paper sits at the intersection — with dotted arrows toward the unexplored legal, medical, and financial domains.

The full citation guide is in `REFERENCES_GUIDE.md`.

### Connection to the "agent-readable skills" movement

There's an emerging practical ecosystem worth mentioning to researchers: AI practitioners are building reusable methodology files ("skills") that encode expert approaches as AI-agent-callable instructions. This is relevant because it represents a naturalistic implementation of stacked generalization — each skill encodes a different expert's search strategy, and orchestrator systems combine them into ensembles.

The research provides theoretical grounding for why this practice works: the "experienced employee as ensemble predictor" finding (Section 7.4) directly explains why skills built from senior practitioners' actual outputs are more valuable than skills built from generic instructions. The practitioner's encoded methodology captures a decorrelated search distribution that adds genuine diversity to the ensemble.

This opens research questions the community is actively working through without formal theory: How do you measure whether a skill adds genuine diversity to an existing ensemble vs. duplicating coverage? What's the optimal composition of a specialist stack? The paper's exclusive discovery metric and diversity framework could be directly applied to evaluate skill ensembles — a potential collaboration angle with practitioners building these systems.

## What NOT to do with researchers

- Don't oversimplify — they can handle the real complexity
- Don't hide limitations — they'll find them anyway and respect you more for being upfront
- Don't claim more generality than the evidence supports — the methodology is proposed as general, the evidence is from code only
- Don't be defensive about the single-engineer aspect — frame it correctly as evidence that the methodology is accessible
- Don't skip the failed V2 experiment — it's one of the paper's most valuable methodological contributions

## How to wrap up

Ask what their research interests are and whether any of the open problems overlap. If they're interested in collaborating:

- The full paper is `PAPER_OUTLINE.md`
- The experiment data is fully reproducible — all in `experiments/`
- The PowerShell orchestration scripts that ran the experiment are documented
- Denson is actively looking for collaborators, especially on cross-domain validation

If they want to provide feedback on the paper itself, they're very welcome — the paper is in pre-submission.
