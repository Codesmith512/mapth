A long time ago, set theory spanned almost the entire continent. Nowadays, it remains an honorable city-state. The people of the former empire of set theory still believe that everything is one of three things
- A *Set* of elements
- *Elements* in those sets
- *Maps* that convert elements between those sets

Don’t let this simplicity fool you, as there are still many adherents outside its borders, and these beliefs form a sort of Lingua Franca (or business language) that persists to this day in many other regions. In fact, its cultural influence is so strong that when sufficient logic is applied to set theory, it can derive all other fields of math. This is largely because there are virtually no restrictions on what can be an element - sets or maps can also be elements of other sets.

Also notable is the pilgrimage that every child makes to the temple in set theory as they learn to count. If you remember counting cookies or stones or trees, then you remember counting the elements in a particular set (or domain). You also probably remember learning to add and subtract by combining or splitting sets.

# Notation

Common Symbols

| $e$                                  | An element $e$                                                |
| ------------------------------------ | ------------------------------------------------------------- |
| $S$                                  | A set named $S$                                               |
| $e \in S$                            | $e$ is in $S$                                                 |
| $f : A \rightarrow B$, $a \mapsto b$ | The map $f$, which turns elements of $A$ into elements of $B$ |
| $\mathbb{N}$                         | The set of all natural numbers                                |

## Set Builder Notation

the cornerstone of any set is describing which elements make it up. There are two main approaches - extensional and intensional.

Extensional notation explicitly lists the elements in the set (the extent) :
$$
A_1 = \{ 0, 1, 2, 3 \}
$$
> $A_1$ is exactly 0, 1, 2, and 3

{% include note.html content="This is my note. All the content I type here is treated as a single paragraph." %}


Intensional notation defines the rule that all elements of the set must follow, by naming a potential member and then stating the condition that it must meet
$$
A_2 = \{ n \> | \> n < 4\}
$$
> $A_2$ is all n such that n is less than 4

Note that $A_2$ is different than $A_1$ because it can contain anything less than 4, such as the number -12, a perfectly reasonably sized hot dog, or your left sock.

To fix this, we can say that all potential members must come from an already existing set, such as the countable numbers
$$
A_3 = \{ n \in \mathbb{N} \> | \> n<4 \}
$$
> $A_3$ is all n in the natural numbers such that n is less than 4

$A_3$ now contains all the same elements as $A_1$, it’s just defined intensionally.

# Maps

A map defines a relationship between elements. Some maps take elements of one set and map them onto elements of the same set. An easy to swallow example is the succession map :
$$
succ : \mathbb{N} \rightarrow \mathbb{N}, x \mapsto x+1
$$
> $succ$ is a map from natural numbers to natural numbers such that every $x$ maps to $x+1$

Other maps take elements of one set and map them onto elements of another set entirely. Consider this map that takes a ratio (between 0 and 1) and turns it into a percentage :
$$
percent : \{x | 0 \leq x \leq 1\} \rightarrow \{y|0 \leq y \leq 100\}, x \mapsto x \times 100
$$
> $percent$ is a map from the set of all $x$ between $0$ and $1$ to the set of all $y$ between $0$ and $100$, such that every $x$ maps to $x \times 100$

# Major Battles

## Russel’s Paradox
In the 1900s, set theory was largely seen as a solved (or complete) field of math and was already beginning to underpin most of the rest of mathematics. However, Bertrand Russel discovered an inconsistency that rendered the field useless, and threatened the entire order of math :
$$
D = \{ s | s \notin s\} \rightarrow D \in D \wedge D \notin D
$$
> If $D$ is all $s$ such that $s$ is not in $s$ then $D$ contains $D$ and $D$ does not contain $D$

In other words, does the set of all sets that do not contain themselves, contain itself?

In order to kill this dragon, Zermelo teamed up with Fraenkel to create ZF set theory, which avoids this famous paradox while still being flexible enough to underpin mathematics. For more, visit the modern capital of Set Theory, ZFC.