<!--
SPDX-FileCopyrightText: © 2025 Authors of the ROAR-NET API Specification <https://github.com/roar-net/roar-net-api-spec/blob/main/AUTHORS>

SPDX-License-Identifier: CC-BY-4.0
-->

# Random move

## Signature

```text
random_move(Neighbourhood, Solution) : Move[0..1]
```

## Description

This function provides for the random sampling of the neighbours of a
given solution by producing a move drawn uniformly at random from the
set of possible moves for that solution under the given neighbourhood
structure or none if no such moves exist.

## Pre-requisites

Both the given neighbourhood structure and the given solution must
pertain to the same problem instance.

## Use cases

Sampling moves uniformly at random is appropriate when only a partial
exploration of the set of neighbours of a solution is performed by the
optimisation algorithm. In this case, complete exploration of that set
is neither expected nor detected.

Randomised local search (RLS) and most evolutionary algorithms are
examples of algorithms where a single move for each solution is
typically generated at random and immediately applied.

## See also

[Neighbourhood](../types/Neighbourhood.md),
[Solution](../types/Solution.md),
[Move](../types/Move.md),
[moves](./moves.md),
[apply\_move](./apply_move.md).
