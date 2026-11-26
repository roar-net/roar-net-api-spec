<!--
SPDX-FileCopyrightText: © 2025 Authors of the ROAR-NET API Specification <https://github.com/roar-net/roar-net-api-spec/blob/main/AUTHORS>

SPDX-License-Identifier: CC-BY-4.0
-->

# Feature name

## Signature

```text
feature_name(Feature) : string
```

## Description

This function produces a symbolic identifier string for the given
`Feature`. Within a given `Neighbourhood`, each feature returned by
`features` must have a distinct name formatted as a valid lexical
identifier (e.g., `snake_case` alphanumeric characters).

## Use cases

Symbolic feature identifiers are used to:

- label terminal nodes in Genetic Programming (GP) expression trees so
  that evolved priority rules can be rendered and inspected in a
  human-readable mathematical form, and
- bind named attributes or variables in code templates and prompts used
  by Large Language Model (LLM) hyper-heuristics.

## See also

[Feature](../types/Feature.md),
[Neighbourhood](../types/Neighbourhood.md),
[features](./features.md),
[description](./description.md),
[feature\_value](./feature_value.md).
