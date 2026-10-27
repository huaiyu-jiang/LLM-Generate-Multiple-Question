# Does Question Ambiguity Explain LLM Errors on Multiple-Choice Questions?

An evaluation of 8 LLMs on 50 multiple-choice questions, studying whether the questions models get wrong are also the ones humans judge ambiguous.

## Method
1. Clean the question bank (strip HTML, drop image-based questions) and sample 50 questions
2. Query 8 models through the OpenRouter API: GPT-3.5 Turbo, GPT-4, Claude 3 Opus, Gemini Pro, Llama 2 70B Chat, Mistral 7B Instruct (two providers), and Mixtral 8x7B Instruct
3. Hand-grade each response for correctness and whether the question is ambiguous, then re-grade after revising ambiguous questions
4. Compare per-model accuracy before and after revision, and test the correlation between per-question accuracy and ambiguity (Spearman)

## Layout
- `unambiguous_revised.ipynb`: preprocessing, API calls, and analysis
- `results/`: raw model responses
- `checked/`: graded responses per model

## Run
```bash
export OPENROUTER_API_KEY=...
jupyter notebook unambiguous_revised.ipynb
```
