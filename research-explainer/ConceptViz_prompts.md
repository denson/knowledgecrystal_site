# ConceptViz Prompts for Research Explainer Images

Use "Thinking" mode. Paste one at a time. Colorblind-friendly: specify colors by name (green, blue, orange, purple, etc.) — no hex codes.

These images are for the research-explainer skill, not the paper. They should be more conceptual and accessible than the paper figures — designed to make dense text sections visual and engaging for diverse audiences.

---

## Tier 1 — Hook Images (everyone sees these)

---

**E1 — Two Flashlights**

Two flashlights with different colored beams (one warm orange, one cool blue) shining into the same dark room from different angles. Each beam illuminates objects the other misses entirely. Some objects in the center are lit by both beams. The orange beam reveals items clustered near text labels and surface patterns. The blue beam reveals items connected by lines and hidden relationships behind furniture. A small region of overlap in the middle where both beams reach. No jargon. Clean, inviting illustration style. Caption area at bottom: "Two approaches. Different blind spots. Better together."

---

**E2 — Decorrelated Search Patterns**

ONE single large network graph — a web of interconnected nodes and edges, like a sprawling constellation or city-scale transit map. Nodes are circles of varying sizes scattered across the space. Edges connect them in a complex web — some nodes are highly connected hubs, others are remote with only one or two connections. Gold stars mark important discoveries, scattered throughout — some on central well-connected nodes, some on remote peripheral nodes far from the center.

ALL search paths from ALL groups are drawn on this SAME graph simultaneously, so the viewer can directly compare who explores what:

Two experienced expert paths (dark green and emerald): Each follows a completely different chain of connections through the network. One expert traces an unusual chain from the center out to remote clusters in the bottom-left that nobody else reaches. The other expert follows a different chain of non-obvious connections into the upper-right periphery. Their paths have very little overlap with each other — they chose different edges to follow based on different mental models of what matters. Each reaches gold stars on remote nodes that nobody else visits.

Three new-hire paths (three shades of steel blue — light, medium, dark): They all start at the same obvious high-connectivity hub nodes and follow the most visible, well-traveled edges. About 60-70% of their paths overlap with each other — they form a blue cluster through the central, well-connected part of the network. They spread apart slightly at the edges but never venture far from the main hubs. They find gold stars on central nodes but miss the ones on remote periphery nodes entirely.

Four AI agent paths (orange): Nearly identical overlapping orange lines that form one thick orange stripe through the network. They follow the same high-probability edges every run — the connections that look most important based on node connectivity. Almost no divergence between runs. They cover the obvious central routes very thoroughly but ignore less-traveled connections. The diverse tools we give agents are what create whatever spread they have — without diverse tools, they'd be even more identical.

CRITICAL LAYOUT REQUIREMENT: Do NOT separate these into panels, quadrants, or side-by-side views. All paths must be drawn on the SAME single network so the viewer sees them traversing the same graph. The contrast must be visible through where the paths go: the orange stripe and blue cluster share the same central hub connections, while the two green paths branch off into completely different parts of the network — both from each other and from everyone else.

A small legend in one corner identifies the colors: "Experienced Experts" (green), "New Hires" (steel blue), "AI Agents" (orange).

Colorblind-friendly: specify colors by name (dark green, emerald, steel blue, orange) — no hex codes. No jargon. No chart axes. Clean, inviting, conceptual illustration style — flat design with simple shapes and bold named colors on a light warm-gray background. Think editorial illustration for a general audience, not a data chart.

---

**E3 — Skills as Living Snapshots**

A horizontal timeline flowing left to right. A person (simple silhouette) walks along the timeline, growing and evolving (shown by their silhouette subtly changing posture or gaining detail). At several points along the timeline, a snapshot branches downward — a captured skill file (shown as a document icon or card) that freezes what the person knew at that moment. Each snapshot is labeled with a time marker (e.g., "Year 1," "Year 2," "Year 3"). The snapshots are useful but visibly behind where the person currently stands. The person is always ahead of their last snapshot. Arrows from the person point forward ("keeps learning"), arrows from the snapshots point outward to multiple parallel lanes ("scales to every analysis"). The visual punch: the person is the source, the skills are echoes. The person is always more valuable than the skill.

---

## Tier 2 — High-Reuse Across Multiple Audiences

---

**E4 — Code Is the Easy Case**

Side-by-side comparison. Left side (labeled "Code," green tint): a clean, organized structure — files neatly connected by explicit typed arrows (imports, calls, inherits), a compiler checkpoint at the bottom giving a thumbs-up. Everything is parseable and enforced. Right side (labeled "Business Documents," orange tint): a messy tangle — contracts, amendments, specifications, regulations, and emails connected by implicit dashed lines with question marks. No compiler. Dependencies are scattered, cross-format, expressed in natural language. Some connections have labels like "referenced in amendment 3" and "contradicts clause 7.2" floating loosely. The right side should feel visibly harder — more connections, less structure, more ambiguity. Footer text: "If diverse approaches matter this much for code, they matter even more here."

---

**E5 — Expertise Encoding Flywheel**

A circular flywheel diagram with four stages flowing clockwise. Stage 1 (green): "Expert does high-value work" — a person reviewing complex material. Stage 2 (blue): "Encodes methodology into skill" — the person's approach captured as a document. Stage 3 (orange): "AI runs methodology at scale" — multiple parallel analyses using the encoded skill. Stage 4 (purple): "Expert learns from new cases" — the person encountering novel situations, building new mental models. An arrow from Stage 4 back to Stage 1 completes the loop. In the center of the flywheel: "Compounding" with a subtle upward spiral indicating that each cycle produces better skills and a more experienced expert. Important: the person appears at Stages 1, 2, and 4 — they are central to the loop, not replaced by it.

---

**E6 — Your Domain's Two Approaches**

A 2×3 grid (or 3×2). Each cell represents a profession. In each cell, two complementary analysis approaches are shown as contrasting icons or mini-diagrams separated by a "vs" divider. Row 1: Lawyers (keyword search through contracts vs. tracing clause cross-references and defined-term dependencies). Accountants (line-item review vs. ratio analysis and cross-account pattern detection). Row 2: Actuaries (standard model assumptions vs. scenario analysis with alternative correlations). Underwriters (checklist evaluation vs. portfolio-level pattern analysis). Row 3: Patent Examiners (keyword prior-art search vs. citation-network traversal). Compliance Officers (rule-based scanning vs. behavioral pattern analysis). Use profession-appropriate icons. Each cell has a small label for each approach. The visual point: every profession has its own version of "text search vs. structural analysis."

---

## Tier 3 — Audience-Specific, High Impact

---

**E7 — HCE Architecture Pipeline**

A horizontal pipeline flowchart with four connected stages, left to right. Stage 1 "Indexer" (green): source code files flowing into a tree-sitter parser that extracts a hypergraph with typed edges (calls, inherits, imports). Stage 2 "Query Engine" (blue): the hypergraph being traversed by different query strategies — blast radius, cross-cutting concerns, hierarchy, exception flow — shown as different colored paths through the graph. Stage 3 "Memory Tours" (orange): an ordered sequence of exploration steps with provenance tags showing which tool found what and why it looked there. Stage 4 "Enrichment" (purple): multiple traversal results merging, with exclusive discoveries highlighted where one strategy found something the others missed. Data flows left to right through all four stages. Clean engineering diagram style — boxes, arrows, clear labels.

---

**E8 — Specialist Stack as Ensemble**

A vertical architecture diagram. At the top, an orchestrator (labeled "Orchestrator Agent") spawns multiple subagents downward, each loading a different specialist skill from a folder. Five subagents shown: PRD Skill, Issues Skill, Tests Skill, Code Skill, Review Skill — each in a distinct color (green, blue, orange, purple, steel blue). Each subagent analyzes the same project (shown as a central artifact) and produces findings. The findings flow into a merge layer at the bottom where overlapping discoveries are deduplicated and exclusive discoveries from each specialist are highlighted with that specialist's color. The visual point: each specialist finds things the others miss, and the ensemble coverage is larger than any individual. Annotation: "Each skill encodes a different expert's search strategy."

---

**E9 — Inter vs. Intra-Department Diversity**

Two-level zoom diagram. Top level (labeled "Organization"): four department bubbles (Legal in green, Engineering in blue, Compliance in orange, Finance in purple) arranged around a central document, each with a different lens icon indicating they search differently. Arrows from each department to the document show diverse perspectives — this is inter-department diversity that organizations already have. Bottom level (labeled "Zoom: Inside One Department"): a single department bubble expanded. Inside it, one practitioner with a single search approach, shown as a single beam. Next to them, a structural analysis tool with a different beam. The practitioner alone has blind spots (grayed-out areas). The practitioner plus tool covers significantly more. The visual point: organizations have diversity across departments but often lack it within departments. That's the gap.

---

**E10 — Research Positioning Landscape**

A 2D scatter plot or positioning map. X-axis: "Text-Based Analysis" to "Structural Analysis." Y-axis: "Domain-Specific" to "General Purpose." Six labeled points plotted: Borowski et al. SCG (structural, code-specific), IRIS (neuro-symbolic, vulnerability-specific), MIT LAMM lab (structural, general theory), Tang & Runkler survey (general, text-based agents), Wolpert/Page (general, theoretical foundations). This paper ("Structured Data as LLM Tools") plotted in a distinct color at the intersection — structural + domain-methodology + proven on code with general framework. Dotted arrows from this paper toward unexplored regions labeled "Legal," "Medical," "Financial" — showing where the methodology extends but hasn't been validated yet.

---

## Tier 4 — Nice to Have

---

**E11 — Open Research Frontiers**

A central node labeled "Core Framework" (the paper's contributions) with five branches radiating outward, each ending in an open question mark. Branch 1 (green): "Cross-Domain Validation — does this work on legal, medical, financial documents?" Branch 2 (blue): "Convergence Theory — when can you stop adding runs?" Branch 3 (orange): "Ensemble Optimization — how to allocate budget across tools?" Branch 4 (purple): "Verification Cost Modeling — can we quantify how hard it is to check a finding?" Branch 5 (steel blue): "Human-AI Ensemble Theory — how to optimally combine human and AI search?" Each branch should feel like an invitation — open, unexplored, worth pursuing. Style: clean, minimal, with whitespace suggesting room for discovery.

---

**E12 — The 500K Skills Gap**

A split bar or imbalanced scale visualization. Left side (crowded, green): "Developer Tooling" — a dense cluster of 500K skill icons packed tightly, representing the current ecosystem. Right side (nearly empty, orange): "Knowledge Work" — a vast open space with only a handful of skill icons scattered across labels: "Legal Review," "Financial Modeling," "Competitive Analysis," "Medical Records," "Compliance Audit," "Contract Review." The imbalance should be visually striking — overwhelming density on one side, conspicuous emptiness on the other. Footer: "The biggest opportunity is where the skills aren't."

---

## Accessible Versions of Paper Figures

These are conceptual, illustration-style replacements for the paper's data charts. Same core message, but designed for people who aren't reading a research paper — no axes, no chart jargon, just the idea made visual.

---

**E13 — The Honeymoon Cliff (accessible version of `vibe_coding_regression.jpg`)**

A path winding from left to right through a landscape that shifts from sunny and simple to foggy and complex. On the left, a person and an AI robot walk side by side on a wide, well-paved road through a bright, familiar neighborhood — houses are labeled, streets have signs, everything is visible. The AI robot is confidently pointing the way, and the person looks relaxed. A sign reads "The Honeymoon Phase." As the path moves rightward, the road narrows, the terrain gets rougher, signs disappear, fog rolls in, and the buildings become unfamiliar and tangled. The AI robot starts hesitating — question marks float above its head, it points in conflicting directions. The person pulls out a second tool (a structural map or blueprint, colored green) and starts navigating with it while the AI stumbles. On the far right in the fog, the person with both tools (the AI and the green structural map) is making progress, while a second vignette shows the AI alone, stuck at a dead end. A small caption area at the bottom: "AI seems to 'just know' at first. That's the honeymoon. The hard part is everything after." Colorblind-friendly: specify colors by name — the sunny left side uses warm orange tones, the foggy right side uses cool blue-gray, the structural map tool is green. No hex codes. No jargon. No chart axes or data labels. Clean, inviting, conceptual illustration style — flat design with simple shapes and bold named colors on a light warm-gray background. Think editorial illustration for a general audience, not a data chart.

---

**E14 — Why Experienced Humans Break the Pattern (accessible version of `human_engineer_as_ensemble_predictor.jpg`)**

Three runners on the same racetrack, but each lane reveals something different about how they explore. Lane 1 (labeled "Experienced Expert," colored green): one runner taking a wildly unique route — vaulting over walls, cutting through unmarked passages, doubling back to check hidden corners. Their footprints are distinct and reach places no one else's do. A thought bubble shows a mental map of the whole course with annotations only they would know ("the original architect put a shortcut here," "this changed in '09"). Lane 2 (labeled "New Hire," colored steel blue): a runner with fresh energy taking a reasonable but predictable route. Their footprints overlap significantly with faint footprints from other new hires — they all tend to find the same things. Lane 3 (labeled "Additional AI Runs," colored orange): multiple identical robot runners stacked on top of each other, all running nearly the exact same path every time. Their footprints are one thick, repeated line. A dotted ceiling above them labeled "correlation floor" — they physically cannot spread out beyond it because they share the same training. The visual punch: adding more robots doesn't widen the search, but one experienced human shatters the pattern. Caption area at bottom: "One experienced person breaks the pattern more than ten extra AI runs." Colorblind-friendly: specify colors by name (green, steel blue, orange) — no hex codes. No jargon. No chart axes or data labels. Clean, inviting, conceptual illustration style — flat design with simple shapes and bold named colors on a light warm-gray background. Think editorial illustration for a general audience, not a data chart.
