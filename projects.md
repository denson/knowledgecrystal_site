---
layout: default
title: Projects
permalink: /projects.html
---

# Projects

<div class="grid">
  <div class="card">
    <h3>Hypergraph Code Explorer (HCE)</h3>
    <p>A tool that transforms codebases into interactive, queryable maps. HCE uses tree-sitter to parse code into a hypergraph — where a single edge groups multiple related entities (caller, callee, argument types, return type) as one relationship, rather than decomposing them into pairwise connections that lose information.</p>
    <p>Supports 9 languages. Provides MCP tools so AI agents like Claude can explore codebase structure in milliseconds without consuming LLM tokens for parsing. Captures seven relationship types: CALLS, IMPORTS, DEFINES, INHERITS, SIGNATURE, RAISES, and DECORATES.</p>
    <p>The research behind HCE showed that combining structural traversal with text search finds things neither approach finds alone — with the effect scaling dramatically on larger codebases.</p>
    <div>
      <span class="card-tag">Python</span>
      <span class="card-tag">Hypergraphs</span>
      <span class="card-tag">AST Analysis</span>
      <span class="card-tag">MCP Tools</span>
      <span class="card-tag">tree-sitter</span>
    </div>
    <p style="margin-top: 1.5rem;">
      <a href="https://github.com/denson/hypergraph_code_explorer" class="btn btn-secondary" style="padding: 0.5rem 1rem; font-size: 0.95rem;">View on GitHub →</a>
    </p>
  </div>
  <div class="card">
    <h3>Ariadne Thread</h3>
    <p>An open source document extraction and retrieval pipeline that saves AI agents 100–200x in token costs. Converts 20+ document formats into clean Markdown, chunks intelligently, embeds for semantic search, and stores everything in Postgres with pgvector.</p>
    <p>Deploy once on Railway (free tier works), connect Claude Code with one CLI command, and your agents get six tools for document ingestion, search, and retrieval. Any MCP-compatible agent system — Open Brain, OpenClaw, Cursor — connects the same way.</p>
    <p>Basic extraction is free via MarkItDown. The full pipeline costs pennies per document. The expensive model never touches raw documents.</p>
    <div>
      <span class="card-tag">Python</span>
      <span class="card-tag">Document Pipeline</span>
      <span class="card-tag">pgvector</span>
      <span class="card-tag">MCP Tools</span>
      <span class="card-tag">Semantic Search</span>
      <span class="card-tag">MarkItDown</span>
    </div>
    <p style="margin-top: 1.5rem;">
      <a href="https://github.com/denson/ariadne-thread" class="btn btn-secondary" style="padding: 0.5rem 1rem; font-size: 0.95rem;">View on GitHub →</a>
    </p>
  </div>
</div>

More projects coming soon. In the meantime, you can find my other work on [GitHub](https://github.com/denson).
