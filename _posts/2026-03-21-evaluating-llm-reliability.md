---
layout: post
title: "Evaluating LLM Reliability: Beyond BLEU Scores"
date: 2026-03-21
excerpt: "Why traditional NLP metrics fail for LLM evaluation, and what actually matters for production systems."
---

You can't improve what you don't measure. But measuring LLM systems is harder than people think.

Most teams start with metrics inherited from the NLP era: BLEU, ROUGE, F1. These metrics can be useful, but they miss what actually matters in production: **Does the system do what we need reliably?**

## The Problem with Traditional Metrics

### BLEU and ROUGE Are Narrow

These metrics measure surface-level similarity to reference outputs. But an LLM response that's semantically perfect but phrased differently will score poorly.

Example:
- Reference: "The company was founded in 1995"
- Output: "This organization was established in 1995"
- BLEU Score: Low
- Actual Quality: High

### They Don't Measure Hallucinations

You can get high BLEU/ROUGE scores while hallucinating. A model that writes plausible-sounding fiction will score high on surface metrics.

I've seen this in real projects: a customer support chatbot that scored 0.78 BLEU had a 15% hallucination rate.

## What Actually Matters

For production LLM systems, I measure:

### 1. Factuality
Does the system output factually correct information? This requires:
- Reference data to check against
- Semantic similarity checks (not string matching)
- Domain-expert evaluation for subjective domains

### 2. Hallucination Rate
What percentage of outputs contain information not in the source material?

```python
def has_hallucination(response, source_documents):
    # Check if claims in response exist in sources
    # This is harder than it sounds—requires reasoning
    facts = extract_facts(response)
    for fact in facts:
        if not is_supported_by(fact, source_documents):
            return True
    return False
```

### 3. Coverage
Does the system attempt to answer the query, or does it avoid difficult questions?

### 4. Latency & Cost
Does it serve responses fast enough and cheaply enough?

### 5. Consistency
Does the system give the same answer to the same question asked different ways?

## Building Your Evaluation Suite

For a production system, I recommend:

1. **Automated Metrics** (run on every change):
   - Hallucination detection
   - Fact checking against sources
   - Latency monitoring

2. **Sampled Human Evaluation** (weekly):
   - Rate 50-100 random outputs
   - Score on: accuracy, completeness, tone
   - Look for patterns in errors

3. **Targeted Testing** (per feature):
   - Edge cases specific to your domain
   - Known hard problems
   - Regression tests for past failures

4. **Production Monitoring**:
   - User feedback signals (thumbs up/down)
   - Error logs and exceptions
   - Performance degradation alarms

## A Real Example

For a legal research tool, we built:

```
Manual Metrics:
- Accuracy on known test queries: 96%
- Hallucination rate: 2.1%
- False positive rate (citing non-existent laws): 0.3%

Automated:
- Citation validation (law exists + is current)
- Semantic similarity to known good answers
- Latency tracking

Result:
- Could deploy confidently
- Caught a prompt regression in 4 hours
- User satisfaction: 94%
```

## The Hard Truth

LLM evaluation is still more art than science. You'll need people who understand your domain to validate outputs. But with a thoughtful measurement approach, you can build confidence in your system.

Start measuring today. Your future self will be grateful.

—Denson
