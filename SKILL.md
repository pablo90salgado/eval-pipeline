---
name: eval-pipeline
description: |
  Designs and runs evaluation pipelines for AI models and agents.
  Use this skill when the user says: "evaluate this model", "measure response quality",
  "compare two prompts", "build a benchmark", "test the agent against real cases",
  "calculate accuracy", "how good is my prompt", "eval dataset", "measure my agent",
  "A/B test prompts", "score the outputs". Generates evaluation datasets, defines
  relevant metrics and produces comparison reports between versions.
---

# Eval Pipeline

Skill for measuring and comparing AI agent and model performance systematically.

## When to use this skill

- You want to know if a prompt change actually improved results
- You need to compare two versions of an agent
- You want to catch regressions before deploying changes
- You need to report on agent quality with concrete metrics
- You are building a dataset to fine-tune or test a model

## Evaluation process

### 1. Define what you are measuring

Pick the right metric for your task:

- **Accuracy** — correct vs incorrect answers on factual tasks
- **Consistency** — same input produces same output across runs
- **Format compliance** — output matches expected structure
- **Task completion** — agent completed the goal vs failed
- **Latency** — time to complete the task

### 2. Build the evaluation dataset

A good eval dataset has:
- Minimum 20 examples for meaningful signal
- Mix of easy, medium and hard cases
- Known ground truth for each example
- Edge cases and adversarial inputs
- Real examples from production when possible

### 3. Run the evaluation
for each example in dataset:
  - run agent with example input
  - compare output to ground truth
  - score with chosen metric
  - log result

aggregate scores
compare against baseline

### 4. Interpret results

- Score improvement > 5% = meaningful improvement
- Score drop > 2% = potential regression, investigate
- High variance across runs = agent is unstable, fix prompt
- Failure clustering = systematic issue, not random noise

## Prompt comparison template

When comparing prompt A vs prompt B:
1. Run both on the same dataset
2. Use the same judge (model or human) for scoring
3. Report win/loss/tie counts, not just averages
4. Check if improvements hold across difficulty levels

## Compatibility

Claude Code, Cursor, Windsurf, Cline, Roo and any agent compatible with the Agent Skills standard.
