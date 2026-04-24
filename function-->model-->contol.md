Link the two stacks = “function → model → role” (closed mapping):

State Estimation ↔ POMDP / Bayesian / Causal
→ serves: observability under uncertainty
(hidden state reconstruction + belief update)
Feedback Control ↔ Robust / Adaptive Control
→ serves: stability under drift
(keeps system inside safety envelope despite model error)
Reliability ↔ Stochastic Hybrid Systems
→ serves: risk modeling in mixed domains
(dependencies + discrete/continuous failures)
FDI (Residuals) ↔ Runtime Verification / Temporal Logic
→ serves: real-time invariant enforcement
(detect + act on violations continuously)
Trajectory Optimization ↔ Constrained RL / Control Optimization
→ serves: decision-making under constraints
(optimal actions within safety limits)
Multi-Agent Reality (implicit gap) ↔ Game Theory
→ serves: conflict resolution + global safety
(local vs system-wide constraints)
Causal Gap (implicit) ↔ Causal Models
→ serves: correct intervention logic
(prevents unsafe cause-effect assumptions)

Cross-links (where strength actually comes):

Estimation → Control → Optimization
→ decision uses corrected state + bounded dynamics
Verification → Control
→ violations trigger corrective action
Causality → RL / Optimization
→ learning only valid interventions
Game Theory → Constraints
→ multi-agent safety envelope holds

Compressed map:

See system → (Estimation / POMDP)
Keep stable → (Control)
Decide safely → (Optimization / RL)
Prove & enforce → (Verification / FDI)
Handle reality → (Hybrid + Probabilistic)
Handle interaction → (Game Theory + Causality)

Indestructible insight:
Each pair serves one invariant of governance:
visibility, stability, safety, correctness, coordination
