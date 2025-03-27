<!--
SPDX-FileCopyrightText: © 2025 Authors of the ROAR-NET API Specification <https://github.com/roar-net/roar-net-api-spec/blob/main/AUTHORS>

SPDX-License-Identifier: CC-BY-4.0
-->

# Lower-bound increment

## Signature

```text
lower_bound_increment(Move, Solution) : double[0..1]
```

## Description

This function produces the difference between the lower bound of the
solution that would be obtained by applying the given move to the
given solution and the lower bound of the given solution. If lower
bound of either solution is undefined, the lower-bound increment is
also undefined, and this function produces no value.

Since it is assumed that the objective function is to be minimised,
the lower-bound increment resulting from a construction move cannot be
negative, and that resulting from a destruction move cannot be
positive.

## Pre-requisites

The given move must have been generated under some neighbourhood
structure for the given solution or a pristine copy of it, or be the
inverse of the move that produced the given solution.

## Use cases

The lower-bound increment provides a heuristic measure of move quality
in constructive search. In algorithms such as GRASP, construction
moves typically consist of adding components to the current solution,
and move quality is often seen as an attribute of the components
themselves. The lower-bound increment provides a more general, drop-in
replacement for such move-quality heuristics in constructive search.

Determining the lower-bound increment can often be performed faster
than applying a move to a solution and computing the difference
between the two lower-bound values. This avoids spending time applying
moves to solutions that will be discarded immediately, and motivates
further investment in efficient lower-bound increment evaluation, even
if at the expense of some additional processing when moves are applied
to solutions.

## See also

[Solution](../types/Solution.md),
[Neighbourhood](../types/Neighbourhood.md),
[Move](../types/Move.md),
[lower\_bound](./lower_bound.md),
[objective\_value](./objective_value.md),
[objective\_value\_increment](./objective_value_increment.md).
