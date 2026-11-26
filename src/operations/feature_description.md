<!--
SPDX-FileCopyrightText: © 2025 Authors of the ROAR-NET API Specification <https://github.com/roar-net/roar-net-api-spec/blob/main/AUTHORS>

SPDX-License-Identifier: CC-BY-4.0
-->

# Feature description

## Signature

```text
feature_description(Feature) : string
```

## Description

This function produces a natural-language description of the given
`Feature`, explaining its domain meaning, its value type (`double`,
`int`, or `bool`), and how it relates to the candidate `Move` and
`Solution`.

## Use cases

Natural-language feature descriptions allow Large Language Model (LLM)
hyper-heuristics to understand the semantic meaning of each available
feature in a neighbourhood without breaking the black-box encapsulation
of the problem model. They also serve as self-contained documentation
for interpreting symbolic heuristics discovered by Genetic Programming
(GP).

## See also

[Feature](../types/Feature.md),
[Neighbourhood](../types/Neighbourhood.md),
[features](./features.md),
[feature\_name](./feature_name.md),
[feature\_value](./feature_value.md),
[problem\_description](./problem_description.md).
