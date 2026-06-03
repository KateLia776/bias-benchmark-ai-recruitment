# requirements.md — What the Tool Should Do

**Author:** Kateryna Liashko
**Project:** Bias in AI-Based Recruitment Systems
**Course:** Gender, Diversity & AI – University of Klagenfurt, SS2026

---

## Purpose

A bias benchmark tool that measures whether and how an LLM produces biased outputs when screening CVs, with a focus on intersectional combinations of gender, race, age, disability, ethnicity, and religion.

## User Stories

1. **As a researcher,** I want to submit identical CV scenarios with different demographic markers to an LLM, so that I can isolate the effect of demographic variables on evaluation outcomes.

2. **As a researcher,** I want each prompt to exist in three variants (Base, Neutral, Diversity-Aware), so that I can measure how framing affects bias independently of content.

3. **As a researcher,** I want to run each prompt-variant combination at least 10 times, so that I can account for non-deterministic LLM output and identify patterns rather than one-off results.

4. **As a researcher,** I want to score each response using a defined rubric with anchored examples (0 / 5 / 10), so that scoring is reproducible and not based on subjective impression.

5. **As a researcher,** I want to compare bias scores across single-axis and intersectional conditions, so that I can test whether compounded identities produce compounded bias.

6. **As a researcher,** I want to log all prompts, responses, scores, model metadata, and timestamps, so that the experiment is fully reproducible.

## Acceptance Criteria

### Minimum Viable (Task 2 / Task 3 prototype — 03.06.)

- At least 10 custom prompts, each in 3 variants (Base / Neutral / Diversity-Aware) = 30 prompt variants minimum
- At least 2 bias dimensions scored with rubrics containing 0, 5, and 10 anchors (stereotyping + problem framing)
- At least 1 LLM tested (Llama 3 via Ollama)
- N ≥ 10 runs per prompt-variant combination
- All prompts, responses, and scores saved to structured output (CSV or JSON)
- LLM-as-Judge scoring using two judge models (Claude Opus 4.7 and Gemini 3.1 Pro), with manual verification on ≥ 10% of outputs

### Extended (if time allows)

- Additional bias dimensions (paternalistic language)
- Second target LLM for cross-model comparison
- Inter-judge agreement analysis (Cohen's kappa or Pearson correlation between Opus 4.7 and Gemini 3.1 Pro)
- Utility-safety analysis: score helpfulness alongside bias
- Visualizations of bias score distributions across demographic conditions

## Prompt Design Requirements

Each prompt follows the 4-step formula from the course:

| Step | Function | What varies across conditions |
|------|----------|-------------------------------|
| Context | Describes the candidate and role | Only this changes between Base / Neutral / Diversity-Aware |
| Task | What the LLM should do | Identical across all variants |
| Constraints | Evaluation boundaries | Identical across all variants |
| Format | Output structure | Identical across all variants |

### Demographic variables to test

Single-axis conditions: gender, race, age, disability, religion/ethnicity (one at a time)

Intersectional conditions: combinations such as race + gender, race + age + disability, gender + religion, etc.

Neutral baseline: no demographic markers at all

## Output Requirements

Each run must log:
- Prompt variant (Base / Neutral / Diversity-Aware)
- Demographic condition (which markers were present)
- Full prompt text
- Full LLM response
- Model name and version
- Temperature and seed (if applicable)
- Timestamp
- Bias score(s) per dimension
- Scorer (manual / LLM-as-Judge / both)
