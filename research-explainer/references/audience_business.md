# Business / Decision-Maker Audience Guide

**Pacing: one image per message, then stop and wait.** Deliver each section's text with its image, then pause for the reader to absorb and respond before continuing.

This person makes or influences decisions about tools, processes, teams, or strategy. They could be a CTO, VP of Engineering, engineering manager, product manager, compliance officer, head of legal, head of security, or anyone who allocates resources and cares about outcomes.

Your job: show them how the research framework applies to decisions they're actually making. The paper has direct implications for tool investment, team composition, and process design. Speak in terms of ROI, risk, coverage, and cost — not algorithms and data structures.

## Key principle: adapt to their specific role

A CTO and a compliance officer care about completely different things. Pay close attention to what they told you about their role and daily work. The framework maps differently for each:

- **CTO / VP Engineering**: Tool investment decisions, build vs. buy, team productivity
- **Engineering Manager**: Team composition, when to hire senior vs. junior, how to structure code review
- **Product Manager**: Feature prioritization, technical debt assessment, risk estimation
- **Head of Security / Head of Compliance**: Audit coverage strategy, false negative cost at org level, regulatory exposure
- **Head of Legal / General Counsel**: Due diligence process design, review coverage strategy
- **Operations / Supply Chain**: Dependency tracing, failure mode analysis, vendor audit

Note: if this person is a *practicing* lawyer, accountant, actuary, underwriter, or compliance officer — doing the actual review work rather than managing teams — route them to `audience_professional.md` instead. The distinction is decision-maker vs. practitioner.

## Important framing: code is the EASY case

→ **Show `E4.png`** (Code Is the Easy Case) early in this section. It makes the argument visually: code on the left is clean, typed, compiler-verified; business documents on the right are a tangle of implicit dependencies, question marks, and cross-format chaos.

The research was tested on code, but **code is a relatively easy search problem compared to what most businesses face.** If the research found 21-26% exclusive discovery rates on code — a domain with enforced structure — the gaps in business document analysis are almost certainly larger. **The paper's code experiments are a lower bound on how much diverse approaches matter for their document-heavy problems.**

This framing should run through the entire conversation. It's a mathematical framework proven on the easy case (code) with even stronger implications for the hard case (their world).

## The diversity businesses already have — and the diversity they're missing

→ **Show `E9.png`** (Inter vs Intra-Department Diversity) here. It tells this entire story in one image: org-level diversity already exists across departments, but zoom into any single department and there's a gap.

Most businesses already have *inter-department* diversity. When a contract goes through legal, engineering, compliance, and finance, each department brings a different lens. What they typically *don't* have is sufficient diversity **within** departments. Three lawyers from the same firm are more correlated with each other than a lawyer and an engineer. Adding a structurally different analysis tool adds genuine diversity that more reviewers from the same discipline may not.

**Your cross-department review process is already doing the right thing at the organizational level. The question is whether each department has the tools to achieve the same diversity advantage within its own domain.**

## What to emphasize

### The cost of missing things (their language for "false negatives")

Every business person understands the cost of missing something important — a contractual obligation buried in an amendment, an engineering spec that contradicts a regulatory requirement, a compliance gap that spans three documents nobody read together. Frame the research around this: **when the cost of missing something is high, using a single analysis approach leaves systematic gaps.**

The paper quantifies this on code — a domain with enforced structure. On their documents, which lack that structure, the gaps are likely worse. Ask them what it would mean for their organization to miss a quarter of the relevant findings in their most critical document review tasks.

### The team composition insight

The experienced-employee finding has direct HR and org-design implications:

**One experienced person contributes more to finding important things than several new hires.** This isn't about seniority for its own sake — it's about cognitive diversity. Experienced people search differently based on mental models that are fundamentally uncorrelated with how others search. New hires converge on similar exploration strategies regardless of background.

The person who's been reading contracts in your industry for fifteen years doesn't just know more clauses — they *look in different places*. They know which cross-references tend to create hidden obligations, which amendment patterns tend to contradict the base agreement, which specification gaps tend to cause problems downstream. That search strategy is genuinely decorrelated from how a junior reviewer or an AI tool would approach the same stack of documents.

For managers making hiring decisions: this framework predicts when experience matters most (hard search problems on complex document sets) vs. when fresh perspectives help more (problems needing creative reframing).

→ **Show `E14.png`** (Why Experienced Humans Break the Pattern)

### The task taxonomy (help them categorize their problems)

The paper's 5-class taxonomy is directly useful for business people because it tells them where to invest:

- **Easy search, easy verify** (Class I): Standard clause identification, routine data extraction from structured forms. Existing tools handle this. Don't over-invest.
- **Easy search, hard verify** (Class II): You can find the relevant items, but judging whether they're problems requires expertise. A contract clause is easy to locate but hard to assess in context. You need experienced human review, not more search tools.
- **Hard search, easy verify** (Class III): Once you find it, you know what it means — but you might never look in the right place. A spec requirement that contradicts an amendment you didn't think to cross-reference. This is where diverse search approaches pay off most.
- **Hard search, hard verify** (Class IV-V): Can't easily find it AND can't easily judge it once found. Verifying that a set of engineering specifications together fulfil a contract with all amendments taken together. Assessing whether a regulatory change interacts with existing contractual obligations across multiple agreements. This is the hardest class, and it's where most high-stakes business document work actually lives. You need both diverse tools AND experienced human judgment.

Most business document review is Class III-V. Code, by contrast, has more Class I-II tasks because the structure is machine-enforced. Ask them to categorize their most important analysis tasks on this grid — it reframes how they think about allocating review resources.

→ **Show `task_taxonomy_search_vs_verification.jpg`**

### The four-stage methodology (if they're thinking about building)

If they're considering building domain-specific tools or augmenting their AI pipeline, walk them through the four stages in terms of their domain:

1. **What data do you have that you KNOW contains relevant information but your tools don't use?** (This question is electric — they almost always know the answer. Cross-reference structures between contracts and specs. Amendment histories. Dependency chains between regulatory requirements and internal policies.)
2. **Can you test whether an LLM can use it raw?** Quick, cheap validation before committing
3. **Do you need to precompute structure?** The implicit relationships between business documents almost certainly need to be made explicit — extracted, mapped, indexed — before AI tools can reason over them effectively. Code gets this for free from the parser. Documents don't.
4. **How do you measure whether the investment paid off?** Exclusive discovery tracking — what does the new approach find that the old approach missed?

→ **Show `four_stage_methodology.jpg`** and potentially `four_stage_methodology_across_domains.jpg`

### The scaling argument (for justifying investment)

The effect scales with problem complexity, and complexity is determined by the *nature of the problem* — not the size of the organization. A ten-person engineering firm verifying that their specs fulfil a complex government contract faces harder search problems than a Fortune 500 company doing routine data extraction.

The paper's task taxonomy tells you who needs this based on the *class of problem they're solving*:

- **Complex document interdependencies (any org size)**: Contracts with amendments, specs that must fulfil those contracts, regulatory requirements constraining both — this is Class IV-V territory regardless of how many employees you have. Diverse search approaches matter from the start.
- **Large document corpora**: The sheer volume means each approach's exclusive contribution is larger in absolute terms. More surface area for things to hide in.
- **Cross-format dependencies**: When the critical relationships span contracts, specs, regulations, emails, and technical documents in different formats, no single search approach can trace all the threads. This is where the "two fundamentally different ways of looking" principle has the strongest business case.

The unifying principle: **whenever the cost of missing something is high and the space of things you might need to find is larger than one approach can cover, diverse tools pay off.** That's a property of the problem, not the org chart.

→ **Show `exclusive_discovery_rates_by_codebase_size.jpg`** — note to the audience that these numbers are from code, where structure is enforced. On unstructured business documents, the exclusive discovery rates are likely higher.

### The expertise-encoding opportunity

→ **Show `E5.png`** (Expertise Encoding Flywheel) here. It replaces most of the explanation below with a visual cycle: expert does work → encodes methodology → AI runs it at scale → expert learns from new cases → repeat, compounding.

The research explains why encoding expert methodology into reusable AI skills is so effective: **a skill captures part of the decorrelated search strategy that makes a senior practitioner's perspective valuable.** Organizations investing in this aren't just saving time — they're building the cognitive diversity that drives analysis coverage.

Two things decision-makers need to hear, both visible in the flywheel:

First, **skills are an ongoing practice, not a one-time extraction.** The expert keeps learning (Stage 4 feeds back to Stage 1). The organization that treats skill-building as continuous will compound indefinitely.

Second, **the person who writes the skill remains more valuable than the skill itself.** They're the source of the next skill. Skills don't make experts replaceable — they make experts *scalable*.

## What NOT to do with business audiences

- Don't frame this as "a code tool with business applications" — frame it as a mathematical framework proven on the easy case (code) with even stronger implications for the hard case (their document-heavy world)
- Don't explain hypergraphs or ASTs — they don't need to know the implementation
- Don't lead with the experiment details — lead with the implication
- Don't assume they want to build anything — many just want to make better decisions about what to buy or how to structure their teams
- Don't use ML jargon like "predictor", "ensemble", "decorrelation" without immediately translating to business terms
- Don't present the methodology as a fixed prescription — frame it as a thinking tool
- Don't imply this only matters for large enterprises — the class of problem determines the need, not the org size

## How to wrap up

Connect back to a specific decision they mentioned. If they talked about hiring, discuss the team composition implications. If they talked about tooling, discuss the four-stage evaluation framework. If they talked about risk, discuss the taxonomy. If they talked about contract or spec review, drive home the point that their document analysis problems are *harder* than the code problems in the paper — which means the diverse-approach principle matters even more for them.

Offer the paper as a resource their team could use for making these decisions more rigorously.
