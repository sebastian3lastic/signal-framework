# Signal Framework

Signal Framework is a structured decision protocol for evaluating
professional tools, resources, and emerging trends in high-change
environments.

It separates judgment from impulse.

------------------------------------------------------------------------

## Purpose

Professionals operating in fast-moving domains (AI, design, product,
strategy) are constantly exposed to new tools and ideas.

Signal exists to:

-   Reduce reactive adoption
-   Clarify trade-offs
-   Make opportunity cost visible
-   Enforce consistent decision logic

It does not eliminate uncertainty. It introduces structure.

------------------------------------------------------------------------

## Two Ways to Use Signal

### 1. Public GPT (Quick Test)

The public GPT version allows you to evaluate tools immediately using a
fixed rubric.

-   No setup required
-   Instant scoring
-   Good for validating the need

This version is opinionated and simplified.

------------------------------------------------------------------------

### 2. Protocol Engine (Full Control)

This repository contains the full protocol-driven version.

It is based on:

-   A YAML protocol file (source of truth)
-   Strict scoring logic
-   Defined thresholds
-   Absolute veto rules
-   Versioned governance

The model (GPT, Gemini, Claude, etc.) acts only as an executor. All
decision logic lives in the YAML.

------------------------------------------------------------------------

## How It Works

1.  The protocol defines:

    -   Criteria
    -   Scale
    -   Thresholds
    -   Veto rules
    -   Source validation policy

2.  The model loads the protocol.

3.  Each resource is scored across all criteria.

4.  The average is calculated.

5.  Thresholds determine:

    -   Integrate
    -   Sandbox
    -   Discard

6.  Veto rules override the average if structural risk is unacceptable.

No threshold inference is allowed. Numeric values in the protocol are
absolute.

------------------------------------------------------------------------

## Repository Structure

protocol/ signal-framework.protocol.v1.0.0.yaml

prompts/ gpt_public_v1.md gpt_protocol_engine_v1.md

docs/ overview.md quickstart.md adopt_your_own.md governance.md

------------------------------------------------------------------------

## Getting Started

To execute the full protocol-driven version:

1.  Upload the YAML file to your model's Knowledge.
2.  Paste the protocol engine prompt into Instructions.
3.  Enable web search.
4.  Run an evaluation.

See docs/quickstart.md for detailed instructions.

------------------------------------------------------------------------

## Adaptation

You can adapt the framework by modifying the `profile` section of the
YAML.

Do not modify the `framework` section unless you intend to create a new
version of the system.

See docs/adopt_your_own.md.

------------------------------------------------------------------------

## Versioning

Signal follows semantic versioning.

Structural changes to the framework require a MAJOR version increment.
Profile changes do not.

See docs/governance.md.

------------------------------------------------------------------------

## Philosophy

Direction over novelty.

Reusable systems over temporary efficiency.

Structure over impulse.

------------------------------------------------------------------------

## License

MIT License
