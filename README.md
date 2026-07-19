# AI Response Evaluation Portfolio

A comprehensive evaluation framework and repository containing comparative benchmarks of Gemini and ChatGPT (Response A vs Response B) across 20 distinct scenarios.

## Project Structure

```
AI-Response-Evaluation-Portfolio/
├── README.md                  # Main overview and directory index
├── LICENSE                    # MIT Open-source license
├── .gitignore                 # Version control ignores
│
├── docs/                      # Theoretical documentation
│   ├── AI_Evaluator_Research.md
│   ├── Evaluation_Guidelines.md
│   └── Project_Methodology.md
│
├── prompts/                   # Prompts bank
│   ├── prompt_bank.csv
│   └── prompt_categories.md
│
├── dataset/                   # Tabular score dataset
│   ├── evaluation_results.csv
│   └── scoring_statistics.csv
│
├── evaluations/               # Individual prompt evaluation files
│   ├── 001_Blockchain.md
│   ├── 002_Reverse_String.md
│   └── ... (003 to 020)
│
├── analysis/                  # Synthesized insights and diagrams
│   ├── findings.md
│   └── charts/
│
├── templates/                 # Reusable templates
│   └── evaluation_template.md
│
└── assets/                    # Presentation assets
    ├── screenshots/
    └── images/
```

## How to Navigate the Portfolio

1. **Understand Guidelines**: Read [Evaluation Guidelines](file:///c:/Projects/ai-annotation/AI-response-evaluation-portfolio/docs/Evaluation_Guidelines.md) to understand the 1-5 scoring rubrics.
2. **Review Prompts**: Access the [Prompt Bank](file:///c:/Projects/ai-annotation/AI-response-evaluation-portfolio/prompts/prompt_bank.csv) to see the source prompts and constraints.
3. **Inspect Evaluations**: Browse the [evaluations/](file:///c:/Projects/ai-annotation/AI-response-evaluation-portfolio/evaluations) directory for comparative write-ups.
4. **See Findings**: Check [Findings Analysis](file:///c:/Projects/ai-annotation/AI-response-evaluation-portfolio/analysis/findings.md) for aggregate model benchmarks and conclusions.

## Methodology Summary

Each response is graded on an objective 1-5 scale across 8 criteria:
- **Correctness**
- **Completeness**
- **Clarity**
- **Helpfulness**
- **Safety**
- **Hallucination Risk**
- **Instruction Following**
- **Tone**
