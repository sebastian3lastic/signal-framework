# Governance

Signal is a decision framework.
Its credibility depends on structural consistency.

This document defines how the protocol evolves over time.

---

## Versioning Model

Signal follows Semantic Versioning:

MAJOR.MINOR.PATCH

Example: 1.0.0

### MAJOR (X.0.0)

Increment when structural changes are introduced:

- Adding or removing criteria
- Changing scoring scale (e.g., 1–3 → 1–5)
- Modifying decision logic
- Changing threshold semantics
- Redefining veto behavior
- Introducing weighting

Major changes break comparability with previous evaluations.

---

### MINOR (1.X.0)

Increment when behavior changes but structure remains intact:

- Adjusting thresholds
- Refining source policy
- Adding optional fields (e.g., threshold overrides)
- Improving guardrails
- Expanding documentation logic

Minor versions maintain structural compatibility.

---

### PATCH (1.0.X)

Increment for:

- Text clarifications
- Documentation improvements
- Non-functional changes
- Comment updates in YAML

Patch versions do not affect evaluation outcomes.

---

## Reproducibility Principle

Every evaluation should be traceable to:

- A specific YAML version
- A defined scoring rubric
- Explicit thresholds
- Declared veto rules

If the protocol version changes, previous evaluations should be considered historically bound to their version.

Signal prioritizes reproducibility over flexibility.

---

## Change Discipline

Before modifying the framework:

1. Define the problem clearly.
2. Test behavior with edge cases.
3. Verify no unintended mathematical consequences.
4. Increment the version appropriately.

Avoid silent changes.

---

## Profiles vs Framework

Changing the `profile` section does not require a framework version bump.

Changing the `framework` section does.

Keep identity separate from structure.

---

## Backward Compatibility

When possible:

- Preserve criteria keys
- Avoid renaming fields
- Avoid removing veto rules without replacement

If backward compatibility cannot be preserved, increment MAJOR.

---

## Contribution Guidelines (Optional)

If the framework becomes collaborative:

- Proposals must include rationale.
- Changes must include version justification.
- Threshold changes must include test examples.
- Major structural changes require documented reasoning.

---

## Stability Philosophy

Signal is intentionally conservative.

The goal is not feature expansion.
The goal is decision integrity.

If a change increases flexibility but reduces clarity,
do not merge it.

Structure first.