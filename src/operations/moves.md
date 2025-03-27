<!--
SPDX-FileCopyrightText: © 2025 Authors of the ROAR-NET API Specification <https://github.com/roar-net/roar-net-api-spec/blob/main/AUTHORS>

SPDX-License-Identifier: CC-BY-4.0
-->

# Moves

## Signature

```text
moves(Neighbourhood, Solution) : Move[0..*]
```

## Description

This function provides for the complete enumeration of the neighbours
of a given solution by producing a sequence of moves in unspecified
order.

## Pre-requisites

Both the given neighbourhood structure and the given solution must
pertain to the same problem instance.

## Use cases

Move enumeration is appropriate when the optimisation algorithm
performs a full exploration of the set of neighbours of a solution
before deciding how to proceed. In this case, enumeration order is
irrelevant to the algorithm.

Greedy construction with random tie breaking and best-improvement
local search are examples of algorithms where the whole set of
neighbours is explored before the next move is accepted or the
algorithm stops.

## See also

[Neighbourhood](../types/Neighbourhood.md),
[Solution](../types/Solution.md),
[Move](../types/Move.md),
[random\_moves\_without\_replacement](./random_moves_without_replacement.md),
[apply\_move](./apply_move.md).
