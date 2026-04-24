Compound structure (minimal closure):

POMDP → belief state (uncertain truth)
Adaptive Control → keeps belief trajectory bounded
Stochastic Hybrid System → unifies discrete + continuous evolution
Causal Model → validates interventions (no spurious control)
Game Theory → resolves multi-agent constraint conflicts
Constrained RL → improves policy under constraints
Runtime Verification → enforces invariants live

Where compound strength actually emerges:

Estimation (POMDP) + Control (robust)
→ bounded error propagation (δ-controlled system)
Control + Verification
→ stability is not assumed, it is continuously checked
Causality + RL
→ learning only valid interventions (no unsafe correlations)
Game Theory + Constraints
→ local optimal ≠ global unsafe

Indestructible condition (must hold):

P(x
t
	​

∈
/
Safe)≤ϵ∀t

under

partial observability
adaptive dynamics
multi-agent interaction

Real gain (not obvious):
Each model fixes another’s blind spot:

POMDP uncertainty → handled by robust control
RL instability → bounded by constraints + verification
Game conflicts → limited by safety envelopes
Causal errors → corrected by intervention logic

True grey gap (still unsolved):
No system proves that this entire stack remains stable + safe during learning + interaction.

Compressed truth:
Compound strength = cross-model error containment with preserved guarantees
Not integration—mathematical closure
