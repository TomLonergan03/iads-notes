The canonical (and first proven) [[W16N1 - P and NP#NP-completeness|NP-complete]] problem is statisfiability.

Given a propositional logical formula $\phi$  over variables $\{x_1,...,x_n\}$ in conjunctive normal form (CNF) (in the format $\phi=C_1\land C_2\land C_3\land...\land C_n$ where each $C_i$ is some combination of $\{x_1,...,x_n\}$ ored together (e.g. $\phi_1=(x_1\lor x_2)\land(x_3\lor \overline x_4)$).

What assignments of logical variables makes $\phi$ true?
e.g. for $\phi_1$:
$x_1=0,x_2=0,x_3=0,x_4=0$ satisfies $\phi_1$.
$x_1=0,x_2=0,x_3=0,x_4=1$ does not satisfy $\phi_1$.

There are $2^n$ possible assignments to the $n$ logical variables of a CNF.

# Cooke-Levin Theorem
