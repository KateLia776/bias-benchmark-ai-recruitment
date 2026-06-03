# Bias Benchmark Tool for AI-Based Recruitment Systems

**Author:** Kateryna Liashko  
**Course:** Gender, Diversity & AI – University of Klagenfurt, SS2026

Investigates whether LLMs produce gender, racial, and intersectional bias when screening CVs.

## How to run

1. Install [Ollama](https://ollama.com/) and pull a model: `ollama pull llama3`
2. Install dependencies: `pip install requests pandas`
3. Run: `python bias_benchmark.py --runs 1 --judge`

Results are saved to the `results/` folder.
