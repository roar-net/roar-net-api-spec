<!--
SPDX-FileCopyrightText: © 2025 Authors of the ROAR-NET API Specification <https://github.com/roar-net/roar-net-api-spec/blob/main/AUTHORS>

SPDX-License-Identifier: CC-BY-4.0
-->

# Heuristic solution

## Signature

```text
heuristic_solution(Problem) : Solution[0..1]
```

## Description

This function produces a feasible solution for the given problem
instance or none if the underlying heuristic fails to generate such a
solution.

## Use cases

Heuristic solutions are often used as initial solutions in local
search.

## See also

[Problem](../types/Problem.md),
[Solution](../types/Solution.md).
