<!--
SPDX-FileCopyrightText: © 2025 Authors of the ROAR-NET API Specification <https://github.com/roar-net/roar-net-api-spec/blob/main/AUTHORS>

SPDX-License-Identifier: CC-BY-4.0
-->

# Copy solution

## Signature

```text
copy_solution(Solution) : Solution
```

## Description

This function produces a copy of the given solution.

## Use cases

Making copies of solutions may be required when keeping track of the
best solution found so far. It is also required by optimisation
algorithms such as beam search and evolutionary algorithms.

## See also

[Solution](../types/Solution.md).
