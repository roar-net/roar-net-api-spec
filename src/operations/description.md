<!--
SPDX-FileCopyrightText: © 2025 Authors of the ROAR-NET API Specification <https://github.com/roar-net/roar-net-api-spec/blob/main/AUTHORS>

SPDX-License-Identifier: CC-BY-4.0
-->

# Description

## Signature

```text
description(Problem | Neighbourhood | Feature) : string
```

## Description

This polymorphic function produces a natural-language description of the
given problem-modelling component:

- When applied to a `Problem` instance, it outlines the domain context,
  the structure of candidate solutions, the problem constraints, and the
  objective function to be minimised.
- When applied to a `Neighbourhood` instance, it specifies the
  transition rule defining neighbouring solutions (for example, how a
  construction neighbourhood extends a partial solution at each step).
- When applied to a `Feature` instance, it explains the domain meaning
  of the feature, its value type (`double`, `int`, or `bool`), and how
  it characterises a candidate `Move` in the context of a `Solution`.

## Use cases

Natural-language descriptions provide structured semantic context to
hyper-heuristics, most notably Large Language Model (LLM)
hyper-heuristics, without exposing internal data structures or breaking
the black-box separation between problem modelling and optimisation
algorithms. They also serve as self-contained documentation for
interpreting symbolic heuristics discovered by Genetic Programming (GP).

## See also

[Problem](../types/Problem.md),
[Neighbourhood](../types/Neighbourhood.md),
[Feature](../types/Feature.md),
[features](./features.md),
[feature\_name](./feature_name.md),
[feature\_value](./feature_value.md).
