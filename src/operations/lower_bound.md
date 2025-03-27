<!--
SPDX-FileCopyrightText: © 2025 Authors of the ROAR-NET API Specification <https://github.com/roar-net/roar-net-api-spec/blob/main/AUTHORS>

SPDX-License-Identifier: CC-BY-4.0
-->

# Lower bound

## Signature

```text
lower_bound(Solution) : double[0..1]
```

## Description

This function produces a lower bound on the value taken by the
objective function at any feasible solution that can be obtained by
applying construction moves to the given, presumably partial,
solution. If it is known that no feasible solution can be obtained by
further construction, this function should produce no value.

Evaluation of the lower bound must occur before this function returns,
but the time at which the evaluation actually occurs is otherwise
unspecified.

It is assumed that the objective function is to be minimised.

## Use cases

Lower bounds are typically used in constructive search to guide
solution construction or to stop it early (also known as *pruning*) by
signalling that a better feasible solution than the best one known so
far can no longer be constructed from a given partial solution.

Lower-bound functions are strongly related to the notion of
*admissible heuristics* in computer science.

## See also

[Solution](../types/Solution.md),
[Neighbourhood](../types/Neighbourhood.md),
[Move](../types/Move.md),
[objective\_value](./objective_value.md),
[empty\_solution](./empty_solution.md),
[apply\_move](./apply_move.md),
[lower\_bound\_increment](./lower_bound_increment.md).
