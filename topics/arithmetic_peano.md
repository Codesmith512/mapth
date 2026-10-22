---
title: peano arithmetic
area: number theory
rigor: city
---

The inhabitants of Peano Arithmetic pride themselves in being the "official" body of Arithmetic from which the people of simple [Airthmetic](./arithmetic.html) have long since broken off and declared independence. The people of Peano Arithmetic tend to view simple Arithmetic as imprecise and shallow, and while both groups can can be traced back to their heritage in set theory, they rarely interact with each other and their cultures have diverged over time.

In most modern contexts, the Peano Axioms are defined as such:

$$
\begin{gather}
0 \in \mathbb{N} \\
S : \mathbb{N} \rightarrow \mathbb{N} \\
\forall x, Sx \neq 0 \\
\forall x \forall y, (Sx=Sy) \rightarrow (x=y)
\end{gather}
$$

<details markdown="1">
<summary>(In English...)</summary>

> 1. $0$ is a natural number
> 2. There exists an $S$ that takes a natural number and gives a natural number
> 3. There does not exist an x such that the successor of $x$ is 0
> 4. For all $x$ then for all $y$, then when the successor of $x$ equals the successor of $y$, then $x$ equals $y$

_Note_ that $S$ is initially taught as the successor function, where 1 is $S0$ and 2 is $SS0$ and so on.

</details>

These statements fully define natural numbers ($\mathbb{N}$) up to isomorphism with any other system.

The following Axioms introduce what's necessary to define addition and multiplication:

$$
\begin{gather}
\forall x, x + 0 = x \\
\forall x \forall y, x + Sy = S(x + y) \\
\forall x, x \cdot 0 = 0 \\
\forall x \forall y, x \cdot Sy = (x \cdot y) + x
\end{gather}
$$

<details markdown="1">
<summary>(In English...) </summary>

> 5. For all $x$, then $x + 0 = 0$
> 6. For all $x$ then for all $y$, $x$ plus the successor of $y$ is the same as the successor of $x$ plus $y$
> 7. For all $x$, then $x$ times $0$ equals $0$
> 8. For all $x$ then for all $y$, $x$ times the successor of $y$ equals $x$ times $y$ plus $x$

_Note_ that 6 and 8 are dependent on succession of $y$, hence 5 and 7 define the base case where $y$ is 0

</details>

Finally, an induction system rounds the system out. Given a predicate $P(\mathbb{N})$

$$
\begin{gather}
(P(0) \wedge (P n \rightarrow P S n) ) \rightarrow P \\ 
\end{gather}
$$

<details markdown="1">
<summary>(In English...)</summary>

> 9. For all $P$ depending on a natural number, then when $P$ is true at $0$ and when $P$ at some number $n$ is true implies that $P$ at the successor of $n$ is true, then $P$ is true

</details>

There is a long standing tradition in this city that an annual debate in held in the public square, where various systems that are equivalent and almost-equivalent are presented and debated in a variety of contexts.

## References

https://www.cs.toronto.edu/~sacook/csc438h/notes/page96.pdf


<details markdown="1">
<summary><em>In <a href="/mapth/appendix/mathlib.html">Mathblib</a>...</em></summary>

Lean is based on a different, but compatible set of axioms as the Peano Arithmetic outlined here. As a result, the axioms presented here are theorems in Lean, but they hold nonetheless.

Lean uses `Nat` as the type of natural numbers. Axioms 1 and 2 are captured in the [inductive constructors][1] of the type. Axiom 3 present as the theorem [`Nat.succ_ne_zero`][3], and Axiom 4 is present as the theorem [`Nat.succ_inj`][4].

[`Nat.add`][5] is implemented by two equations that exactly capture 5 and 6, and [`Nat.mul`][7] is implemented by equations perfectly capturing 7 and 8.

Because 9 is a form of induction, the [induction tactic][9] will create an instance from a particular bound number.

[1]: https://leanprover-community.github.io/mathlib4_docs/Init/Prelude.html#Nat
[3]: https://leanprover-community.github.io/mathlib4_docs/Init/Data/Nat/Basic.html#Nat.succ_ne_zero
[4]: https://leanprover-community.github.io/mathlib4_docs/Init/Data/Nat/Basic.html#Nat.succ_inj
[5]: https://leanprover-community.github.io/mathlib4_docs/Init/Prelude.html#Nat.add
[7]: https://leanprover-community.github.io/mathlib4_docs/Init/Prelude.html#Nat.mul
[9]: https://lean-lang.org/doc/reference/latest/Tactic-Proofs/Tactic-Reference/#induction

</details>