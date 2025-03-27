<!--
SPDX-FileCopyrightText: © 2025 Authors of the ROAR-NET API Specification <https://github.com/roar-net/roar-net-api-spec/blob/main/AUTHORS>

SPDX-License-Identifier: CC-BY-4.0
-->

# Random solution

## Signature

```text
random_solution(Problem) : Solution
```

## Description

This function samples the feasible decision space of the given problem
instance uniformly at random (with replacement) and produces a
feasible solution.

## Use cases

Random solutions are often used as initial solutions in local
search. The initial population of evolutionary algorithms typically
consists of solutions generated at random.

## See also

[Problem](../types/Problem.md),
[Solution](../types/Solution.md).
