<!--
SPDX-FileCopyrightText: © 2025 Authors of the ROAR-NET API Specification <https://github.com/roar-net/roar-net-api-spec/blob/main/AUTHORS>

SPDX-License-Identifier: CC-BY-4.0
-->

# Candidate Solution

## Signature

```text
Solution
```

## Description

The type `Solution` is a data structure defining a particular
candidate solution. Therefore, `Solution` is an expression of the
decision space. In case of combinatorial optimisation, `Solution` can
be a particular combinatorial structure.

`Solution` instances are always associated to a problem instance,
hence they have a reference to one such an instance. Additionally,
associated to a `Solution` instance there is its evaluation value,
that we assume to be of `float` type.

Candidate solutions define the elementary decisions (or *components*)
from the decision space. For example, in a problem that asks to
determine the value of a set of decision variables taken from their
domains an elementary decision is the value assigned to a single
variable. Candidate solutions can be restricted to be *complete*, in
that all its elementary decisions are defined. Alternatively, they can
be allowed to include *partial* solutions where only a subset of
components is defined. This distinction is not always relevant. For
some problems where it makes sense for candidate solutions to be
defined as sets the number of components is not known a priori. Sets
can also be represented by indicator vectors in which case the
distinction is again relevant but the vector representation might not
be convenient for the specific problem.

Instances of `Solution` must be candidate solutions but do not need to
be *feasible*. For example, for a local search that works on complete
solutions, these solutions do not need to satisfy all constraints of
the problem but they do satisfy the requirement that all decisions are
defined, even if they may break some other problem constraints. On the
other hand, partial solutions would not be *valid* instances of
`Solution` in that they do not satisfy the internal requirement of
candidate solutions.

Candidate solutions can be direct or indirect representations of
solutions.  Indirect solution representations can be used when we can
identify a smaller decision space, such that for a given member of
this space a best corresponding solution for the original space can be
derived in polynomial time. A somehow related distinction is done in
evolutionary algorithms between genotype and phenotype. In this case,
candidate solutions represent commonly genotypes.

<!-- Structural state vs evaluation state vs ???

MC: I do not get what this means -->

Note, particular information used by the optimisation algorithm - tabu
lists, pheromone matrix, etc - must be stored on the algorithm's side.

However, `Solution` may contain auxiliary data structures to
facilitate calculations, for example, of increments.

## Use cases

All algorithms need to be able to define, take as input and return as
output instances of type `Solution`. Moreover, they need to be able to
modify them via neighbourhoods and their moves.

## See also

[Problem](./Problem.md),
[Neighbourhood](./Neighbourhood.md),
[Move](./Move.md),
[empty\_solution](../operations/empty_solution.md),
[random\_solution](../operations/random_solution.md),
[copy\_solution](../operations/copy_solution.md),
[lower\_bound](../operations/lower_bound.md),
[objective\_value](../operations/objective_value.md),
[moves](../operations/moves.md),
[apply\_move](../operations/apply_move.md).
