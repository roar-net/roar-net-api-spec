<!--
SPDX-FileCopyrightText: © 2025 Authors of the ROAR-NET API Specification <https://github.com/roar-net/roar-net-api-spec/blob/main/AUTHORS>

SPDX-License-Identifier: CC-BY-4.0
-->

# Inverse move

## Signature

```text
inverse_move(Neighbourhood, Move) : Move
```

## Description

This function produces the inverse of a given move. If a move can be
applied to a solution A to obtain solution B, then applying its inverse
to solution B must produce solution A. As a consequence, the inverse of
a construction move must be a valid destruction move and vice-versa.

The result must be a valid move for the corresponding solution under the
given neighbourhood structure.

## Pre-requisites

The given neighbourhood structure and the given move must pertain to the
same problem instance. Unlike the resulting inverse move, the given move
may not pertain to the given neighbourhood structure.

## Use cases

Obtaining the inverse of moves allows backtracking to be performed from
a given solution by applying the inverse of each move previously applied
to the solution in reverse order. This assumes that storing, inverting
and applying moves is generally more efficient than copying and storing
solutions.

## See also

[Move](../types/Move.md),
[apply\_move](./apply_move.md).
