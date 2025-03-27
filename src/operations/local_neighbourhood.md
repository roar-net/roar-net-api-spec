<!--
SPDX-FileCopyrightText: © 2025 Authors of the ROAR-NET API Specification <https://github.com/roar-net/roar-net-api-spec/blob/main/AUTHORS>

SPDX-License-Identifier: CC-BY-4.0
-->

# Local neighbourhood

## Signature

```text
local_neighbourhood(Problem) : Neighbourhood
```

## Description

This function returns the local neighbourhood structure of the given
problem instance. In a local-search model of a combinatorial
optimisation problem, the local neighbourhood structure specifies
which feasible solutions, or neighbours, can be obtained from each
feasible solution by means of a "small" modification.  The notion of
local optimum is intrinsically tied to the definition of such a
neighbourhood.

## Use cases

A local neighbourhood structure is required by all local search
approaches, including but not limited to best-improvement,
first-improvement and iterated local search, tabu search and
evolutionary algorithms.

## See also

[Problem](../types/Problem.md),
[Neighbourhood](../types/Neighbourhood.md).
