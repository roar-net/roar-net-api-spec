<!--
SPDX-FileCopyrightText: © 2025 Authors of the ROAR-NET API Specification <https://github.com/roar-net/roar-net-api-spec/blob/main/AUTHORS>

SPDX-License-Identifier: CC-BY-4.0
-->

# Background

## Optimisation problem

Formally, we consider a **(minimisation) problem** in the form

\\[\min\\{f(x) \mid x \in F\\}\\]

The set \\(F\\) is the set of **feasible solutions**, which is a
subset of the **decision space**, \\(S\\). The mapping \\(f: S \to
\mathbb{R}\\) is an **objective function** that associates to each
solution \\(s\in S\\) a real value in the **objective space**,
\\(\mathbb{R}\\).

<!--The image of \\(F\\) under \\(f\\) is the image of the feasible
solutions in the objective space. -->

In this case, the objective space is totally ordered, and the minimum
is given by all solutions \\(x^\*\in F\\) such that \\(f(x^\*)\leq
f(x) \\) holds for all \\(x\in F\\).  Such a solution \\(x^\*\\) is
called an **optimal solution**.  **Maximisation problems**, in which
we are searching for the feasible solutions whose value is the maximum
in the objective space, can be reduced to minimisation problems as
\\(\max\\{f(s) \mid s \in F\\}=-\min\\{-f(s) \mid s \in F\\}\\).

In this specification, optimisation problems are specified by means of
a `Problem` type.

## Search space

The representation and the exploration of the **search space** of a
problem implementing the API rely on how solutions are characterised,
how they are generated, and on how they are evaluated.

### Candidate solutions

We assume that the details regarding the components of the solution
are not exposed, nor the details of how to create or modify a
solution. Instead, the API provides abstract operations that allow to
generate and modify solutions in a black-box manner, and that is
common to all algorithmic approaches covered.

The API relies on the observation that:

- constructive search algorithms work by starting from an initial
  *state* and sequentially applying *actions* or *changes* to it to
  attain new states until a goal is reached.
- local search algorithms work by maintaining a set of states, and
  iterating through states that can be reached by applying (small)
  *changes* to the stored states.

In both cases, such states represent **candidate solutions**. The
changes that allow to modify a solution \\(s\\) to obtain another
solution \\(s'\\) is called a **move**, in which case \\(s'\\) is
called a **neighbour** of \\(s\\).

A **candidate solution** is an element of the *decision space*,
\\(s\in S\\), but not necessarily an element of the set of feasible
solutions. Such solution can violate constraints or satisfy other
constraints that are known to be necessary for optimal solutions. A
candidate solution in ROAs can be:

- a **partial solution**, which may not contain yet all components of
  a feasible solution.
- a **complete solution**, which contains all components but may
  violate problem constraints and may not be optimal.

<!-- TODO: introduce here the notions of feasible/infeasible and
valid/invalid solutions? -->

In this specification, solutions are specified by means of a
`Solution` type.

### Neighbourhoods

We assume that the exploration of the search space relies on the
concept of *neighbourhood structure*, which has a central role in
ROAs. A **neighbourhood structure** is given by the definition of a
neighbouring relation between solutions. That is, \\(N(s,s')\\) is a
Boolean, whose value depends on whether \\(s'\\) can be obtained from
\\(s\\) by means of the application of a small change operator, called
**move**. The set of solutions \\(s'\\) that can be reached in this
way from \\(s\\) forms the **neighbourhood** set of \\(s\\),
\\(N(s)\subseteq S\\). **Neighbourhood structures can be defined for
both complete and partial solutions**.

In this specification, the neighbourhood structure is specified by
means of a `Move` type and a `Neighbourhood` type, this latter
implementing the generation of moves.

### Solution evaluation

The specification provides operations to query the feasibility and the
objective value of candidate solutions.  We do not assume to have
available a mathematical description of \\(F\\) nor \\(f\\), that is,
we assume a **black box** scenario. Even if a mathematical description
of the decision space is known, we assume that the feasibility and the
objective value of **candidate solutions are assessed in an oracle
manner**, that is, without exposing how these assessments have been
computed; e.g., the feasibility and the objective value of candidate
solutions could be assessed by executing a computationally costly
simulation, but this information is not shared.  However, when
present, mathematical descriptions can be exploited to improve the
implementation of the specification.

In ROA, the **objective function** is frequently replaced by an
**evaluation function** \\(g\\), which is also a mapping of the
decision space \\(S\\) to a set of real numbers \\(\mathbb{R}\\). The
evaluation function can account for the objective function but also
for penalties due to the violation of the problem constraints.
