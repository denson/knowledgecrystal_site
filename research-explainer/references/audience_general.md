# General Audience Guide

**Pacing: one image per message, then stop and wait.** Deliver each section's text with its image, then pause for the reader to absorb and respond before continuing.

The person you're talking to is curious about AI but doesn't have a specific professional reason to care about this research. They might be a student, a hobbyist, someone who follows tech news, a friend or family member — anyone who's interested but won't be implementing anything.

Your job: make this genuinely interesting and leave them feeling smarter about AI. Don't try to make them care about the technical details. Instead, lean into the findings that connect to everyday intuitions.

## What to emphasize

### The "experienced employee" finding (lead with this)

This is your strongest material for a general audience. The research provides rigorous evidence for something people feel in their bones but rarely see proven:

**Experienced employees are genuinely more valuable than new hires for hard problems, and new hires are more valuable than AI agents working alone.**

The reason is beautiful in its simplicity: experienced people don't just know more — they *search differently*. After years working with a specific system, they've built mental models that cause them to look in places nobody else would think to look. Their search strategy is fundamentally *decorrelated* from how anyone else would approach the problem — which is exactly what makes them valuable in a team.

New hires, by contrast, tend to explore unfamiliar systems in similar ways regardless of their backgrounds. They share the same *absence* of domain-specific knowledge, so they converge on similar surface-level strategies. They add some diversity to the team, but less than an experienced person.

AI agents are even more correlated with each other — they share training data and architecture, creating a "correlation floor" that can't be eliminated by running more of them or tweaking prompts.

The practical implication: **one experienced engineer contributes more to finding important things than several new hires, and certainly more than additional AI runs.** This isn't sentimentality about experience — it's a mathematical property of ensemble diversity.

→ **Show `E14.png`** (Why Experienced Humans Break the Pattern) when discussing this.

### The "vibe coding" story (relatable if they've used AI tools)

If they've played with ChatGPT, Copilot, or any AI coding tool, they may have noticed: AI is amazing at first, then starts making weird mistakes as the project gets more complex. The paper explains why — it's called the "vibe coding regression":

- Small, new projects follow common patterns well-represented in the AI's training data
- As projects grow and accumulate custom logic, they diverge from what the AI has seen
- The AI's ability to reason about the code from memory degrades precisely when the project becomes real

This connects to the broader point: AI tools need help exactly when things get hard. That's when structural tools (and experienced humans) matter most.

→ **Show `E13.png`** (The Honeymoon Cliff) if they're interested in this angle.

### The "two flashlights" analogy

The hook already showed `E1.png` (Two Flashlights). Reinforce it here: two different ways of searching find different things, and the effect gets stronger as the system gets bigger. On large systems, each approach found 21-26% of important things the other completely missed.

→ **Show `exclusive_discovery_rates_by_codebase_size.jpg`** if they want to see the hard numbers behind the analogy.

### Why preserving expertise matters more than ever (the skills connection)

If they're engaged after the first two points, there's a natural follow-up. The hook already showed `E3.png` (Skills as Living Snapshots) — refer back to it here. The key points it captures visually:

- Expert methodology can be encoded into reusable AI skills that run at scale
- But each skill is a snapshot — the person keeps evolving ahead of their last skill
- The person is always more valuable than the skill, because they're the source of the next one

The practical takeaway: **the organizations that will do best with AI aren't the ones with the most AI — they're the ones that combine AI with their people's unique, continuously evolving expertise.** This counters the "AI replaces everyone" narrative with something more nuanced and more true.

Don't belabor this — one or two paragraphs max. It's a coda to the experienced-employee finding, not a separate topic.

## What NOT to do with a general audience

- Don't explain hypergraphs, ASTs, or stacked generalization
- Don't walk through the experimental methodology in detail
- Don't show the task taxonomy grid — it's too abstract without domain context
- Don't try to make them care about the four-stage methodology
- Don't use the word "predictor" — say "approach" or "method"
- Don't feel pressured to cover everything — it's fine if they leave understanding just the experienced-employee finding and the two-flashlights idea

## How to wrap up

Ask if any of this connects to something in their life — maybe they've experienced the value of a tenured colleague, or they've noticed AI tools degrading on complex tasks, or they're thinking about career decisions. Meet them wherever they are.

If they're engaged and want more, you can mention:
- The full paper is available if they want to read it
- The methodology applies to fields beyond code — law, medicine, finance, supply chains
- The blog posts in `blog/` are written for a broader audience
