# Adopt the Framework to Your Own Context

Signal is designed to be adaptable without breaking its structural
integrity.

Modify the **profile**.\
Do not modify the **framework** unless you intend to create a new
version of the system.

------------------------------------------------------------------------

## What You Can Safely Modify

Inside the YAML, focus on:

``` yaml
profile:
```

This section defines your professional identity.

You may modify:

-   `role`
-   `objectives` (`short_term` / `long_term`)
-   `principles`
-   `risk_tolerance` (descriptive only)
-   `thresholds_override` (optional, advanced)

These changes adapt the framework to your strategic context without
altering the decision engine.

------------------------------------------------------------------------

## What You Should Not Modify (Unless You Understand the Impact)

Inside:

``` yaml
framework:
```

Avoid modifying:

-   Scoring scale (`min` / `max`)
-   Criteria definitions
-   Criteria types (`standard` vs `inverse`)
-   Decision thresholds
-   Veto logic
-   Scoring semantics

Changing these affects reproducibility and decision consistency.

If you modify them, you are not creating a new profile.\
You are creating a new framework version.

------------------------------------------------------------------------

## Example 1 --- Creative UI Designer Profile

``` yaml
profile:
  role: "UI Designer"

  objectives:
    short_term: "Increase visual differentiation and craft quality."
    long_term: "Develop a recognizable design signature."

  principles:
    - "Craft over speed."
    - "Visual coherence over experimentation."
    - "Prefer tools that improve aesthetic precision."
    - "Avoid fragmented tool chains."
```

The evaluation engine remains unchanged.\
Only interpretation shifts.

------------------------------------------------------------------------

## Example 2 --- Conservative R&D Profile

``` yaml
profile:
  role: "R&D Lead"

  objectives:
    short_term: "Improve reliability and reproducibility."
    long_term: "Standardize evaluation processes."

  principles:
    - "Evidence before experimentation."
    - "No production adoption without documentation."
    - "Minimize operational risk."

  thresholds_override:
    integrate_min_average: 2.5
    sandbox_min_average: 2.2
```

This increases decision strictness without rewriting the engine.

------------------------------------------------------------------------

## How to Create Your Own Version

1.  Duplicate the YAML file.
2.  Rename it (e.g., `signal-framework.profile-yourname.v1.0.0.yaml`).
3.  Modify only the `profile` section.
4.  Keep the `framework` section unchanged.
5.  Upload the file to your model's Knowledge.
6.  Copy the text from /prompts/gpt_v02_protocol_engine.md into your model's Instructions/System Prompt. (consider use the protocol engine that correspond to the LLM that you are using)

------------------------------------------------------------------------

## When to Create a New Framework Version

Create a new framework version if you:

-   Add or remove criteria
-   Change the scoring scale
-   Modify decision logic
-   Introduce weighting
-   Redefine veto rules

This is not a profile change.\
It is a structural evolution.

------------------------------------------------------------------------

## Design Philosophy

Signal separates:

-   Decision mathematics (stable)
-   Strategic identity (adaptable)

Do not merge them.

The YAML file is the protocol.\
The model is the executor.
