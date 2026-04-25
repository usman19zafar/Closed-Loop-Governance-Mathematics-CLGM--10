\documentclass[11pt]{article}

\usepackage{amsmath, amssymb, amsthm}
\usepackage{bbm}
\usepackage{mathrsfs}

\begin{document}

\section{Definition-Style Formalism (Refined and Closed)}


\subsection{Definition 1 (State-Measure Space).}
A state-measure structure is a triple $(X,\mathcal{B}(X),\mu)$ where
$X$ is a Polish space, $\mathcal{B}(X)$ is its Borel $\sigma$-algebra, and
$\mu \in \mathcal{P}(X)$ is a probability measure on $(X,\mathcal{B}(X))$.

\vspace{1em}

\textbf{Base Spaces}
Let $X$ and $Y$ be Polish spaces with Borel $\sigma$-algebras $\mathcal{F}_X=\mathcal{B}(X)$ and $\mathcal{F}_Y=\mathcal{B}(Y)$. Let $\mathcal{P}(X)$ denote the set of probability measures on $X$ endowed with the weak topology, so $(\mathcal{P}(X),\mathcal{B}(\mathcal{P}(X)))$ is Polish.

\vspace{1em}

\textbf{Explanation:} A state space is just the set of all possible situations the system can be in. We require it to be Polish so that probability theory works nicely, meaning the space is complete, has no “holes,” and has a countable structure. A probability measure μ tells us how likely each state is. Imagine a big box with every place the system can be. We also have a rule that says how likely we are to be in each place. The box is clean and tidy so math works.

\subsection{Topological and Measurable Spaces}

\textbf{State Space.}


\[
X \text{ is Polish}, \qquad \mathcal{F}_X = \mathcal{B}(X).
\]



\textit{Discussion:}
The choice of a Polish space ensures separability and completeness, which 
are critical for applying probability theory and stochastic analysis. Using 
the Borel $\sigma$-algebra guarantees compatibility with standard 
measure-theoretic tools. This allows existence results (e.g., probability 
measures, kernels) to hold without pathological exceptions.


\vspace{2em}

\textbf{Belief Space.}


\[
\mathcal{P}(X) \text{ with the weak topology is Polish}, 
\qquad \mathcal{F}_{\mathcal{P}(X)} = \mathcal{B}(\mathcal{P}(X)).
\]



\textit{Discussion:}
Beliefs are modeled as probability measures over the state space. The weak 
topology ensures convergence of distributions is well-defined. Making this 
space Polish allows fixed-point theorems and learning dynamics to be applied 
later.

\textbf{Observation Space.}


\[
Y \text{ is Polish}, \qquad \mathcal{F}_Y = \mathcal{B}(Y).
\]



\textit{Discussion:}
Observations are the only interface between the agent and the hidden state. 
A Polish structure ensures that observation kernels are well-defined and 
measurable.

\vspace{1em}

\textbf{Agents and Actions.}

Let


\[
I = \{1,\dots,n\}.
\]



For each agent $i \in I$:


\[
A^{(i)} \text{ is Polish}, \qquad \mathcal{F}_{A^{(i)}} = \mathcal{B}(A^{(i)}).
\]



Joint action space:


\[
A = \prod_{i \in I} A^{(i)}, 
\qquad \mathcal{F}_A = \mathcal{B}(A).
\]



\textit{Discussion:}
The product structure encodes multi-agent interaction rigorously. Polish 
structure ensures the joint space remains well-behaved, enabling 
game-theoretic and control-theoretic analysis.

\vspace{2em}
\textbf{Operator Space.}

We assume either:
\begin{itemize}
    \item (Strong) $\mathcal{T}$ is Polish, or
    \item (Minimal) $\mathcal{T}$ is standard Borel
\end{itemize}
with


\[
\mathcal{F}_{\mathcal{T}} = \mathcal{B}(\mathcal{T}).
\]



\textit{Discussion:}
Operators represent system evolution. Restricting $\mathcal{T}$ to Polish or 
standard Borel spaces prevents pathological transformations and ensures 
measurability of operator-valued processes.

\vspace{1em}

\textbf{Full System Space.}


\[
Z = X \times \mathcal{P}(X) \times A \times \mathcal{T} \times \mathcal{P}(X).
\]



Then:


\[
Z \text{ is Polish (or standard Borel)}, 
\qquad \mathcal{F}_Z = \mathcal{B}(Z).
\]



\textit{Discussion:}
This product space unifies all components into a single mathematical object. 
This closure is essential: every system configuration is now an element of a 
well-defined measurable space.

\textbf{Safety Set.}


\[
S \in \mathcal{F}_X.
\]



\textit{Discussion:}
Safety is defined as a measurable subset of the state space. This allows 
probabilistic reasoning about violations and supports later invariance 
definitions.


\section{Definition: Belief Space}
The belief space is the measurable Polish space


\[
(\mathcal{P}(X),\mathcal{B}(\mathcal{P}(X)))
\]


endowed with the weak topology, where $\mathcal{P}(X)$ denotes all probability measures on $X$.

\vspace{1em}

{Agents and Actions.}
Let $I={1,\dots,n}$ be a finite or countable index set. For each $i\in I$, let $(A^{(i)},\mathcal{F}{A^{(i)}})$ be Polish with $\mathcal{F}{A^{(i)}}=\mathcal{B}(A^{(i)})$. The joint action space is $A=\prod_{i\in I} A^{(i)}$ with $\mathcal{F}_A=\mathcal{B}(A)$.
\vspace{1em}

\textbf{Explanation Belief Space}
A belief is a probability distribution over states — what an agent thinks the true state might be. The weak topology makes sure beliefs behave well when they change or update. This space is also Polish so learning and convergence theorems apply. It’s like guessing where something is, and giving each guess a number. The guessing rules are neat so we can update them without breaking anything.

\subsection{Probability Space and Filtrations}

\textbf{Global Probability Space.}


\[
(\Omega, \mathcal{F}, P).
\]



\textbf{Time Index.}


\[
t \in \mathbb{N}_0.
\]



\textbf{Full Filtration (Latent).}


\[
\mathcal{F}_t 
= \sigma(x_0,\dots,x_t,\; y_0,\dots,y_t,\; a_0,\dots,a_{t-1}).
\]



\textbf{Observation Filtration.}


\[
\mathcal{F}_t^{\mathrm{obs}}
= \sigma(y_0,\dots,y_t,\; a_0,\dots,a_{t-1}).
\]



\textit{Discussion:}
The separation of filtrations is critical. The latent filtration contains the 
true system state, while the observation filtration reflects what agents can 
access. This enforces partial observability rigorously and prevents 
information leakage.


\section{Definition:3 Agent and Action Structure}
Let $I=\{1,\dots,n\}$ be a finite or countable index set.
For each $i \in I$, $(A^{(i)},\mathcal{B}(A^{(i)}))$ is a Polish space.

The joint action space is defined as


\[
A = \prod_{i \in I} A^{(i)}, \qquad 
\mathcal{B}(A) = \bigotimes_{i \in I} \mathcal{B}(A^{(i)}).
\]

\vspace{2em}

Agents, Actions, and Operator Space
There are multiple agents, each with their own action space.
The joint action space is the product of all individual action spaces. The operator space contains all allowed system‑evolution rules each operator maps the whole system state into a new one while preserving probability structure. Many players can do things. All their choices together make one big choice.There’s also a “magic machine” that takes the whole system and moves it to the next step without breaking the rules.

\vspace{1em}

\textbf{Definition 3 (Operator Space).}
\vspace{1em}
Let $T$ be a Polish (or standard Borel) space with $\mathcal{F}_T=\mathcal{B}(T)$ such that

T⊂{τ:Z→Z∣τ is Borel measurable and maps measure components into P(X)}.

\subsection{Random Processes and Measures}

\textbf{Processes.}


\[
x_t : \Omega \to X, \qquad
y_t : \Omega \to Y, \qquad
a_t : \Omega \to A.
\]

\vspace{1em}

\textbf{True Law and Belief.}


\[
\mu_t = \mathcal{L}(x_t) \in \mathcal{P}(X), 
\qquad b_t \in \mathcal{P}(X).
\]



\textit{Discussion:}
The distinction between $\mu_t$ and $b_t$ separates objective system 
behavior from subjective belief. This is essential for modeling learning and 
uncertainty.

\vspace{1em}

\textbf{Observation Kernel.}


\[
O : X \times \mathcal{F}_Y \to [0,1].
\]



\textit{Discussion:}
This kernel formalizes the probabilistic mapping from hidden states to 
observations. It is the foundation of partial observability.

\textbf{Adaptation.}
\begin{itemize}
    \item $x_t$ is $\mathcal{F}_t$-measurable,
    \item $y_t, a_t, b_t, T_t$ are $\mathcal{F}_t^{\mathrm{obs}}$-measurable.
\end{itemize}

\textit{Discussion:}
This ensures that decisions depend only on available information, preserving 
causal consistency.



\section{Definition:4 (Filtered Probability Space and Information Structure).}
Let $(\Omega,\mathcal{F},P)$ be a probability space with time index $t \in \mathbb{N}_0$.
Define filtrations:


\[
\mathcal{F}_t = \sigma(x_0,\dots,x_t,\; y_0,\dots,y_t,\; a_0,\dots,a_{t-1}),
\]




\[
\mathcal{F}_t^{\mathrm{obs}} = \sigma(y_0,\dots,y_t,\; a_0,\dots,a_{t-1}).
\]


This separates latent system evolution from observable agent information. The probability space describes randomness.
Two filtrations exist:
everything, including the hidden state


\vspace{1em}

\textbf{Definition 4 (System Space).}
Define the product space

Z=X×P(X)×A×T×P(X),



with $\mathcal{F}_Z=\mathcal{B}(Z)$. Let $S\in\mathcal{F}_X$ be the safety set.

The probability space describes randomness. Two filtrations exist:


\[
\mathcal{F}_t : \text{everything, including the hidden state},
\qquad
\mathcal{F}_t^{\mathrm{obs}} : \text{only what agents can see}.
\]


Processes such as 


\[
x_t,\; y_t,\; a_t
\]


must be measurable with respect to the correct filtration. Beliefs $b_t$ and
true laws $\mu_t$ are probability measures over states. Take as an example of open world first person game: There is a big world where everything happens, and a smaller world where the players only see some things. The system moves step by step. Some things are secret (the real state), and some things are visible (what the players see). 


\[
\mathcal{T} \subseteq 
\{\, T : Z \to Z 
\mid T \text{ is Borel measurable and maps measure components into } 
\mathcal{P}(X) \,\}.
\]



\textit{Discussion:}
Operators define system evolution at the highest level of abstraction. 
Restricting them to admissible classes ensures structural consistency and 
prevents invalid transformations.

\vspace{1em}

\textbf{System State Process.}


\[
Z_t = (x_t, b_t, a_t, T_t, \mu_t) : \Omega \to Z.
\]



\textit{Discussion:}
This aggregates all system components into a single stochastic process. It 
enables unified analysis of dynamics, uncertainty, and control.


\section{Definition:5 (System State and Operator Space).}
Define the system state space:


\[
Z = X \times \mathcal{P}(X) \times A \times \mathcal{T} \times \mathcal{P}(X),
\]


equipped with the Borel $\sigma$-algebra $\mathcal{B}(Z)$.

Let $\mathcal{T}$ be a Polish (or standard Borel) space of operators such that each
$\tau \in \mathcal{T}$ is a Borel measurable mapping:


\[
\tau : Z \to Z,
\]


preserving the probabilistic structure of the $\mathcal{P}(X)$ components.

The full system state process is:


\[
Z_t = (x_t, b_t, a_t, T_t, \mu_t): \Omega \to Z.
\]

\textbf{Stochastic Structure and Processes}

Let (\Omega,\mathcal{F},P) be a probability space with time index  $t \in \mathbb{N}_0$. 
Define the filtration


\[
\mathcal{F}_t 
= \sigma(x_0,\dots,x_t,\; y_0,\dots,y_t,\; a_0,\dots,a_{t-1}),
\]




\[
\mathcal{F}_t^{\mathrm{obs}}
= \sigma(y_0,\dots,y_t,\; a_0,\dots,a_{t-1}).
\]



Processes are defined as


\[
x_t : \Omega \to X, 
\qquad 
y_t : \Omega \to Y, 
\qquad 
a_t : \Omega \to A,
\]


with 


\[
x_t \text{ being } \mathcal{F}_t\text{-measurable},
\qquad
y_t,\, a_t,\, b_t,\, T_t 
\text{ being } \mathcal{F}_t^{\mathrm{obs}}\text{-measurable}.
\]



The belief and true law satisfy


\[
\mu_t = \mathcal{L}(x_t) \in \mathcal{P}(X),
\qquad
b_t \in \mathcal{P}(X).
\]



The system state is


\[
Z_t = (x_t, b_t, a_t, T_t, \mu_t) : \Omega \to Z.
\]


This section establishes the complete measurable and topological structure 
of the Indestructible Governance Framework (IGF). No dynamics, laws, or 
invariants are introduced here. The goal is to define a mathematically 
closed universe in which all subsequent reasoning will occur. The system state process lives in this space. The final identity states that IGF is a stochastic system on a filtered probability space with a clean separation between hidden and observable information. 
The whole system is like a big backpack holding everything: the real place, the guess, the actions, the rule machine, and the truth. At each time, the backpack has new things inside. The rules say what you can see and what you cannot. IGF is a stochastic system defined on a filtered probability space


\[
(\Omega,\mathcal{F},\{\mathcal{F}_t\},\{\mathcal{F}_t^{\mathrm{obs}}\},P)
\]

collects everything: the real state, the belief, the actions, the operators, and the true law. The system state process lives in this space. The final identity states that IGF is a stochastic system on a filtered probability space with a clean separation between hidden and observable information. The whole system is like a big backpack holding everything: the real place, the guess, the actions, the rule machine, and the truth. At each time, the backpack has new things inside. The rules say what you can see and what you cannot. where all processes are measurable and adapted, operators are admissible measurable maps, and the information structure explicitly separates latent and observable components.

\vspace{1em}

\textit{Discussion:}
This identity formalizes the complete mathematical universe of IGF. It 
guarantees that all objects are well-defined, all mappings are measurable, 
and all interactions respect information constraints. This provides a fully 
closed foundation upon which laws, invariants, and governance principles can 
be rigorously built.









\end{document}
