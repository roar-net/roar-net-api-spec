<!--
SPDX-FileCopyrightText: © 2025 Authors of the ROAR-NET API Specification <https://github.com/roar-net/roar-net-api-spec/blob/main/AUTHORS>

SPDX-License-Identifier: CC-BY-4.0
-->

# Destruction neighbourhood

## Signature

```text
destruction_neighbourhood(Problem) : Neighbourhood
```

## Description

This function returns the destruction neighbourhood structure of the
given problem instance. In a constructive-search model of a
combinatorial optimisation problem, the destruction neighbourhood
structure, or destruction rule, dictates how complete or partial
solutions may be made progressively less complete until an empty
solution is reached.

## Use cases

A destruction neighbourhood structure is required by some constructive
search approaches, such as ruin and recreate.

## See also

[Problem](../types/Problem.md),
[Neighbourhood](../types/Neighbourhood.md),
[construction\_neighbourhood](./construction_neighbourhood.md),
[empty\_solution](./empty_solution.md).
