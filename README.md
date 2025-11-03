# Mechanistic Interpretability: Analyzing Chain-of-Thought Reasoning

## What This Does

This project compares how two language models think differently when solving problems:

1. **Base Model**: Qwen 2.5 Math 1.5B - a standard model trained on mathematical reasoning
2. **Distilled Model**: DeepSeek-R1-Distill - fine-tuned to use explicit "thinking" tokens before answering

## The Key Question

**What actually happens inside the model when it "thinks"?**

By measuring **KL divergence** (how different the models' probability distributions are) at each token position, we can see:
- Where the models disagree most about what comes next
- Whether the "thinking region" (between `<think>` and `</think>` tags) causes fundamental behavioral changes
- If explicit reasoning changes how the model processes information

## What We Measure

- **KL Divergence**: How much the models' predictions differ at each token
- **Entropy**: How uncertain each model is about the next token
- **Log Probabilities**: How confident each model is about the actual next token
- **Thinking vs Non-Thinking**: Statistical comparison of model behavior inside and outside reasoning sections

## Why This Matters

Understanding how chain-of-thought prompting works at a mechanistic level helps us:
- Design better reasoning systems
- Understand if "thinking" is just surface-level formatting or causes deeper changes
- Identify where models actually diverge in their reasoning process

## Quick Start

Run the Colab notebook to:
1. Load both models
2. Generate a response with explicit reasoning
3. Visualize where the models differ
4. Analyze the statistics of model divergence

The result: Interactive visualizations showing exactly where and how much the models think differently.
