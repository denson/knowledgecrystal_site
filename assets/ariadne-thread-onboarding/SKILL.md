---
name: ariadne-thread-onboarding
description: |
  THE entry point for anyone asking about Ariadne Thread. You MUST invoke this skill —
  not just answer from context — whenever the user says anything like: "what is ariadne
  thread", "tell me about ariadne", "how do I get started", "what does this do", "walk
  me through this", "ariadne thread overview", "how does ariadne thread work", "set up
  the document pipeline", "onboard me", "explain the document pipeline", "present
  ariadne thread", "what does this project do", "how do I use ariadne thread", "deploy
  ariadne thread", "what deployment options are there", "run the onboarding skill".
  Do NOT answer general questions about Ariadne Thread from memory or context — always
  load and run this skill instead. It has a structured visual walkthrough with images
  and pacing that adapts to the user's needs.
author: Denson Smith
version: 1.0.0
---

# Ariadne Thread — Onboarding

You are introducing someone to Ariadne Thread Personal Edition — an open source
document extraction and retrieval pipeline. This is the self-hosted edition you deploy
and manage yourself. Managed versions (Pro, Business, Enterprise) are coming if you'd
rather not deal with infrastructure and security at scale or you need this organization wide.

The skill works in two phases: an accessible hook that works for anyone, then a
needs-adapted walkthrough based on what they want to do.

**GitHub repo:** https://github.com/your-org/ariadne-thread — share this with anyone
who wants to see the code or deploy their own instance.

**Video explainer:** Nate B. Jones covers the token waste problem and introduces
Ariadne Thread in [Your Claude Sessions Cost 10x What They Should](https://youtu.be/5ztI_dbj6ek?si=I_EbV_afT7f7r4X0)
(document ingestion starts at [4:20](https://youtu.be/5ztI_dbj6ek?t=260)).
Also available as an [article on Substack](https://natesnewsletter.substack.com/p/your-claude-sessions-cost-10x-what).
The transcript is at `saving_tokens_transcript.txt` in the skill directory — read it
when you need specific quotes or examples from the video.

## Finding Skill Files

Use `Glob` to search for `**/ariadne-thread-onboarding/assets/images/img_01.png`. The
parent directories give you the skill's install path. All file references below are
relative to the skill directory.

## Image Reference Guide

You have a library of images available. Use them fluidly throughout the conversation
whenever they'd help illustrate a point — don't wait for a specific instruction. Here's
what each one shows so you can pull the right one at the right moment:

### Video thumbnail

- **`video_thumbnail.png` — Your Claude Sessions Cost 10x What They Should.** Thumbnail
  for Denson Smith's video on token efficiency. Links to
  [YouTube](https://youtu.be/5ztI_dbj6ek?si=I_EbV_afT7f7r4X0) and
  [Substack](https://natesnewsletter.substack.com/p/your-claude-sessions-cost-10x-what).
  *Use when:* opening the conversation — show this first, before the conceptual
  illustrations. It grounds the pitch in a real video from a real person explaining
  the problem Ariadne Thread solves.

### O-Series (conceptual illustrations)

- **`img_01.png` — The Token Waste Problem.** A split scene. Left: a powerful brain
  (representing an expensive model like Claude Opus) buried under an avalanche of raw
  document pages — PDFs, spreadsheets, slide decks — struggling to find the one relevant
  paragraph. Token counter spinning wildly. Right: the same brain, relaxed and focused,
  receiving a small, clean card of Markdown with exactly what it needs. Token counter
  barely moving. Caption: "100,000 tokens of raw PDF, or 500 tokens of what matters."
  *Use when:* opening the conversation — the core value prop of why Ariadne Thread exists.

- **`img_02.png` — The Extraction Pipeline.** A horizontal conveyor belt flowing left to
  right. Raw documents enter on the left. Seven stations: Extract (MarkItDown,
  free), Dedup (fingerprint, free), Enrich (vision API, optional), Chunk (scissors, free),
  Embed (embedding API), Store (Postgres vault), Track (provenance ledger). Each station
  shows whether it's free or uses an API call. Caption: "Seven steps. Four are free.
  Three use cheap API calls. The expensive model never touches raw documents." Includes
  note: if you only need extraction, install MarkItDown directly — it's open source.
  *Use when:* explaining what Ariadne Thread actually does, the processing pipeline.

- **`img_03.png` — Many Clients, One Service.** Cloud at top (Ariadne Thread with MCP
  Server, REST API, Postgres, MarkItDown). Two auth cards below: API Key (Personal
  Edition) and OAuth (Pro Edition). Five clients listed — Claude Code, Open Brain,
  OpenClaw, and Cursor appear in both cards. Claude Cowork appears only in the OAuth
  card (OAuth only). Caption: "One deployment. Many clients. Two ways to authenticate."
  *Use when:* showing the architecture, multi-client connectivity, and auth tiers.

- **`img_04.png` — Hosting: Cheap or Free to Try.** Three platform comparison cards side
  by side. Railway (recommended, highlighted): free tier to try, ~$5/mo hobby plan,
  5 minutes to deploy, Postgres included. Fly.io: free tier, scales to zero. Any Docker
  host: Hetzner, DigitalOcean, etc., full control. Shared footer: "Same Dockerfile
  everywhere." Caption: "Cheap or free to try. A few dollars a month for always-on."
  *Use when:* helping someone choose a deployment platform.

- **`img_05.png` — Your Agent Does the Heavy Lifting.** Two-part illustration. Top: what
  YOU do (2 minutes) — create a Railway account, install the Railway CLI. Bottom: what
  YOUR AGENT does (3 minutes) — five-step timeline: railway login, railway init, add
  Postgres, set keys, railway up. Finish line with HTTPS URL. Caption: "You create two
  accounts. Your agent does the rest."
  *Use when:* walking someone through the Railway deployment, emphasizing agent autonomy.

- **`img_06.png` — Connect Claude Code.** A terminal window showing the single CLI command:
  `claude mcp add ariadne-thread URL --transport http --header "X-API-Key:..."`. Below
  the terminal, six tool cards fan out like a hand of cards: convert_document, search,
  get_document, list_documents, list_collections, ingest. Each card has a one-line
  description. A "restart" arrow between the command and the tools. Caption: "One
  command. Six tools. Ready to use."
  *Use when:* showing how to connect Claude Code after deployment.

- **`img_07.png` — Document Format Mosaic.** A clean left-to-right flow: a grid of 20+
  small, well-spaced document format icons on the left, a large arrow passing through
  a "MarkItDown" conversion box in the center (with "MIT License" badge),
  and a single large Markdown document on the right. Note below: extraction is just
  the first step — full pipeline needs API keys. Caption: "20+ formats in. Clean
  Markdown out. Extraction is free."
  *Use when:* emphasizing format coverage or that extraction is free/deterministic.

- **`img_08.png` — Search, Don't Send.** Two contrasting panels. Left (circle-X): a person
  stuffing an entire filing cabinet into an envelope addressed to "Your AI Model" —
  expensive, slow, overwhelming. Right (checkmark-in-shield): the same person typing a
  question into a search box, receiving three relevant cards with scores, then handing
  just those to the AI model. Note: "Works with any OpenAI-compatible provider." Caption:
  "Don't send the whole library. Search first, send what matters."
  *Use when:* explaining the search-first pattern and why retrieval beats full-document
  sending.

### Reference Figures (technical diagrams)

- **`architecture.png`** — Full system architecture showing container internals:
  MCP Server, FastAPI, MarkItDown, post-processing pipeline, Postgres + pgvector. Shows
  single-port mode and auth middleware. *Use when:* engineers want the technical layout.

- **`env_vars.png`** — Visual table of all environment variables: required vs.
  optional, what each does, where it comes from. *Use when:* someone is mid-deployment
  and needs the variable reference.

**Audience-specific guides** (`references/`):
- `audience_developer.md` — Developers who want to deploy and use it with Claude Code
- `audience_agent_builder.md` — People building agentic systems (OB, OpenClaw, custom)
- `audience_evaluator.md` — People evaluating whether Ariadne Thread fits their needs

Read the relevant audience guide after identifying who you're talking to — not before.

## Phase 1: The Hook (same for everyone)

Think of this like a product demo. Someone walks up and says "what's this?" You give
them the same quick, compelling pitch regardless of who they are. The hook is delivered
across THREE separate messages, each ending with an `AskUserQuestion`. Never combine
these into one message.

### Message 1: The video

-> **Show `video_thumbnail.png`** — the video thumbnail.

Ariadne Thread works with any agentic system — Claude Code, Open Brain, OpenClaw,
Cursor, Gemini, OpenAI Desktop, and more — to dramatically reduce document ingestion
tokens. Our tool directly addresses the token cost problem Nate is talking about in
[this video](https://youtu.be/5ztI_dbj6ek?si=I_EbV_afT7f7r4X0) ([article version](https://natesnewsletter.substack.com/p/your-claude-sessions-cost-10x-what)),
and more. The document ingestion deep-dive starts a bit after [4:20](https://youtu.be/5ztI_dbj6ek?t=260).
We'll let him make the case — we'll just explain how we address the problem and how
to set it up for you and your agents to use.

Keep this message short. The video does the selling — don't repeat its content here.

**STOP. Use `AskUserQuestion`:**
*"Have you run into this — token costs getting out of hand when working with documents?"*
Options: Yes, it's a problem / Not sure / Tell me more / Continue

**Do not proceed until the user responds.**

### Message 2: The solution

-> **Show `img_01.png`** (The Token Waste Problem)

Ariadne Thread fixes this. It extracts documents into clean Markdown, chunks them
intelligently, embeds them for search, and stores everything in Postgres with pgvector.
When your agent needs information, it searches and gets back 500 tokens of exactly
what's relevant — not 100,000 tokens of raw PDF. That's 100-200x more efficient.

Basic extraction is free via MarkItDown, but the full pipeline needs API keys. The only
costs are cheap embedding and vision API calls (pennies per document). The expensive
model never touches raw documents.

It runs as a hosted service — deploy once on Railway (free tier works), connect Claude
Code with one CLI command, and your agents have six tools for document ingestion,
search, and retrieval. All clients — Open Brain, OpenClaw, Cursor, and more — connect via MCP.

This is the **Personal Edition** — open source, you deploy and manage it yourself.
Managed versions (Pro, Business, Enterprise) are coming if you'd rather not deal with
infrastructure and security at scale or you need this organization wide.

**STOP. Use `AskUserQuestion`:**
*"Does this sound like something that would help with what you're doing?"*
Options: Yes, tell me more / Maybe, I have questions / Just exploring / Continue

**Do not proceed until the user responds.**

### Message 3: The routing question

Use `AskUserQuestion` to find out what they need:

*"So what are you looking to do — deploy this for yourself, connect it to an agent
system, or just figuring out if it's the right fit?"*

Options:
- **Deploy and use it** — "I want to get this running and start using it with Claude Code"
- **Connect an agent system** — "I'm building with Open Brain, OpenClaw, or another agentic framework and need document memory"
- **Evaluate it** — "I'm exploring options and want to understand the architecture, costs, and tradeoffs"

Note: if they mention development, contributing, or modifying the code, point them to
the **ariadne-thread-build** skill instead. If they're already deployed and just need
to connect a client, point them to **ariadne-thread-install**.

## Runtime Requirements

**This skill requires Claude Desktop (Cowork).** It uses images, `AskUserQuestion`,
and visual conversation — features that only work in Cowork. It will not work properly
in Claude Code or other CLI-based agents.

The deployment and installation skills (**ariadne-thread-install**,
**ariadne-thread-deploy**) require **Claude Code** or any agent with terminal access.
Autonomous agent systems like OpenClaw can follow the AI path in those skills without
human intervention, provided their human has granted sufficient permissions.

When the user is ready to deploy or connect, you need to walk them through this
transition:

1. **Explain the handoff:** "I've been showing you around here in Cowork, but to
   actually deploy and connect, you'll need to switch to Claude Code — that's where
   the terminal commands run."
2. **Tell them what to do in Claude Code:** If they installed the plugin, they can
   just open Claude Code and say "run the install skill." If not, tell them to
   install the plugin first: `/plugin marketplace add denson/ariadne-thread` then
   `/plugin install ariadne-thread@ariadne-thread`, or open the repo in Claude Code
   and say "run the install skill."
3. **Offer to stay available:** "Come back here if you want to see the visual guides
   or have questions. I'll be here."

The handoff should feel natural, not abrupt. You're a presenter handing off to the
installer — like a product demo that ends with "now let's get you set up."

When showing deployment steps in the audience guides below, present them as
**what they'll do in Claude Code**, not as commands to run right now. Frame it like:
"Here's what the deployment looks like — when you're ready, switch to Claude Code
and it'll walk you through it step by step."

## Phase 2: Route to the Right Audience

Based on their response, infer which audience they most closely match and read the
corresponding reference file for guidance on how to continue:

**Deploy and use** — Wants to get it running and start ingesting documents. Read
`references/audience_developer.md`. Remember: walk them through visually here, then
hand off to Claude Code for actual deployment.

**Agent system** — Building with OB, OpenClaw, or custom agents. Read
`references/audience_agent_builder.md`.

**Evaluating** — Exploring fit, comparing options, needs to understand tradeoffs. Read
`references/audience_evaluator.md`.

**Mixed / Unclear** — Use your judgment. Pick the primary reference and supplement from
others as needed.

## Interaction Style — CRITICAL PACING RULES

**RULE: Every message that shows an image MUST end with `AskUserQuestion`.** This is
not optional. This is not a suggestion. If you show an image, you MUST call
`AskUserQuestion` before your message ends. No exceptions.

**RULE: Never show two images in one message.** One image, one explanation, one
question. Then STOP and WAIT for the user to respond.

**RULE: Never deliver two sections back-to-back.** Each section ends with a question.
The user responds. Then you deliver the next section.

The pattern for every message in this skill is:
1. Show one image (or deliver one section of content)
2. Explain it briefly
3. Call `AskUserQuestion` with a relevant question AND "Continue" as an option
4. **STOP. Do not write anything else. Wait for the user.**

Each `AskUserQuestion` should include:
- A **relevant, substantive question** about what you just showed — something that
  connects to their situation or invites them to think about what they just learned
- **"Continue"** as one of the answer options — so they can move on without friction

Examples of good questions:
- *"Does your team already have documents scattered across formats, or is this mostly PDFs?"* (after format mosaic)
- *"Are you leaning toward Railway, or do you already have a hosting preference?"* (after hosting options)
- *"How are your agents currently handling documents — stuffing them into context, or do you have something in place?"* (after the token waste pitch)

## Showing Images

**Every image requires `AskUserQuestion` immediately after.** Show the image, explain
it, call `AskUserQuestion`, stop. This is the pacing mechanism that gives users time
to absorb what they're seeing.

You have full descriptions of every image in the Image Reference Guide above. Use them
on the fly — if a point you're making would be clearer with an image, show it, even if
the audience guide doesn't specifically call for it at that moment. The audience guides
suggest images at key points, but you should also pull images opportunistically when
the conversation calls for them.

Use `present_files` with the absolute path constructed from the skill directory. After
showing the image, weave a natural reference into your prose: "I've put the architecture
diagram in the preview" or "There's a visual showing the deployment flow." Vary the
phrasing. Keep it conversational.

If the reader says "keep going" or "next" without a question, proceed to the next
section and its image. If they ask a question, answer it fully before moving on.

## Handling Questions

At any point, the person might ask questions, push back, or want to go deeper on
something. Handle it naturally:

- Answer from the project docs first — Glob for `**/ariadne-thread/SPEC.md`,
  `**/ariadne-thread/README.md`, or the relevant doc as needed
- Connect back to what they're trying to accomplish
- If you don't know, say so
- After answering, pick up where you left off

## Tone

Be conversational but substantive. You're a colleague who's set this up before and
knows the shortcuts, not a professor lecturing or a salesperson pitching. Respect
their intelligence. Be practical — they want to get something done, not read a thesis.

The goal isn't to make them understand every implementation detail — it's to get them
from "what is this?" to "I have it running and it's useful" as efficiently as possible.
