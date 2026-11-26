<!--
SPDX-FileCopyrightText: © 2025 Authors of the ROAR-NET API Specification <https://github.com/roar-net/roar-net-api-spec/blob/main/AUTHORS>

SPDX-License-Identifier: CC-BY-4.0
-->

# Problem description

## Signature

```text
problem_description(Problem) : string
```

## Description

This function produces a natural-language description of the given
optimisation problem instance, outlining the domain context, the
structure of candidate solutions, the problem constraints, and the
objective function to be minimised.

## Use cases

A natural-language description of the problem provides domain semantics
to language-model-based hyper-heuristics without exposing the internal
implementation details of `Problem`, `Solution`, or `Move`. When
combined with `features`, `feature_name`, and `feature_description`,
this operation enables Large Language Models (LLMs) to synthesise
context-aware move-scoring functions for constructive search.

## See also

[Problem](../types/Problem.md),
[Feature](../types/Feature.md),
[features](./features.md),
[feature\_name](./feature_name.md),
[feature\_description](./feature_description.md).
