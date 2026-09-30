---
title: Route 01
Rigor: Road
---

$$
S \rightarrow \mathbb{N} , s \mapsto |s|
$$

> Any set can be mapped onto a number, given a set $s$, simply take the number of elements in it.

The road from set theory to arithmetic is incredibly well traveled by almost everyone. It was probaby the first road you took as you learned to count. Deep in the mountains, a customs officer will take all of your bags, and give you tickets with the number of items in each bag. These tickets are the currency and lifeblood inside the walls of number theory. He also gives you a barcode you can use to retrieve your bags later.

$$
\mathbb{N} \rightarrow S , ?
$$

The road from arithmetic back to set theory is far less traveled. As you encounter the customs agent headed the other way, you realize why - if you have a barcode, you can exchange your numbered tickets for your bags and be on your way. If you don't know which bags are yours however, there is no way back into set theory.

---

Formally, sets can only be mapped to arithmetic as a whole if the operations in arithmetic can also be mapped from set theory. Since we define `-` and `/` to be inverses of `+` and `*`, we only need to be able to define $A$ and $B$ such that $\{S, A, B\} \rightarrow \{\mathbb{N}, +, *\}$, and then we can derive `-` and `/` from there.

In this case, we can pick\
$A$ to be the indexed summation operation on sets to become addition over natural numbers\
$B$ to be the cartesian product operation on sets to become multiplication over natural numbers

