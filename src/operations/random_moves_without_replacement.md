<!--
SPDX-FileCopyrightText: © 2025 Authors of the ROAR-NET API Specification <https://github.com/roar-net/roar-net-api-spec/blob/main/AUTHORS>

SPDX-License-Identifier: CC-BY-4.0
-->

# Random moves without replacement

## Signature

```text
random_moves_without_replacement(Neighbourhood, Solution) : Move[0..*]
```

## Description

This function provides for the complete enumeration of the neighbours
of a given solution by producing a sequence of moves in random order.

## Pre-requisites

Both the given neighbourhood structure and the given solution must
pertain to the same problem instance.

## Use cases

Sampling at random without replacement is appropriate when the
optimisation algorithm explores the set of neighbours of a solution
sequentially and may decide to stop the exploration and proceed some
other way after seeing each move. In this case, the order in which
moves are presented may influence how long such a partial exploration
takes. Sampling at random without replacement avoids the bias inherent
to deterministic enumeration, while still allowing completion of the
exploration to be detected.

First-improvement local search is an example of an algorithm where
moves are typically accepted before the whole set of neighbours is
explored, but complete exploration is still performed in case no
improving move is found.

## See also

[Neighbourhood](../types/Neighbourhood.md),
[Solution](../types/Solution.md),
[Move](../types/Move.md),
[moves](./moves.md),
[apply\_move](./apply_move.md).
