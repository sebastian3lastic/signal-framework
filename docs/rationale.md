# Signal Framework --- Rationale

This document explains the structural decisions behind Signal
Framework.
It clarifies why certain design choices were made, what alternatives
were considered, and what trade-offs they imply.

Signal is not designed to eliminate uncertainty.
It is designed to make trade-offs explicit and decisions reproducible.

---

## 1. Why a 1--3 Rubric instead of 1--5 or 1--10?

**Decision:**
Use a 3-point scoring scale.

**Why:**
A 1--3 scale forces directional judgment: Negative, Contextual, or
Clearly positive.

It reduces false precision and discourages cosmetic scoring differences
(e.g., debating between 7 and 8).

**Why not 1--5 or 1--10:**
Larger scales create the illusion of accuracy without improving decision
quality. They increase variance between sessions and evaluators.

**Trade-off:**
Less numerical granularity.

**Mitigation:**
Nuance is captured in the rationale and in sandbox experiments---not in
extra numbers.

---

## 2. Why Standard vs Inverse (risk-based) criteria?

**Decision:**
Explicitly separate positive criteria from inverse (risk-based)
criteria.

**Why:**
Some dimensions represent opportunity (e.g., Strategic Fit), while
others represent structural risk (e.g., Lock-in Risk). Treating them
identically hides asymmetry.

**Why not treat all criteria equally:**
A simple average can obscure critical risks. A high average may still
contain a severe structural vulnerability.

**Trade-off:**
Slightly more complexity in scoring logic.

**Mitigation:**
Clear labeling and explicit veto rules.

---

## 3. Why explicit numerical thresholds?

**Decision:**
Use predefined numerical thresholds for Integrate, Sandbox, and Discard.

**Why:**
Thresholds prevent post-hoc reinterpretation. They externalize the
decision boundary instead of allowing subjective re-framing.

**Why not rely on qualitative interpretation:**
Without thresholds, decisions drift toward narrative justification
rather than structural consistency.

**Trade-off:**
Reduced flexibility in borderline cases.

**Mitigation:**
A Sandbox category exists to absorb ambiguity without forcing premature
production adoption.
Sandbox means a time-boxed experiment with defined tasks and measurable
criteria, without production integration.

---

## 4. Why absolute veto rules?

**Decision:**
Certain criteria (e.g., Lock-in Risk, Privacy/Reputation Risk) can
override the average score.

**Why:**
Some risks are structural and non-compensatory. A strong strategic fit
does not neutralize a critical lock-in or privacy exposure.

**Why not allow weighted averaging:**
Weighted averages can normalize unacceptable risk if other scores are
high.

**Trade-off:**
More conservative outcomes.

**Mitigation:**
Structural risks are made explicit so that experimentation and
production decisions are clearly separated.

---

## 5. Why require a 6-Month objective?

**Decision:**
Every evaluation must be anchored to a defined 6-month objective.

**Why:**
Tools and trends only make sense relative to direction. Without a
time-bound objective, novelty bias dominates decision-making.

**Why not allow general goals:**
Vague intentions allow almost any tool to appear strategically
justified.

**Trade-off:**
Users without clarity may feel blocked.

**Mitigation:**
If a formal 6-month objective is unavailable, a defined operational
focus may substitute.
Example: "Become employable as a junior PM within 6 months." Tools that
do not clearly move that objective become Sandbox or Discard.

---

## 6. Why YAML as protocol format?

**Decision:**
Use YAML as the structural definition of criteria, thresholds, and veto
rules.

**Why:**
YAML enforces explicit structure while remaining readable. It separates
decision logic from model behavior.

**Why not rely solely on prompt text:**
Plain-language prompts are interpretive and drift-prone. Structured
configuration reduces ambiguity.

**Trade-off:**
Requires minimal technical literacy.

**Mitigation:**
The public GPT can be used as a testing environment before formalizing a
YAML protocol.

---

## 7. Why source validation via Web Search?

**Decision:**
When evaluating tools or links, current public information should be
retrieved via web search.

**Why:**
Model memory may be outdated or incomplete. Decisions should reflect
present-state reality.

**Why not rely on model knowledge alone:**
Static knowledge increases the risk of outdated or fabricated
information influencing decisions.

**Trade-off:**
Dependency on search availability.

**Mitigation:**
If search is unavailable, the model must acknowledge uncertainty
explicitly.

---

## 8. Is Signal Deterministic?

No.

Signal Framework operates on probabilistic LLMs.
It does not guarantee identical outputs across sessions.

Its purpose is not determinism.
Its purpose is structural consistency.

Reasoning phrasing may vary between sessions.
However, when inputs, protocol, and sources remain the same, the
decision logic (thresholds and veto rules) should remain stable.

---

## Final Position

Signal Framework is not:

-   A predictor
-   A recommender
-   A scoring game

It is:

A structured decision protocol designed to reduce reactive adoption and
make trade-offs explicit in high-change environments.
