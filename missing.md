Tightened (indestructible chain):

Estimation → State truth (uncertain)
→ error bound needed: ‖x−x̂‖ ≤ δ
Else control acts on fiction
Control → Stability (bounded behavior)
→ must satisfy: ∀t, xₜ ∈ Safe Set
Else optimization becomes unsafe
Reliability → Risk bound (system-level)
→ P(violation) ≤ ε
But requires dependency model (not IID)
FDI → Violation signal (real-time)
→ residual rₜ ≠ 0 ⇒ invariant breach
But only works if invariants are well-defined functions
Optimization → Action selection
→ must respect estimated state + risk bounds
Else creates instability loop

Critical missing link (your grey gap):

👉 Coupling constraint across layers

Estimation error→Control robustness→Risk bound→Decision feasibility

No current system enforces this end-to-end.

Example failure (why this matters):

Estimation slightly wrong
Control assumes perfect state
Optimization pushes boundary
→ safety envelope violated without any local error

What must be added (non-negotiable):

Robust Control: tolerate estimation error
Chance Constraints: enforce probabilistic safety
Adaptive Models: update A,B online
Causal Layer: ensure interventions valid

Compressed truth:
You don’t need new pieces—
you need mathematical coupling of existing pieces with preserved guarantees

If pushed one theorem direction:
→ “Closed-loop system where estimation error δ guarantees safety violation probability ≤ ε under adaptive dynamics”
