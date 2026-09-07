---
title: Higher Order Logic
area: logic
rigor: capital
---

It's a common misconception that Higher Order Logic is a distinct place. As you wander the streets of the city of First Order Logic, you'll eventually pass a small sign that marks the district of Second Order Logic. If you felt a chill in the air as you crossed the threshold, that's certainly appropriate. If you missed it entirely, you're certainly not the first.

The people here seem incredibly familiar, as the Faerie magic still drives them to absolute honesty, but it's the nuance of their statements that gets trickier and trickier.

## Second Order Logic

The sign that marks the district of second order logic is a small one, and many tourists miss it. Variables, Propositions, and quantification all work like they do in [First Order Logic](./logic_first_order.html). The only difference is that the type introduced by quantification is itself now a first order statement.

For example, a carrot cake is a property that a cake has, when there is at least one carrot in it (I don't make the rules):

$$
\text{CarrotCake} (c : \text{Cake}) \equiv \exists(r : \text{Carrot}), r.\text{in}(c)
$$

The type of $c$ and $r$ are concrete, so this statement is a first order statement. However, if we want to assert that there exists a _vegetarian carrot cake_ (not vegan, and something I've genuinely seen in the store before), we need second order logic, as the existential quantifier introduces a first-order variable:

$$
\exists (c : \text{CarrotCake}(c)), \text{IsVegan}(c) \wedge \text{IsVegan}(pr_1(CarrotCake(c)))
$$

Let's break that down real quick
- $\exists (c : \text{CarrotCake}(c))$ Simply states that there exists a $c$ that is not only a cake, but one where the carrot cake property holds
- $\text{IsVegan}(c)$ simply asserts that the cake $c$ is vegan
- $\wedge$ is the "both ... and ..." connective
- $\text{IsVegan}(pr_1(CarrotCake(c)))$
    - $\text{IsVegan}(pr_1(\exists(r : \text{Carrot}), r.\text{in}(c)))$
    - $\text{IsVegan}(r)$
        - Note that the first projection of an existential quantification is the thing being quantified.

So not only does the cake have to be vegetarian, but also the carrot in it. Not just any carrot, but specifically the one in the cake (hence the complexity above).

If first-order logic allows you to take a bare type and define a property that some/all members of that type have, then second-order logic is about taking some/all members that meet a property and deriving another propery.

## Higher Order Logic

If you wander far enough, you'll find the district of Third Order Logic, where quantification happens over second-order statements. Quantify over those, and you get to the district of fourth-order logic. I think you see where this is going.

At and beyond second-order logic, most of the districts are really similar. Everyone just says that they're from higher order logic, and unless you're familiar with the capital, you probably won't have heard of the exact district anyway.

Beware wandering around the capital though - the deeper you go, the more powerful the magic becomes. More and more ideas can be expressed with ever increasing nuance and power. But the burden of proof grows _significantly_, and the specificity often makes statements less useful than they first appear. As the bound approaches infinite nesting, proofs become impossible (an interesting analogy to [The Halting Problem](./topics/problem_halting.html)). You'll notice that fewer and fewer people inhabit the innermost districts, and the ones that do have a wild look in their eyes.

---

<details markdown="1">
<summary><em>In <a href="/mapth/appendix/mathlib.html">Mathblib</a>...</em></summary>

The ability to express and chain logical statements is a core part of the Lean language, not implemented specifically in mathlib.

The parallel concept in lean's type system is [Type Universality](https://lean-lang.org/doc/reference/latest/The-Type-System/Universes/) :

> types in a given universe may only quantify over types in smaller universes 

Lean implements this by mapping types onto universes, onto natural numbers. This requires that type universes (and therefore the logic in the type system) are finite, albeit arbitrarily complex. It also allows programmers to place bounds on the complexity of the logic allowed in parts of their codebase.

</details>
