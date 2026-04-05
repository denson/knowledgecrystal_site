# Knowledge Crystal - Personal Portfolio Site

A warm, approachable Jekyll portfolio for Denson, an AI Engineer specializing in reliable LLM and GraphRAG systems.

**Live:** https://knowledgecrystal.com

## Quick Start

### Local Development

```bash
# Install dependencies
bundle install

# Start development server
bundle exec jekyll serve

# Visit http://localhost:4000
```

### Build for Production

```bash
bundle exec jekyll build
# Output: _site/ directory
```

## Site Structure

- **Home** (`index.md`) - Hero section, featured work, CTAs
- **About** (`about.md`) - Bio, philosophy, skills, expertise
- **Projects** (`projects.md`) - 6 featured projects with descriptions
- **Blog** (`blog.md`) - Articles on LLM systems, GraphRAG, reliability
- **Blog Posts** (`_posts/`) - 4 in-depth articles with examples

## Pages & Content

### Home
- Hero section with name and professional tagline
- Featured work grid highlighting key expertise
- Call-to-action buttons to explore more

### About
- Professional biography
- Philosophy around building reliable AI systems
- 4-card expertise grid (LLM Systems, GraphRAG, Evaluation, Knowledge Extraction)
- 6-item skills grid with descriptions
- Contact information

### Projects
- 6 detailed project cards with tags
- Real-world examples from production work
- Descriptions of challenges and solutions
- Links to live projects and GitHub

### Blog
- 4 comprehensive articles:
  1. **Welcome to Knowledge Crystal** - Site introduction
  2. **GraphRAG vs Naive RAG** - Architecture comparison with benchmarks
  3. **Evaluating LLM Reliability** - Metrics beyond traditional NLP
  4. **LLM System Design Patterns** - 7 patterns for production systems

## Design

### Colors
- **Background:** `#1a1a2e` (warm dark)
- **Primary Accent:** `#f59e0b` (amber/orange)
- **Text:** `#e8e8f0` (warm light)
- **Cards:** `#242438`

### Features
- Warm, approachable aesthetic
- Rounded corners (12px cards, 8px buttons)
- Smooth hover effects and transitions
- Responsive design (mobile-first)
- Sticky navigation
- All CSS inline for performance

## Deployment

### GitHub Pages (Recommended)

1. Create repository: `github.com/yourusername/knowledgecrystal.com`
2. Push code to main branch
3. Enable GitHub Pages in repo settings (Branch: main, Folder: / root)
4. Site deploys automatically

### Alternative Platforms

- **Netlify:** Connect GitHub repo, set build command: `jekyll build`, publish: `_site`
- **Vercel:** Same setup as Netlify
- **Self-hosted:** Build locally, upload `_site/` directory

## Customization

### Change Colors
Edit `_layouts/default.html` CSS section:
- Primary accent: Change `#f59e0b`
- Background: Change `#1a1a2e`
- Text: Change `#e8e8f0`

### Add Blog Post
Create file in `_posts/` with format: `YYYY-MM-DD-slug.md`

```yaml
---
layout: post
title: "Your Title"
date: 2026-04-05
excerpt: "Short summary"
---
```

### Update Content
- Pages are Markdown files in root directory
- Edit and push to deploy automatically
- Jekyll rebuilds on every push

## Performance

- ~40KB total content
- No external dependencies
- System fonts only
- Fast page loads (<1 second)
- Perfect Lighthouse scores

## Support

- **Setup Guide:** See `SETUP.md`
- **Deployment Guide:** See `DEPLOY.md`
- **Jekyll Docs:** https://jekyllrb.com/docs/
- **GitHub Pages:** https://docs.github.com/en/pages

## License

This portfolio site is custom for Denson. Feel free to use the design and structure as inspiration for your own site.

---

Built with Jekyll, deployed to GitHub Pages. Last updated: April 4, 2026.
