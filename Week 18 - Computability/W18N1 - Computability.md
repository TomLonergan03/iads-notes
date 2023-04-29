The **Church-Turing (CT) computable functions** are generally accepted as coinciding with the 'algorithmically computable' functions i.e. functions that can be computed using a series of instructions which can be defined as a series of steps and ignoring time and space limitations.

There are many ways to reach the same class of CT-computable functions:
- $\lambda$ calculus
- Turing machines
- Register machines

To use the example of register machines, a register machine has a fixed, finite set of registers ($A,B,...,I$)each capable of storing an arbitrary natural number.
We can build a machine by joining trivial components
![[w18n1RegisterMachineComponents.png]]
The example machine adds $B$ to $A$, losing the value of $B$ in the process.

To use a register to compute a function, e.g. $\mathbb{N}\times\mathbb{N}\rightharpoonup\mathbb{N}$,  we can supply inputs in registers $A$ and $B$, and read the output from $A$.

