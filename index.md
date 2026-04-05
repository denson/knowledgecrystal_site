---
layout: default
title: Home
permalink: /
---

<div class="hero">
  <h1>Denson</h1>
  <p class="tagline">AI Engineer building reliable LLM & GraphRAG systems for teams that can't afford hallucinations</p>
  <div class="cta-buttons">
    <a href="/about.html" class="btn btn-primary">Learn More</a>
    <a href="/blog.html" class="btn btn-secondary">Read the Blog</a>
  </div>
</div>

## What I Do

I specialize in building production-ready LLM systems and knowledge graph retrieval architectures that deliver reliable, grounded answers. I help teams deploy intelligent systems that actually work — without the hallucinations that plague modern AI applications.

<div class="grid">
  <div class="card">
    <h3>LLM Systems Engineering</h3>
    <p>Designing robust AI systems that balance performance with reliability. System design patterns, prompt engineering, and evaluation frameworks for consistent outputs.</p>
    <span class="card-tag">LLMs</span>
    <span class="card-tag">Prompting</span>
    <span class="card-tag">RAG</span>
  </div>

  <div class="card">
    <h3>GraphRAG Architecture</h3>
    <p>Knowledge graph systems that provide precise, contextual information retrieval. Using structured knowledge representations to ground AI responses and reduce hallucinations.</p>
    <span class="card-tag">GraphRAG</span>
    <span class="card-tag">Knowledge Graphs</span>
    <span class="card-tag">Semantic Search</span>
  </div>

  <div class="card">
    <h3>Production Deployment</h3>
    <p>Taking models from research to production with proper monitoring, evaluation, and iteration. Scaling AI systems safely and reliably in real-world environments.</p>
    <span class="card-tag">Deployment</span>
    <span class="card-tag">MLOps</span>
    <span class="card-tag">Evaluation</span>
  </div>
</div>

## Latest from the Blog

{% for post in site.posts limit:3 %}
<div class="card" style="margin-bottom: 1rem;">
  <h3><a href="{{ post.url }}">{{ post.title }}</a></h3>
  <p>{{ post.excerpt | strip_html | truncatewords: 30 }}</p>
  <small>{{ post.date | date: "%B %d, %Y" }}</small>
</div>
{% endfor %}

<a href="/blog.html" class="btn btn-secondary">All articles →</a>
