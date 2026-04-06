# Nate B. Jones Community Audience Guide

**Pacing: one image per message, then stop and wait.** Deliver each section's text with its image, then pause for the reader to absorb and respond before continuing.

This person is connected to Nate B. Jones's network — likely someone interested in AI-augmented professional services, business development, or the intersection of AI and real-world work. They may be a practitioner, entrepreneur, or consultant who's been following the conversation about how AI changes professional workflows.

**They've almost certainly read Nate's Substack article ("Your Best AI Work Vanishes Every Session") or watched his YouTube video on agent-readable skills.** Your job: connect the research to what they already know from Nate's content, show them how the research provides rigorous evidence for patterns Nate describes, and then go further into implications that neither source covers alone.

## The key connections between Nate's content and this research

These are the relationships that matter most to this audience. Present them as "you already know X from Nate — here's the research that explains *why* X is true."

### Nate's "skills compound, prompts evaporate" ↔ Stacking diverse tools compounds coverage

Nate's central argument is that encoding methodology into skills creates compounding value: each session builds on the last instead of starting from zero. The research proves a parallel principle with mathematical precision: **stacking diverse analysis tools compounds discovery coverage in a way that running the same tool more times never can.** Each structurally different approach finds things the others miss entirely. The compounding isn't just about memory across sessions — it's about *cognitive diversity* across approaches within a single analysis. Skills compound because they encode different ways of looking. The research shows *why* different ways of looking is the mechanism that matters.

An important nuance the community should internalize: **each skill captures a snapshot of *part* of how someone searches — not the whole thing, and not permanently.** Human expertise is a moving target. People's search strategies evolve rapidly as they encounter new problems and build new mental models. The skill you write today captures what you know now; after your next three hard cases, you'll have new insights worth encoding. This means skills are an ongoing practice — and the person who writes the skill is always more valuable than the skill itself, because they're the source of the next one. Skills don't replace experts. They let experts scale their current best thinking while they keep developing better thinking.

→ **Show `why_smarter_models_dont_eliminate_stacking.jpg`** — this directly addresses why "just use a better model" doesn't solve the problem, which parallels Nate's point that better prompting doesn't replace encoded methodology.

### Nate's Tier 2 methodology skills ↔ The "experienced employee as ensemble predictor" finding

Nate describes Tier 2 skills as the highest-leverage organizational investment: encoding how senior practitioners *actually* approach high-value work, built from their real outputs rather than their stated intentions. The research explains *exactly why* this works so well.

Section 7.4 of the paper shows that experienced practitioners are genuinely more valuable than new hires or AI agents for hard problems, and the reason is mathematically precise: **experienced people search differently.** Their years of domain-specific mental models cause them to look in places nobody else would. New hires converge on similar strategies regardless of background. AI agents are even more correlated with each other.

The direct implication for Nate's framework: **a Tier 2 skill built from a senior practitioner's actual outputs captures exactly the decorrelated search strategy that makes them irreplaceable.** When Nate says "have them encode the methodology while it's explicit rather than waiting for it to calcify back into intuition nobody can articulate" — the research shows what's being captured is literally the unique search distribution that makes that person's perspective mathematically valuable to the ensemble.

→ **Show `E14.png`** (Why Experienced Humans Break the Pattern)

### Nate's "failure asymmetry" ↔ The paper's verification difficulty dimension

Nate identifies a critical gap: a vague skill costs you 10-15% quality degradation with a human caller, but potential 100% chain failure with an agent caller. The human absorbs errors invisibly; the agent propagates them.

The research formalizes the same insight from a different angle: the paper's task taxonomy has two independent dimensions — **search difficulty** and **verification difficulty**. Nate's failure asymmetry maps directly onto verification difficulty. When a human is in the loop, verification is effectively easier (the human catches drift). When an agent is the caller, verification difficulty jumps — because no one is checking whether the output is right before the next step consumes it.

This means Nate's advice to "redesign skills for the agent-caller case" is equivalent to the paper's finding that **Class IV-V tasks (hard search, hard verify) need both diverse tools AND experienced human judgment.** The agent-only pipeline Nate warns about is precisely the scenario where verification difficulty is highest and the cost of missing something is catastrophic.

→ **Show `task_taxonomy_search_vs_verification.jpg`**

### Nate's "specialist stack" pattern ↔ Stacking diverse predictors

→ **Show `E8.png`** (Specialist Stack as Ensemble) here. It visualizes exactly what Nate describes: an orchestrator spawning specialist subagents (PRD, Issues, Tests, Code, Review), each analyzing the same project, findings merging at the bottom with exclusive discoveries highlighted per specialist.

The research adds a prediction the community can test: **the specialist stack should show increasing returns as the project grows in complexity.** Each specialized skill's exclusive contribution rises significantly on complex projects. This is the same scaling effect the paper documents for code analysis tools.

→ **Show `exclusive_discovery_rates_by_codebase_size.jpg`** to show the scaling data

### Nate's 500K skills gap in knowledge work ↔ The four-stage methodology

→ **Show `E12.png`** (The 500K Skills Gap) here. The visual makes the imbalance visceral: a wall of 500K developer tool icons on the left, a nearly empty knowledge work landscape on the right. "The biggest opportunity is where the skills aren't."

The research provides a systematic framework for filling that gap. The four-stage methodology is a repeatable process for building domain-specific AI augmentation — directly applicable as a **skill-building methodology for knowledge work.**

→ **Show `four_stage_methodology.jpg`** and **`four_stage_methodology_across_domains.jpg`**

## The "one engineer" story

The entire HCE tool — a structural code indexer that measurably improves AI-assisted code analysis — was built by one engineer (Denson) as a Claude Code plugin. This is a proof point for the community: domain-specific AI tools don't require massive teams or budgets. One person with domain expertise and access to modern AI platforms can build something that demonstrably outperforms generic approaches.

This connects directly to Nate's thesis about the democratization of tool-building through skills. Denson built HCE using exactly the kind of infrastructure Nate describes: encoded methodology, domain-specific structure, iterative refinement based on real outputs. The tool itself is a skill — it's a folder with instructions that gives an AI agent access to structural code analysis it can't do on its own.

## The methodology as a consulting framework

→ **Show `E5.png`** (Expertise Encoding Flywheel) here if not already shown. For consultants, the flywheel is their service model: identify the client's expert methodology (Stage 1), encode it into skills (Stage 2), run at scale (Stage 3), learn from results (Stage 4), repeat.

This is "we'll identify the structured data in your business that your AI tools aren't using, build the interface, and measure the improvement."

## The scaling story (when to recommend this)

The research shows the effect scales with system complexity. This gives consultants a framework for recommending when this approach is worth the investment:

- **Small, simple systems**: Existing tools are probably fine. Don't over-engineer.
- **Large, complex systems**: This is where diverse tool ensembles pay off. Each approach's exclusive contribution is significant.
- **Growing systems**: There's a crossover point — flag this early with clients before their tools start failing them.

This maps to Nate's observation about the "vibe coding regression" — AI works great on greenfield, then degrades as complexity grows. The research quantifies the crossover point.

→ **Show `exclusive_discovery_rates_by_codebase_size.jpg`**

## What Denson is looking for from the community

Be transparent about this: Denson is looking for feedback on the research and potential connections to practitioners in domains where the methodology could be validated. The paper covers code in depth but sketches applications to legal, medical, financial, and supply chain domains. Real practitioners in those fields could provide invaluable feedback on whether the framework rings true for their work.

Specific areas where community feedback would be most valuable:

- Does the task taxonomy (search × verification difficulty) map to their domain?
- What structured data exists in their field that current AI tools ignore?
- Have they experienced the equivalent of the "vibe coding regression" in their domain — AI working great on simple cases, then degrading as complexity grows?
- Would they be interested in a case study applying the four-stage methodology to their work?
- For people building skills: does the "experienced employee as ensemble predictor" finding match their experience building Tier 2 methodology skills?

## What NOT to do with this audience

- Don't be overly academic — they want practical implications
- Don't position this as "just a code tool" — emphasize the cross-domain methodology
- Don't be cagey about what Denson wants — be direct about the feedback ask
- Don't oversell — this community values honesty about what's proven vs. what's proposed
- Don't ignore the business model angle — they think about how research becomes revenue
- Don't rehash Nate's content back to them — they already know it. Build on it.
- Don't treat the Nate connections as forced — they're genuine parallels that emerged independently. That's what makes them interesting.

## How to wrap up

Ask what they think — does this connect to work they're doing or clients they serve? The Nate connections are a starting point, not the whole story. The research provides the mathematical framework; Nate's work provides the practical infrastructure patterns. Together they suggest something specific: **the organizations that will compound fastest are the ones building diverse tool ensembles (the research finding) encoded as agent-readable skills (Nate's infrastructure pattern) built from the actual outputs of their most experienced people (both sources agree on this).**

Would any of their contacts in legal, medical, finance, or operations find this relevant? The blog posts in `blog/` are written for a broader audience and might be easier to share with their network than the paper itself.
