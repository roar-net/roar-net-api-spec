<!--
SPDX-FileCopyrightText: © 2025 Authors of the ROAR-NET API Specification <https://github.com/roar-net/roar-net-api-spec/blob/main/AUTHORS>

SPDX-License-Identifier: CC-BY-4.0
-->

# Construction neighbourhood

## Signature

```text
construction_neighbourhood(Problem) : Neighbourhood
```

## Description

This function returns the construction neighbourhood structure of the
given problem instance. In a constructive-search model of a
combinatorial optimisation problem, the construction neighbourhood
structure, or construction rule, specifies how partial solutions,
including empty solutions, may be made progressively more complete
until a complete solution is reached.

## Use cases

A construction neighbourhood structure is required by all constructive
search approaches, including but not limited to greedy construction
and ruin and recreate.

## See also

[Problem](../types/Problem.md),
[Neighbourhood](../types/Neighbourhood.md),
[destruction\_neighbourhood](./destruction_neighbourhood.md),
[empty\_solution](./empty_solution.md).
