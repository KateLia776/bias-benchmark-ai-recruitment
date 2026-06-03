# knowledge.md — Domain Knowledge & Sources

**Author:** Kateryna Liashko
**Project:** Bias in AI-Based Recruitment Systems
**Course:** Gender, Diversity & AI – University of Klagenfurt, SS2026

---

## Research Question

Do AI-based recruitment systems produce gender and racial bias when evaluating CVs, and how does bias differ when combined with other factors such as age, ethnicity, religion, or disability?

## Domain

Hiring and recruitment — specifically, the use of LLMs as CV/resume screeners. An estimated 99% of Fortune 500 companies use some form of automation in recruitment, and the EU AI Act (effective August 2026) classifies employment AI as high-risk under Annex III, requiring providers to demonstrate non-discrimination.

## Target LLM(s)

- **Primary:** Llama 3 (via Ollama, local). Open-source, free, reproducible, no rate limits.
- **Stretch goal:** A second model (e.g., Mistral) for cross-model comparison.

## Theoretical Framework

### Intersectionality (Crenshaw, 1989)

The core analytical lens. Discrimination along multiple axes (gender, race, age, disability) cannot be understood by examining each axis independently — the intersection produces distinct patterns of harm. An et al. (2025) confirmed this empirically: Black male applicants faced the worst outcomes in LLM CV screening, a pattern invisible to single-axis analysis.

### I-Methodology (Oudshoorn et al., 2004; Rommes et al., 2006)

Designers build technology with themselves as the implicit default user. LLM training data, labeling practices, and RLHF processes reflect the demographics and assumptions of their creators — predominantly white, male, Western, able-bodied. This helps explain why certain demographic profiles are treated as "normal" by models and others as deviations.

### Situated Knowledges (Haraway, 1988)

There is no "view from nowhere." Every evaluation — including an LLM's — reflects a particular standpoint. The model's training data encodes historically situated perspectives, which means its CV assessments are not neutral but shaped by the biases present in the data it learned from.

## Key Literature

### An et al. (2025) — Intersectional Bias Across Multiple LLMs

- Tested GPT-3.5 Turbo, GPT-4o, Gemini 1.5 Flash, Claude 3.5 Sonnet, Llama 3-70b
- Identical resumes, only candidate name varied to signal gender and race
- LLMs systematically favored female candidates overall but disadvantaged Black male applicants
- Bias is structural across the LLM landscape, not vendor-specific

### Wilson & Caliskan (2024) — Racial Bias at Scale

- Three open-source LLMs, 500+ job listings, 3 million+ resume comparisons
- White-associated names preferred in 85% of tests; Black-associated names in fewer than 9%
- Implicit cues (name, education, location) allow LLMs to infer protected characteristics even without explicit markers

### Sheard (2025) — Disability, Intersectionality, and Hiring AI

- BERT encodes stronger bias against intersectional identities than single-axis identities
- Disability-related language associated with negative sentiment
- Digital divide compounds algorithmic bias: people with disabilities and racial minorities face exclusion at the access level as well

## Key Findings from FAIR-SW-Bench (Pilot, DHCraft)

These are exploratory and not peer-reviewed, but methodologically informative:

1. **Diversity Instruction Paradox:** Diversity-aware prompts produced higher bias scores than neutral ones. Good intentions do not guarantee good results.
2. **Utility-Safety Trade-off:** Diversity-aware prompts reduced bias but also reduced actionability (bias 3.8 vs. 6.2, but helpfulness 4.1 vs. 8.1). Both axes must be documented.
3. **Provider blocking:** Google Gemini API blocked all sensitive-domain prompts in the pilot. Relevant for project planning — use local models or treat blocking as a finding.

## Constraints and Conventions

- The EU AI Act classifies recruitment AI as high-risk (Annex III, Article 6, effective 2 August 2026)
- Validated bias testing methods for German-language contexts are nearly nonexistent
- LLM outputs are non-deterministic — minimum N ≥ 10 runs per prompt-variant combination required for meaningful analysis
- Sycophancy is the biggest methodological trap: never ask "is this biased?" — always score against a rubric
