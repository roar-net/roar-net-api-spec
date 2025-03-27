<!--
SPDX-FileCopyrightText: © 2025 Authors of the ROAR-NET API Specification <https://github.com/roar-net/roar-net-api-spec/blob/main/AUTHORS>

SPDX-License-Identifier: CC-BY-4.0
-->

# Apply move

## Signature

```text
apply_move(Move, Solution) : Solution
```

## Description

This function applies a move to a solution in order to produce the
corresponding neighbour.

## Pre-requisites

The given move must have been generated under some neighbourhood for
the given solution or a pristine copy of it, or be the inverse of the
move that produced the given solution.

## Use cases

Applying moves to solutions is required by all optimisation algorithms
in order to visit new solutions.

## See also

[Move](../types/Move.md),
[Solution](../types/Solution.md),
[invert\_move](./invert_move.md),
[moves](./moves.md).
