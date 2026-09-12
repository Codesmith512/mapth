---
title: P vs NP
rigor: Open Problem
---

# Boolean Satisfiability (SAT)

The problems of boolean satisfiability are based entirely on [Propositional (Zeroth Order) Logic](./logic_zero_order.html), and they all involve finding answers to different questions about any propositional system, where "propositional system" is a collection of names and propositional statements about them.

The original, nonconstsructive question is whether there exists a set of values that makes the system $true$. The constructive question asks for a specific set of values make the system $true$ (though there won't always be one).

For example, the system $a \wedge \neg a$ has no solution. A constructive proof may show that whether $a$ is $true$ or $false$, the answer is $false$. A nonconstructive proof may cite the contradiction between the branches of the conjunction as a reason there is no solution.

Another system, $\neg a$, can constructively be shown to have a solution $a \equiv false$, and nonconstructively shown to have a solution because it is contradiction free.

Keep in mind that the goal of SAT is not to solve any single problem, but to produce an algorithm that can solve _all possible_ problems. 📝_Note_ the universal quantification, borrowed from [First Order Logic](./logic_first_order.md). While the solution will be in Zeroth Order Logic, the algorithm must operate at least one layer up.

Note that nonconstructive proofs don't have to demonstrate a specific answer, while constructive proofs are required to construct an answer.

# P vs NP
❗ _Open Problem in Mathematics_

Constructive SAT is a relatively easy problem to verify - given a set of values as a potential answer, simply plug them into the system and see if it works out to true. Finding an answer to any arbitrary system is far harder, with a naive approach simply being to brute-force every possible true/false combination until one makes the entire system true, or no options ara left.

P vs NP is an open problem in computer science that generally asks whether any problem that is quickly verifiable (NP) is also quickly solvable (P).

**If False**
> A proof that P vs NP is false would be huge, and give us confidence in the engineering of the modern world of computing.

P vs NP is generally thought to be false - there are allowed to be problems that are just harder to solve than they are to verify. This actually forms the basis for most modern cryptographic systems that underpin making sure that data is secret or authentic.

**If True**
> A proof that P vs NP is true would be huge, and would a lot of churn in the world.

If P vs NP ends up being true and every problem that is quickly verifiable is also quickly solvable, then a lot of modern software _could_ get significantly faster, including software designed to break cryptography used in finance, healthcare, and military applications.

A lot of the impact comes down to exactly what the proof is, especially whether the proof is constructive ("here is an algorithm that quickly solves NP-complete problems like SAT"), or nonconstructive ("such an algorithm must exist, but I don't have it").

**If Unknowable**\
A proof that P vs NP is unsolvable would be huge, but creates a much murkier picture of the future.

Looking at other unsolvable problems in math (such as the halting problem), I suspect that the question would just get asked in more specific cases - "Is the specific version of P vs NP that underpins cryptography solvable?". This is complicated by the fact that NP-complete problems are all equivalent to each other, so solving one of them amounts to solving all of them (which goes against the premise of this scenario), but there are a lot of NP-hard problems that aren't equivalent that probably get explored.
