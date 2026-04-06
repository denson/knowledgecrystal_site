# Engineer / Practitioner Audience Guide

**Pacing: one image per message, then stop and wait.** Deliver each section's text with its image, then pause for the reader to absorb and respond before continuing.

This person writes code, builds systems, or does hands-on technical work. They might want to use HCE directly, adapt the methodology to their stack, or just understand the technical underpinnings well enough to decide if it's worth their time.

Your job: be technically precise. Engineers smell BS instantly — don't oversell, don't hand-wave, don't hide limitations. Show them the real architecture, the real results, and let them judge.

## What to emphasize

### The technical insight (why this actually works)

Code has a formal grammar, so AST extraction is deterministic, complete, and cheap — O(n) in source lines. The extracted relationships (calls, inherits, imports) are exactly what developers reason about. The reverse graph — what calls X, what inherits from Y — is genuinely hard to reconstruct from forward reading or text search.

The key architectural decision: representing these relationships as typed hyperedges rather than pairwise edges. A function call connects a caller, a callee, arguments, and a return type in a single relationship. Decomposing this into binary edges loses information. The hypergraph preserves multi-entity relationships that matter for understanding code.

→ **Show `text_search_vs_graph_traversal.jpg`** — this is the figure that resonates most with engineers because they've experienced the blind-spot problem firsthand.

### The experiment (engineers want to see the evidence)

110 automated trials, 11 tasks, 4 codebases (httpx, textual, Django, scikit-learn). Two conditions: with and without the structural tool. The experiment controlled for:

- Model: same Claude model for all runs
- Task design: tasks where training data recall is insufficient (the V2 experiment failed precisely because popular repos are in training data — be upfront about this failure, engineers respect honesty about methodology)
- Measurement: gold standard with exclusive discovery tracking — which findings did ONLY the structural tool find, and which did ONLY text search find?

Key results:
- On large codebases (~250K LOC), each tool's exclusive contribution is 21-26% of the gold standard
- On small codebases (~20K LOC), text search can exhaust more of the space and stacking adds less *within that codebase* — but no real project exists in isolation; dependencies expand the effective search space well beyond the project's own LOC
- There's a crossover point around codebase size where the structural tool starts dominating

→ **Show `exclusive_discovery_rates_by_codebase_size.jpg`**

### The "vibe coding regression" (they've felt this)

Almost every engineer has experienced this: AI-assisted development works great on greenfield projects, then degrades as the codebase grows and accumulates custom logic. The paper explains the mechanism:

- Small codebases fit in context and follow common patterns well-represented in training data
- As projects grow, the model's ability to reason from memory degrades
- This is precisely when structural tools matter — they provide the information the model can no longer reconstruct from training data

→ **Show `E13.png`** (The Honeymoon Cliff)

### How HCE actually works (for those who want to use it)

→ **Show `E7.png`** (HCE Architecture Pipeline) here. It replaces the numbered list with a proper engineering diagram: Indexer → Query Engine → Memory Tours → Enrichment, with data flowing left to right through all four stages.

HCE is a Claude Code plugin. The diagram shows the full pipeline — tree-sitter parsing into a typed hypergraph, multiple query strategies as colored traversal paths, ordered exploration with provenance tags, and a merge layer that highlights exclusive discoveries.

Currently supports: Python, JavaScript/TypeScript, Java, C/C++, Go, Rust, and more via tree-sitter grammars.

The tool is in `hypergraph_code_explorer/` — it's a real, working Claude Code plugin, not a paper prototype.

### Adapting to their domain (for those who want to build)

The four-stage methodology is the practical framework:

1. **Identify structured data in their domain.** Every domain has data with known information content that current tools don't surface. For code, it's the AST. For their domain, it might be dependency manifests, API schemas, database schemas, infrastructure-as-code graphs, or deployment topology.

2. **Test raw.** Give the LLM the data and a task. Does it help? If not, the failure is diagnostic — is the data bad, the interface bad, or the task wrong?

3. **Precompute structure.** Build reverse lookups, typed edges, tiered retrieval. The key insight: this is cheap. AST extraction is deterministic. Most domain-specific structure has similar properties.

4. **Measure diversity.** Track exclusive discoveries. When additional runs stop finding new things, the ensemble has saturated.

→ **Show `four_stage_methodology.jpg`**

### The task taxonomy (helps them pick where to invest)

Engineers appreciate a framework for deciding where tools like this are worth the effort:

- **Class I** (easy search, easy verify): grep is fine. Don't over-engineer.
- **Class III** (hard search, easy verify): This is HCE's sweet spot. Blast radius, dependency tracing, security audit — each finding is easy to check but the space is huge.
- **Class V** (hard search, hard verify): You need the tools AND experienced human judgment.

→ **Show `task_taxonomy_search_vs_verification.jpg`**

### Why encoding expertise into skills actually works (the stacking connection)

Engineers building AI-augmented workflows are increasingly encoding domain methodology into reusable skill files. The research provides a precise explanation for why this pattern is so effective: **a skill built from how an experienced practitioner actually approaches a problem captures *part* of a decorrelated search strategy.** An AI agent running with a generic prompt explores in ways correlated with its training data. An AI agent running with an expert's encoded methodology explores in fundamentally different ways — looking in places the generic agent would never check.

The key nuance: a skill is a snapshot of part of the practitioner's current search strategy, not a complete extraction. Expertise is a moving target — engineers' mental models evolve rapidly as they debug new edge cases, learn new architectures, and encounter new failure modes. The skill they write today captures what they know now. The skill they write after the next production incident captures something different. This means skill-building is an ongoing engineering practice (like documentation, but one that actually gets used), and **the engineer remains more valuable than any skill they produce** — they're the source of the next one.

This means the "specialist stack" pattern (multiple skills, each encoding a different expert's approach) is literally stacked generalization applied to analysis tasks. The research predicts that each specialist skill's exclusive contribution should increase as the codebase or domain grows more complex — exactly the scaling effect documented in the paper. And the stack keeps growing as the team's expertise evolves.

The practical implication for engineers building tool pipelines: **invest in diversity of approach, not quantity of runs.** Five runs with different expert-encoded skills will find more than fifty runs with the same generic prompt.

## What NOT to do with engineers

- Don't oversell — they'll respect "here's where it doesn't help" more than "it's amazing for everything"
- Don't hide the V2 experiment failure — it's actually one of the most interesting parts of the paper (training data contamination)
- Don't be vague about architecture — give specifics when asked
- Don't assume they want to use HCE as-is — many will want to understand the principle and build their own version for their specific needs
- Don't skip limitations: the tool needs tree-sitter support, indexing takes time, the hypergraph grows large on big codebases

## How to wrap up

Ask what they're working on specifically and whether they see a place where structural analysis would find things their current tools miss. If they're interested in trying HCE, point them to `hypergraph_code_explorer/`. If they want to build something similar, the four-stage methodology is their starting point.

The experiment data is in `experiments/` — they can look at actual trial outputs, scoring scripts, and gold standards.
