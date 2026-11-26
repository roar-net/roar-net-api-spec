<!--
SPDX-FileCopyrightText: © 2025 Authors of the ROAR-NET API Specification <https://github.com/roar-net/roar-net-api-spec/blob/main/AUTHORS>

SPDX-License-Identifier: CC-BY-4.0
-->

# Features

## Signature

```text
features(Neighbourhood) : Feature[0..*]
```

## Description

This function returns the sequence of `Feature` instances associated
with the given neighbourhood structure. Each `Feature` encapsulates an
elementary domain descriptor of a move and candidate solution under
this neighbourhood that can be evaluated on demand via `feature_value`.

## Use cases

Retrieving the available features of a neighbourhood, currently only
supported for constructive neighborhood, required by generative
hyper-heuristics:

- **Genetic Programming (GP)** hyper-heuristics query `features` to
  construct the terminal set from which symbolic move-scoring rules
  (priority functions) are evolved.
- **Large Language Model (LLM)** hyper-heuristics query `features` and
  inspect each feature's identifier (`feature_name`) and specification
  (`description`) to construct prompts for automated heuristic
  synthesis.

Because this operation returns `Feature` descriptors rather than
pre-computed feature values, no feature evaluations are performed until
`feature_value` is explicitly invoked on a specific `Feature`, `Move`,
and `Solution`.

## See also

[Neighbourhood](../types/Neighbourhood.md),
[Feature](../types/Feature.md),
[Move](../types/Move.md),
[Solution](../types/Solution.md),
[construction\_neighbourhood](./construction_neighbourhood.md),
[description](./description.md),
[feature\_value](./feature_value.md),
[feature\_name](./feature_name.md).
