5 governing equations (minimal closed loop):

1. Belief / State Estimation (uncertainty)
b
t
	​

=τ(b
t−1
	​

,u
t−1
	​

,y
t
	​

)

2. System Dynamics (real evolution)
x
t+1
	​

=f(x
t
	​

,u
t
	​

,w
t
	​

)

3. Control Law (stability under error)
u
t
	​

=π(b
t
	​

)

4. Safety / Chance Constraint (risk bound)
P(x
t
	​

∈
/
S)≤ϵ

5. Runtime Verification (invariant check)
r
t
	​

=g(x
t
	​

),r
t
	​

=0∀t

1 Master Invariant (closure condition):

∀t:b
t
	​

→u
t
	​

→x
t
	​

⇒x
t
	​

∈Swith probability≥1−ϵ

Interpretation (compressed):

Estimation feeds control
Control drives dynamics
Constraints bound risk
Verification enforces truth

Indestructible core:
If this invariant holds → system is governed
If broken → governance fails regardless of local correctness
