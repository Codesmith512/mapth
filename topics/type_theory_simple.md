---
title: simple type theory
area: logic
rigor: village
---

The people of simple type theory are closely related to first and higher order logic, but they've created a sort of legalese to help ensure the deals they strike with the fae are valid. The only difference is that when a variable is introduced, it is given a type noted with a colon after it:

$$
\text{Double} (n : \mathbb{N}) : \mathbb{N} \equiv n + n
$$
> "Double" depends on a natural number, n, and is a natural number. It is defined as adding n to n.

Nowadays, the local economy thrives on mainstream programming languages, which use simple type theory to catch various programming errors before the software is even run! For example, without having to test the following code, we know it's wrong because the type passed in isn't a number:

```lean4
Double "cat"
```

> Should this resolve to two "cats"s? One "catcat"? What is that? What did the writer intend? AAHHHHH

Originally, most of the locals spent their time validating complex proofs, where abstract syntax made it easy to hide hide and miss such catastrophic errors. Some of them still do this today, though most of the village is now employed in programming fields, and most of the proof validators have moved on to [dependent type theory](./type_theory_dependent.html).

Of note, type theory formalizes grammar concepts like semantics. It doesn't prevent bugs per-se, because it can't really determine if you proved the correct thing. It can determine if a proof or a program is "valid", though as you pull that thread and walk through the various settlements of type theory, you'll find that question to be rather philosophical. 

## Type Systems

In programming, there are 2 main types of type systems:

**Normative Typing** determines the type of an object based on the constructor (function) that was used to create it. `f = Foo()` is of type `Foo`, because that's where it came from. Many "harder" languages - C++, C#, etc. use this system. This is also an intensional type system, as can differentiate identical objects based on how they were made.

**Structural Typing** determines the type of an object based on its properties. If we have a `structure Foo { n : number }`, then any object containing a member `n` that is a number is an acceptable `Foo`. This also means that any object can be of many different types. This is also sometimes referred to as an extensional type system, as it cannot differentiate identical objects.

Additionally, there are 3 main times that the type system can be specified:

**Strongly typed languages** are the most common. In these languages, the programmer specifies types and the compiler verifies them when the software is packaged. This is the style of the example above.

**Weakly typed languages** let the compiler both infer and validate typing when the program is packaged. This is inherently weaker, because the same party is specifying and verifying the software.

**Dynamically typed languages** let the compiler both infer and validate tying when the program is run - these are more rare as they come with runtime overhead, but they can solve classes of the others cannot.

---

<details markdown="1">
<summary><em>In <a href="/mapth/appendix/mathlib.html">Mathblib</a>...</em></summary>

Lean4 and Mathlib are written in [Dependent Type Theory](./type_theory_dependent.html), which is a superset of simple type theory - if you have a type that doesn't depend on a bound (named) variable, that is a simple type:

```lean4
def a : Nat := 1
def b : List Nat := #[a]
```

Note the difference between that and this dependently typed declaration (where `List` depends on a bound variable)

```lean4
def c (t : Type) : List t := #[]
```

</details>