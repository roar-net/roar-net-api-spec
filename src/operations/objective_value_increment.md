<!--
SPDX-FileCopyrightText: © 2025 Authors of the ROAR-NET API Specification <https://github.com/roar-net/roar-net-api-spec/blob/main/AUTHORS>

SPDX-License-Identifier: CC-BY-4.0
-->

# Objective-value increment

## Signature

```text
objective_value_increment(Move, Solution) : double[0..1]
```

## Description

This function produces the difference between the value of the
objective function at the solution that would be obtained by applying
the given move to the given solution and the corresponding value at
the given solution. If either solution is infeasible, the
objective-value increment is undefined, and this function produces no
value.

It is assumed that the objective function is to be minimised.

## Pre-requisites

The given move must have been generated under some neighbourhood
structure for the given solution or a pristine copy of it, or be the
inverse of the move that produced the given solution.

## Use cases

The objective-value increment provides a measure of move quality,
especially in local-search algorithms, but also in constructive search
algorithms.

Determining the objective-value increment can often be performed
faster than applying a move to a solution and computing the difference
between the two objective values. This avoids spending time applying
moves to solutions that will be discarded immediately, and motivates
further investment in efficient objective-value increment evaluation,
even if at the expense of some additional processing when moves are
applied to solutions.

## See also

[Solution](../types/Solution.md),
[Neighbourhood](../types/Neighbourhood.md),
[Move](../types/Move.md),
[objective\_value](./objective_value.md),
[apply\_move](./apply_move.md).
