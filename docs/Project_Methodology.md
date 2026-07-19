# Project Methodology

This project benchmarked two state-of-the-art LLMs (anonymized as **Response A** and **Response B**) on a diverse set of 20 prompts.

## 1. Prompt Selection and Diversity

Prompts were selected to test different capabilities:
- **Technical (Coding/SQL/Regex)**: Focuses on syntax, logic, safety, and edge-case handling.
- **Education/Communication**: Emphasizes clarity, analogies, tone, and readability.
- **Business/Professional**: Looks at etiquette, professionalism, and constraint following.
- **Reasoning/Logic**: Tests mathematical, logic-based, and analytical abilities.

## 2. Evaluation Protocol

1. **Generation**: The prompt was run through both models under identical system instructions (temperature=0.7).
2. **Blinded Annotation**: The responses were anonymized as Response A and Response B.
3. **Scoring**: A human annotator graded both responses from 1 to 5 based on the eight core criteria.
4. **Data Aggregation**: Scores were summed to identify a winner, and findings were recorded.
