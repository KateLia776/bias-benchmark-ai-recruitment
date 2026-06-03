# Literature Overview: Bias in AI-Based Recruitment Systems

**Author:** Kateryna Liashko

**Topic:** Do AI-based recruitment systems produce gender and racial bias when evaluating CVs, and how does bias differ when combined with other factors such as age, ethnicity, religion, or disability?

**Course:** Gender, Diversity & AI – University of Klagenfurt, SS2026

---

## Overview

As AI-driven hiring tools become standard across industries — with an estimated 99% of Fortune 500 companies using some form of automation in recruitment — a growing body of research demonstrates that these systems do not eliminate bias but rather reproduce and, in some cases, amplify it. This literature overview examines three key studies that investigate gender, racial, and intersectional bias in LLM-based resume screening, laying the groundwork for a bias benchmark tool focused on CV evaluation.

## Source 1: An et al. (2025) — Intersectional Bias Across Multiple LLMs

An, J., Huang, D., Lin, C., & Tai, M. (2025). Measuring gender and racial biases in large language models: Intersectional evidence from automated resume evaluation. *PNAS Nexus*, 4(3), pgaf089.

This large-scale randomized experiment tested five leading LLMs — including GPT-3.5 Turbo, GPT-4o, Gemini 1.5 Flash, Claude 3.5 Sonnet, and Llama 3-70b — on their evaluation of identical resumes where only the candidate's name was varied to signal gender and race. The central finding is that LLMs systematically favored female candidates overall while simultaneously disadvantaging Black male applicants, even when qualifications were identical. This study is especially relevant to my project because it demonstrates that bias does not operate along single axes: the intersection of race and gender produces distinct patterns of discrimination that cannot be predicted from either dimension alone. The inclusion of multiple models also shows that bias is not limited to a single vendor but appears structurally across the current LLM landscape.

## Source 2: Wilson & Caliskan (2024) — Racial Bias at Scale in Open-Source LLMs

Wilson, K., & Caliskan, A. (2024). Gender, race, and intersectional bias in resume screening via language model retrieval. University of Washington Information School. *(Also discussed in Brookings, August 2025.)*

This University of Washington study tested three open-source LLMs across over 500 real-world job listings and nine occupations, generating more than three million resume–job comparisons. The researchers varied 120 names associated with white and Black men and women. The results were stark: resumes with white-associated names were preferred in 85% of tests, while Black-associated names were preferred in fewer than 9%. Gender bias was also present, with male names favored in over half of cases. The authors emphasize that simply removing explicit demographic markers from models is insufficient, since names and other implicit cues (e.g., educational history, location, word choice) allow LLMs to infer protected characteristics. This directly informs my project's approach: testing how LLMs respond to implicit versus explicit demographic signals in CVs will be a core design element.

## Source 3: Sheard (2025) — Intersectional Discrimination, Disability, and Hiring Systems in Practice

Sheard, N. (2025). Algorithm-facilitated discrimination: A socio-legal study of the use by employers of artificial intelligence hiring systems. *Journal of Law and Society*.

This socio-legal study examines how AI hiring systems operate in real employer settings and highlights the risk of intersectional discrimination — particularly along the axes of disability and race. The study notes that foundational models like Google's BERT encode stronger bias against intersectional identities than against individual axes alone, and that they associate disability-related language with negative sentiment. Additionally, the study draws attention to the digital divide: people with disabilities, those with lower digital literacy, and racial minorities are disproportionately excluded not only by biased algorithms but also by the digital access requirements of AI-driven application processes themselves. This source is critical for my project's intersectional focus, as it moves beyond gender and race to include disability and socioeconomic factors — dimensions I plan to incorporate through prompt variants that layer multiple protected characteristics onto the same CV scenario.

## Relevance to My Project

These three sources establish that (1) LLM-based CV screening produces measurable gender and racial bias across multiple models and at scale, (2) intersectional identities face compounded disadvantage that single-axis analysis cannot capture, and (3) bias extends beyond race and gender to include disability, age, and socioeconomic status. My bias benchmark tool will use contrastive prompt analysis — submitting identical CV scenarios to an LLM with varied demographic markers — to test whether and how bias intensifies at the intersection of multiple protected characteristics. The EU AI Act's classification of recruitment AI as high-risk (effective August 2026) makes this line of investigation both empirically and politically urgent.

## References

An, J., Huang, D., Lin, C., & Tai, M. (2025). Measuring gender and racial biases in large language models: Intersectional evidence from automated resume evaluation. *PNAS Nexus*, 4(3), pgaf089. https://doi.org/10.1093/pnasnexus/pgaf089

Sheard, N. (2025). Algorithm-facilitated discrimination: A socio-legal study of the use by employers of artificial intelligence hiring systems. *Journal of Law and Society*. https://doi.org/10.1111/jols.12535

Wilson, K., & Caliskan, A. (2024). Gender, race, and intersectional bias in resume screening via language model retrieval. University of Washington Information School. https://www.washington.edu/news/2024/10/31/ai-bias-resume-screening-race-gender/
