Where transfer actually holds (indestructible cores):

State Estimation (Kalman-type) → Observability

x
^
t
	​

=A
x
^
t−1
	​

+Bu
t
	​

+K(y
t
	​

−C
x
^
t−1
	​

)
Use: reconstruct hidden system state from noisy logs
Gap: extend to non-stationary org/data systems
Feedback Stability → Governance Control
x
t+1
	​

=Ax
t
	​

+Bu
t
	​


Use: keep system inside safety envelope
Gap: A,B not fixed → need adaptive + causal control
Reliability Engineering → Probabilistic Guarantees
Classical: failure rates, redundancy
Use: bound risk in pipelines/org decisions
Gap: dependencies ≠ independent components
Fault Detection & Isolation (FDI) → Runtime Monitoring
Residuals detect violations
Use: invariant breach detection in real time
Gap: defining invariants in abstract systems
Trajectory Optimization → Decision Systems
max
u
t
	​

	​

∑
t
	​

U(x
t
	​

,u
t
	​

)s.t. x
t+1
	​

=f(x
t
	​

,u
t
	​

),C(x
t
	​

)≤0
Use: constrained decision-making
Gap: unknown dynamics + multi-agent conflict

True grey fusion (where almost no work is solid):

Kalman + Causality → state estimation with interventions
Control + Formal Proof → stability provably maintained at runtime
FDI + Governance → invariant violation = organizational fault model
Trajectory Optimization + Multi-Agent → globally safe equilibrium
