---
title: presburger arithmetic
area: number theory
rigor: city
---

The port city of Presburger Arithmetic lies at the delta of a sacred river between the [Village of Arithmetic](./arithmetic.html) and [City of Peano Arithmetic](./arithmetic_peano.html). Its people rely solely on natural numbers and succession (familiar to Peano Arithmetic), building all other structures on top of them. This makes it more formal, but less powerful than traditional arithmetic.

As a result, the city is very ordered, albeit relatively small. Still, it serves as an important port of trade with the Peninsula of Computation, where merchants bring exotic problems to be worked on, and tourists can enjoy a simpler, more laid back and certain field of logic.

This is also the first major city on this side of the number theory range that isn't often stated in terms of set theory, as it lacks a new path through Number Theory Range that doesn't just piggy back off of the pass that Peano Arithmetic uses.

## Formalization

The formalization of Presburger Arithmetic is remarkably simple, and was probably the first formal system I really wrapped my head around:

$$
\begin{gather}
\neg(0 = x + 1) \\
x + 1 = y + 1 \rightarrow x = y \\
x + 0 = x \\
x + (y + 1) = (x + y) + 1 \\
\end{gather}
$$

> 1. There is no number such than it's successor is 0.
> 2. When x + 1 = y + 1, then x = y
> 3. Adding 0 to x yields x
> 4. Adding 1 to y and the result to x is the same as adding y to x and then adding 1

Additionally, for any $P(x)$, the following axiom holds:

$$
\begin{gather}
(P(0) \wedge \forall x, (P(x) \rightarrow P(x+1))) \rightarrow \forall y, P(y)
\end{gather}
$$

> When $P$ is true at 0, and when for all x, when $P$ at $x$ implies $P$ at $x + 1$, then $P$ is true everywhere

Note that in first order logic, this is a template (a schema) for building infinitely many axioms. It can be expressed as

$$
\forall P : \mathbb{N} \rightarrow \text{Prop}, ...
$$

In [Second Order Logic](./logic_higher_order.html), however as warned there, doing so dramatically increases the complexity of the system.

## Completeness and Consistency

The most notable part of Presburger Arithmetic is that it is provably consistent and complete, a very rare and valuable combination. In a field of math, consistency is the property that any question has at most one answer - there are no contradictions or inconsistencies. Completeness is the property that any question has at least one answer - there are no holes.

Sometimes these topics are easier explored through counter-examples:
- "Traditional algebra" is inconsistent at $\sqrt{9}$ (is it $3$ or $-3$?)
- "Traditional algebra" is incomplete at $1/0$ (which has no answer)

Due to it's simplicity however, Presburger Arithmetic does not contain either of these flaws, and is both consistent and complete. As such, it's common to translate a problem into Presburger terms, as just the act of successfully translating the problem means it is definitely solvable or not.
