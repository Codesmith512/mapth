---
title: first order logic
area: logic
rigor: city
---

After leaving [propositional logic](./logic_zero_order.html), you'll need to venture through the forest to get to the city of First Order Logic. Beware the fae that live in the woods - they cannot lie to you, and their word is binding, but that only makes them more dangerous if you don't know what to look out for.

Once you get to First Order Logic, you'll find that the people are familiar enough. They still tend to frame the world in terms of true/false propositions, but they also how often those things are true:
  * When **_for any_** rainbow, $r$, it holds that $r$ has a pot of gold
  * Then when **_there exists_** a leprechaun, $l$, for every port of gold 
  * Then every rainbow has a leprechaun

This is a really important leap, because it provides enough basis start to talk about the [elements of sets](./naive_set_theory.md) in terms of the propositions they meet. The people of first order logic also resemble the fae of the woods they live near - they always speak truths, but usually not absolute. As you have conversatitons, watch out for the inevitable "if" or "when" of implications - it's always on the listener to decide if their world view coincides with the truths spoken. Whether or not you live in a world with rainbows, pots of gold, and leprechauns, the above logic is true and sound.

It'll take a bit of getting used to, but after a few days, you'll blend in with the locals fine. The only thing that's a bit odd here is how many locals seem to have come back from [higher order logic](./logic_higher_order.html).

## $\forall$ Universal Quantification
_The weird A thing_ means "for Any" or "for All". It asserts that any item in a set satisfies a particular proposition. 

$ \forall (b : \text{Bunny}), \text{IsCute} \ b $
> For any Bunny, $b$, it holds that $b$ is cute.

## $\exists$ Existential Quantification
_The weird E thing_ stands for "there Exists". It asserts that there is at least one thing (that we get to give a placeholder name to) that makes some proposition true.

$ \exists (w : \text{Wolf}), \text{IsCute}\ w $
> There exists a Wolf, $w$, such that $w$ that is cute.

Sometimes, you'll see it with an exclamation mark - $\exists \ !$, which denotes that there is _exactly_ one thing that makes the proposition true.

## Variables

Both types of quantification let us create "bound variables", which give a name to a type of thing, noted as $(\text{name} : \text{Type})$. This name can be used later to refer to it.

Maybe the most common place you'll see names like this used is with implication propositions. For example:

$$
\begin{align}
\> & \text{IsCute} \equiv t \rightarrow \text{I See}\ t \rightarrow \text{I Pet}\ t \\
\text{(Given)}\> & \exists (w : \text{Wolf}), \text{IsCute}\ w \\
& \exists (w : \text{Wolf}), (t \rightarrow \text{I See}\ t \rightarrow \text{I Pet}\ t)\ w \\
& \exists (w : \text{Wolf}), \text{I See}\ w \rightarrow \text{I Pet}\ w
\end{align}
$$

> 1. "Being cute is defined as when there is a thing, $t$, then when I see $t$ then I will pet $t$"
> 2. Given that there exists a Wolf, $w$, such that $w$ is cute
> 3. Is obtained by replacing $\text{IsCute}$ with its definition
> 4. Is obtained by substituting $t$ with $w$ in the chain of reasoning. "There exists a Wolf, $w$, such that when I see $w$ then I will pet $w$".

If I randomly stop posting on this blog, it's probably because I found the cute wolf...

---

<details markdown="1">
<summary><em>In <a href="/mapth/appendix/mathlib.html">Mathblib</a>...</em></summary>

Universal Quantification is [foundational](https://leanprover-community.github.io/mathlib4_docs/foundational_types.html), as it's simply a special type of function. If this isn't intuitive, think about how you can frame a computational function as a universal quantification. For example, a function that takes a natural number and returns the successor can also be stated as "for any natural number, $n$, it holds that there is a successor", and then the algorithm for computing the next number serves as the proof.

Existential Quantification is implemented in the [Exists](https://leanprover-community.github.io/mathlib4_docs/Init/Core.html#Exists) type.

</details>