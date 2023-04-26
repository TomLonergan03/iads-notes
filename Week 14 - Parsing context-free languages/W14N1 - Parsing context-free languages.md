The **parsing problem** is that of how we get from a [[W13N4 - Context-free languages and grammars|CFG]] sentence to a [[W13N4 - Context-free languages and grammars#Syntax trees|syntax tree]].
E.g. using a CFG with terminals `+,0...9,(,)` and non-terminals `Exp,Var` and rules:
`Exp -> Num | ( Exp + Exp )`
`Num -> 0 | ... | 9`
We have the string `( 3 + ( 4 + 5 ) )`. This is produced by the tree ![[w14n1ParsingTree.png]]
However, how do we do this algorithmicly?

# The Cocke-Younger-Kasami Algorithm
The **Cocke-Younger-Kasami (CYK) Algorithm** is an algorithm that can produce a syntax tree for any sentence in any CFG. This algorithm is another example of [[W11N2 - Dynamic programming|dynamic programming]].
- The algorithm works on a special class of grammars, those in Chomsky normal form (CNF)
	- This is still general as any CFG can be transformed into an equivalent one in CNF
- CYK parses an input of length $n$ in $\Theta(n^3)$. This is fine for short sentences, but quickly becomes impractical for long computer programs. There we can instead use [[W14N2 - LL(1) Parsing|LL(1) parsing]], which is faster at the cost of being less general

# Chomsky normal form
In a CFG, the right side of each production is a (possibly empty) string of terminals and non-terminals. E.g.
`Exp -> ( Exp + Exp )`

A grammar in **Chomsky normal form** is one in which each right-hand side consists of either:
- Just 2 non-terminals
- Just 1 terminal

For an example CNF CFG to parse:
Terminals: `book, orange, heavy, my, very`
Non-terminals: `NP, Nom, AP, A, Det, Adv`
Start symbol: `NP`

`NP -> Det Nom`
`Nom -> book | orange | AP Nom`
`AP -> heavy | orange | Adv A`
`A -> heavy | orange`
`Det -> my`
`Adv -> very`

This will generate noun phrases like:
`my very heavy orange` and `my very heavy orange book`

CNFs often include duplication.
In the above case, `AP -> A | Adv A` would be simpler, but is not valid in CNF.

If we want to parse the string `my very heavy orange book`, we can insert position markers: `(0) my (1) very (2) heavy (3) orange (4) book (5)`. We can then talk about sub-strings, e.g (2,4) indicates `heavy orange`.