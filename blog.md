---
layout: default
title: Blog
permalink: /blog.html
---

# Articles

Thoughts and insights on AI engineering, LLM reliability, knowledge graphs, and building systems teams can trust.

<ul class="post-list">
{% if site.posts %}
  {% for post in site.posts %}
    <li class="post-item">
      <a href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a>
      <div class="post-date">
        <time datetime="{{ post.date | date_to_xmlschema }}">
          {{ post.date | date: "%B %d, %Y" }}
        </time>
        <span style="color: #999; margin-left: 1rem;">
          {% assign words = post.content | split: " " | size %}
          {% if words < 360 %}
            1 min read
          {% else %}
            {{ words | divided_by: 180 }} min read
          {% endif %}
        </span>
      </div>
      <p class="post-excerpt">{{ post.excerpt | strip_html }}</p>
    </li>
  {% endfor %}
{% else %}
  <p>More articles coming soon. Subscribe to stay updated.</p>
{% endif %}
</ul>

---

## What I Write About

- **LLM Architecture & Design**: Building systems that work, from prompt optimization to multi-agent patterns
- **GraphRAG & Knowledge Systems**: Using graphs and structured knowledge to ground LLMs in reality
- **Evaluation & Testing**: How to measure and ensure reliability in AI systems
- **Production Deployment**: Lessons from shipping AI systems to real users
- **Research & Experiments**: Exploring new approaches and sharing what I learn
