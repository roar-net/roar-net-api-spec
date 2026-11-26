<!--
SPDX-FileCopyrightText: © 2025 Authors of the ROAR-NET API Specification <https://github.com/roar-net/roar-net-api-spec/blob/main/AUTHORS>

SPDX-License-Identifier: CC-BY-4.0
-->

# Feature value

## Signature

```text
feature_value(Feature, Move, Solution) : (double | int | bool)[0..1]
```

## Description

This function evaluates the given `Feature` for the candidate transition
defined by applying the given `Move` to the given `Solution`. It
produces a numerical (`double` or `int`) or Boolean (`bool`) value
characterising the move in the context of the current solution, or no
value if the feature is undefined for that transition (for instance,
when applying the move would lead to a state from which no feasible
solution can be constructed).

Evaluation of the feature is performed on demand when this function is
called.

## Pre-requisites

The given `Feature` and the given `Move` must pertain to the same
neighbourhood structure, and the given `Move` must have been generated
under that neighbourhood structure for the given `Solution` or a
pristine copy of it.

## Use cases

In constructive search guided by a hyper-heuristic (such as a priority
rule evolved via Genetic Programming or a scoring function synthesised
by a Large Language Model), candidate moves are ranked by evaluating a
composite scoring function over elementary domain features.

Evaluating features individually via `feature_value` avoids computing
all available features of a neighbourhood for every candidate move. A
scoring function only invokes `feature_value` on the specific `Feature`
instances that appear along its active execution path, enabling both
lazy evaluation and short-circuit conditional branching over Boolean
features.

Furthermore, any composite move-scoring function that maps a `(Move,
Solution)` pair to a scalar score conforms to the same evaluation
signature as `feature_value`, allowing evolved heuristics to be treated
uniformly as composite features.

## See also

[Feature](../types/Feature.md),
[Move](../types/Move.md),
[Solution](../types/Solution.md),
[Neighbourhood](../types/Neighbourhood.md),
[description](./description.md),
[features](./features.md),
[feature\_name](./feature_name.md),
[lower\_bound\_increment](./lower_bound_increment.md),
[objective\_value\_increment](./objective_value_increment.md).
