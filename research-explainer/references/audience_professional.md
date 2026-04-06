# Professional Practitioner Audience Guide

**Pacing: one image per message, then stop and wait.** Deliver each section's text with its image, then pause for the reader to absorb and respond before continuing.

This person is a licensed or credentialed professional whose daily work involves reviewing complex material where missing something has real consequences: lawyers doing contract review or due diligence, accountants auditing financial statements, actuaries modeling risk, underwriters evaluating applications, compliance officers reviewing regulatory filings, patent examiners assessing prior art, medical professionals reviewing patient histories, or any practitioner where thoroughness is the job.

**What distinguishes them from the "business" audience:** they aren't making tool-purchasing decisions or thinking about team composition at an org level. They are *the person doing the analysis.* They care about whether this makes their own work more thorough, defensible, and efficient. They live with the professional liability of missing things.

Your job: show them that the research formalizes something they already know from practice — that different ways of looking find different things — and gives them a framework for reasoning about when their current approach leaves systematic gaps.

## Key principle: respect their existing methodology

These professionals already have structured approaches to thoroughness. Lawyers have checklists. Actuaries have models. Underwriters have frameworks. Don't position the research as "here's a better way." Position it as "here's why your instinct to cross-check using multiple approaches is mathematically correct, here's where the gaps are largest, and here's a framework for thinking about which additional approaches would add the most coverage."

## What to emphasize

### Their work IS the paper's core problem

The paper's central question — "when you're searching through something big and complex, how do you know you haven't missed something important?" — isn't a metaphor for these professionals. It's literally their job description. A lawyer reviewing a contract is searching for obligations, risks, and ambiguities. An actuary modeling risk is searching for factors that change the outcome. An underwriter evaluating an application is searching for red flags the standard checklist might miss.

→ **Show `E4.png`** (Code Is the Easy Case) here. The side-by-side comparison — clean typed code on the left, tangled business documents on the right — makes the argument instantly: their domain is *harder* than the domain where this was tested.

The paper's results on code are a lower bound on how much diverse approaches matter for their work.

### The "two approaches" finding, in their terms

→ **Show `E6.png`** (Your Domain's Two Approaches) here. It replaces the bullet list below with a visual grid showing each profession's two complementary analysis methods side by side — lawyers, accountants, actuaries, underwriters, patent examiners, compliance officers.

Point to whichever cell matches their profession. Each one has a text-based approach and a structural approach — and each systematically misses what the other finds.

The paper quantified this: on large systems, each approach found 21-26% of important things the other completely missed. Ask them: in their domain, what's the cost of missing a quarter of the relevant findings?

→ **Show `exclusive_discovery_rates_by_codebase_size.jpg`** — the scaling effect. As the system under review gets larger and more complex, each approach's exclusive contribution grows.

### The task taxonomy maps to their daily work

The paper's five-class taxonomy based on search difficulty × verification difficulty is immediately useful for professionals. Walk them through it with examples from their domain:

- **Easy search, easy verify (Class I)**: Standard clause identification, routine journal entries, straightforward application data. Current tools are fine. Don't over-invest here.
- **Easy search, hard verify (Class II)**: You can find the relevant items, but judging whether they're problems requires expertise. Unusual contract language that's easy to locate but hard to assess. Financial entries that flag easily but require contextual judgment.
- **Hard search, easy verify (Class III)**: The finding is easy to evaluate once you see it, but you might never look in the right place. Hidden cross-references in contracts. Buried dependencies between regulatory requirements. This is where diverse search approaches pay off most.
- **Hard search, hard verify (Class IV-V)**: Can't easily find it AND can't easily judge it once found. Novel risk combinations. Emerging regulatory interpretations. Cascading contractual obligations. This is where you need both diverse tools AND experienced human judgment — and where the research says the cost of working with a single approach is highest.

Ask them to categorize their most critical review tasks on this grid. It's an immediately useful exercise that changes how they think about allocating review time.

→ **Show `task_taxonomy_search_vs_verification.jpg`**

### The experienced-practitioner finding validates their expertise

Section 7.4 of the paper provides rigorous evidence for something every senior professional knows intuitively: **experienced practitioners find things that juniors and AI miss, and the reason is specific — they search differently.** Years of domain expertise create mental models that cause them to look in places nobody else would think to look. Their search strategy is fundamentally decorrelated from how a junior reviewer or an AI tool would approach the same material.

The math is precise: one experienced practitioner adds more coverage to a review team than several juniors, because the juniors converge on similar surface-level strategies while the experienced practitioner's approach is uniquely their own.

This has direct implications for how they think about AI in their practice: **AI doesn't replace the experienced practitioner — it replaces the commodity search work, which makes the experienced practitioner's unique perspective MORE valuable, not less.** The AI handles what any competent reviewer would find. The experienced practitioner catches what only someone with their specific mental models would think to look for.

→ **Show `E14.png`** (Why Experienced Humans Break the Pattern)

### The "vibe coding regression" has an exact parallel in their work

If they've started using AI for drafting or review, they've probably noticed the same pattern the paper documents in code: AI works great on routine, well-structured tasks, then starts making subtle mistakes on complex, domain-specific material. The paper calls this the "vibe coding regression" and explains why:

- Simple, routine work follows patterns well-represented in the AI's training data
- As the material gets more specialized and context-dependent, the AI's training data becomes less representative
- The AI's reliability degrades precisely when the stakes are highest

For a lawyer: AI drafts a clean standard NDA but misses the interaction between a custom indemnification clause and a limitation of liability three pages away. For an actuary: AI handles standard mortality tables but fails to account for how a regulatory change interacts with a specific portfolio's correlation structure.

This connects back to the core finding: AI needs supplementary approaches exactly when the material gets hard.

→ **Show `E13.png`** (The Honeymoon Cliff)

### Encoding expertise into AI-readable methodology

There's a growing practice of encoding professional methodology into reusable AI skill files — structured instructions that give AI tools the practitioner's framework for approaching a specific type of review. The research explains why this is so effective: **the skill captures *part* of the experienced practitioner's decorrelated search strategy — some of the specific places they'd look and patterns they'd flag that a generic AI approach would miss.**

The key word is *part*. A skill is a snapshot of some of what the practitioner currently knows, not a complete extraction. Their expertise is a moving target — every unusual case they handle, every new pattern they recognize, every hard-won lesson builds new search strategies that didn't exist when they wrote the last skill. Six months from now they'll have insights worth encoding into new or updated skills. This means skill-building is an ongoing professional practice, not a one-time knowledge dump. And **the practitioner remains more valuable than any skill they write**, because they're the source of the next one.

For professionals, this has a concrete implication: if they encode their current review methodology (not just a checklist, but the *reasoning behind where they look and what they flag*), they're building an AI tool that genuinely complements the generic AI rather than duplicating it. The research shows this combination — diverse encoded methodologies plus generic AI search — produces measurably better coverage than either alone. And as their expertise evolves, their skills evolve with it.

### The four-stage methodology (if they're interested in building)

If they want to apply this to their own domain, the four stages translate directly:

1. **What data exists in your domain that you KNOW contains relevant information but your current tools don't use?** (Cross-reference structures in contracts. Citation networks in patent databases. Relationship graphs between regulatory requirements. Transaction flow patterns across accounts.)
2. **Can you test whether an AI can use it?** Give the AI the raw data and a specific question. Does it find things your current tools miss?
3. **Do you need to precompute structure?** The raw data may need reshaping — extracting clause relationships, building citation graphs, mapping transaction flows.
4. **How do you measure improvement?** Track what the new approach finds that the old approach missed (exclusive discoveries). This is how you justify the investment.

→ **Show `four_stage_methodology.jpg`** and potentially **`four_stage_methodology_across_domains.jpg`** — the cross-domain figure shows how the methodology maps to law, medicine, and finance specifically.

## What NOT to do with professionals

- Don't assume they're skeptical of AI — many are already using it extensively. They want to use it *better*.
- Don't be dismissive of their existing methodology — it's how they manage professional liability. The research complements it, not replaces it.
- Don't lead with code examples — translate everything to their domain immediately. The code is the test case; the principle is general.
- Don't oversimplify the math — these are quantitative professionals. They can handle "decorrelated search distributions" if you explain it clearly. Don't dumb it down unnecessarily.
- Don't ignore the liability dimension — for many professionals, "missed something" isn't just a quality issue, it's a malpractice or regulatory risk. Acknowledge the stakes.
- Don't position this as "AI will review for you" — position it as "AI plus your methodology, running in parallel, catches more than either alone."
- Don't skip the task taxonomy — it's the most immediately actionable framework for this audience. They can literally categorize their review tasks tomorrow.

## How to wrap up

Ask them to pick one of their most critical review tasks and categorize it on the search × verification grid. Then ask: what structured data exists in their domain that their current AI tools don't use? That's where the four-stage methodology starts.

If they're interested in going deeper, mention:
- The full paper is available and includes cross-domain applications in law, medicine, and finance
- The blog posts in `blog/` are written for a broader audience
- Denson is actively looking for practitioners in exactly their domain to validate whether the framework maps to their work — their feedback would be genuinely valuable
