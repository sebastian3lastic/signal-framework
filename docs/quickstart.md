# Quickstart

This guide shows how to execute the Signal Decision Framework using a Large Language Model (GPT, Gemini, Claude, etc.).

No coding required.

---

## Step 1 — Download the Protocol

Download:

- `signal-framework.protocol.v1.0.0.yaml`
- `System Prompt - GPT_v02.md` (or equivalent for your model)

The YAML file is the source of truth.
The System Prompt is the execution interpreter.

---

## Step 2 — Create a Custom GPT (or equivalent)

In your LLM platform:

1. Create a new custom assistant.
2. Paste the System Prompt into the “Instructions” field.
3. Upload the YAML protocol file into Knowledge (or equivalent document storage).
4. Enable Web Search capability.

The model should not require the user to paste the YAML manually.
It must load it from Knowledge.

---

## Step 3 — Run Your First Evaluation

Example:

> Evaluate https://cursor.com

The assistant should:

- Load the protocol from Knowledge
- Perform web search (because a URL is provided)
- Score using the defined rubric
- Apply numeric thresholds strictly
- Enforce veto rules if necessary
- Return a structured output

---

## Example Output (Simplified)

🔎 Source validated via web search (current public information reviewed).

📊 Evaluation (Based on loaded protocol)

Strategic Fit: 2 — Contextual / Moderate  
Decision Clarity: 2 — Contextual / Moderate  
Output Quality: 3 — Clearly Positive  
Repeatable Speed: 3 — Clearly Positive  
Reusable Assets: 2 — Contextual / Moderate  
Cognitive Load: 2 — Moderate Risk  
Lock-in Risk: 2 — Moderate Risk  
Privacy / Reputation Risk: 3 — Low Risk  

📈 Average: 2.38  

⚠️ Decision: Sandbox  

🧠 Rationale:  
The tool improves repeatable speed and output quality but does not strongly reinforce long-term strategic positioning. Lock-in risk is moderate, suggesting controlled experimentation rather than integration.

🧪 Suggested Experiment:
- Hypothesis: Cursor improves coding iteration speed without increasing cognitive fragmentation.
- Tasks: Implement one real project module using Cursor; compare to baseline workflow.
- Metrics: Time-to-completion, number of manual corrections, integration friction.

---

## Step 4 — Interpret the Decision

Signal does not tell you what to like.

It tells you:

- Whether to Integrate
- Whether to Sandbox
- Whether to Discard

The experiment section defines safe exploration boundaries.

---

## Common Mistakes

- Modifying thresholds in the prompt instead of the YAML.
- Forgetting to enable web search.
- Allowing the model to infer thresholds from descriptive fields.
- Adding criteria directly in the prompt instead of the protocol.

---

## Minimal Rule

If you change behavior, change the YAML.

Never the math in the prompt.