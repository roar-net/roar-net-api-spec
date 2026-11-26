<!--
SPDX-FileCopyrightText: © 2025 Authors of the ROAR-NET API Specification <https://github.com/roar-net/roar-net-api-spec/blob/main/AUTHORS>

SPDX-License-Identifier: CC-BY-4.0
-->

# Feature

## Signature

```text
Feature
```

## Description

The `Feature` type represents an elementary descriptor or
domain-specific attribute of a candidate transition under a given
neighbourhood structure. Formally, for a problem instance \\(\pi\\),
candidate solution space \\(S_{\pi}\\), and a neighbourhood structure
\\({\cal N}(\pi) \subseteq (S_{\pi} \times S_{\pi})\\) whose transitions
from any solution \\(s \in S_{\pi}\\) are described by a set of moves
\\(\Delta(s)\\), an instance of `Feature` defines a partial mapping

\\[\phi : \\{(m, s) \mid s \in S_{\pi},\; m \in \Delta(s)\\}
\rightharpoonup V\\]

where the codomain \\(V = \mathbb{R} \cup \mathbb{Z} \cup
\\{\text{true}, \text{false}\\}\\) comprises numerical (continuous or
discrete) and Boolean values. The operation `feature_value` implements
the evaluation of \\(\phi(m, s)\\). Depending on the feature definition,
\\(\phi(m, s)\\) may depend on properties of the move \\(m\\), the
current candidate solution \\(s\\), the underlying problem instance
\\(\pi\\), or their interaction.

By encapsulating domain attributes as first-class `Feature` instances
associated with a `Neighbourhood`, the API preserves the strict
black-box separation between problem modelling and optimisation
algorithms:

- **On-demand (lazy) evaluation**: A neighbourhood may expose a rich
  catalogue of features via the operation `features`, ranging from
  inexpensive \\(O(1)\\) lookups to more informative structural
  lookahead indicators. Rather than evaluating all features eagerly for
  every candidate move, an optimisation algorithm or scoring function
  evaluates only the subset of `Feature` instances it actually requires
  via `feature_value`.
- **Semantic self-description**: Each `Feature` instance is accompanied
  by a unique identifier (`feature_name`) and a natural-language
  specification (`description`). This allows symbolic and
  language-model-based hyper-heuristics to reason about the domain
  semantics of each feature without accessing internal data structures
  of `Problem`, `Solution`, or `Move`.
- **Compositional closure**: A heuristic move-scoring function (or
  *priority rule*) \\(h(m, s) \to \mathbb{R}\\) that combines multiple
  features through arithmetic and logical operators shares the same
  evaluation interface as an elementary numerical `Feature`.

As an example, in a constructive model of the travelling salesman
problem where a partial tour is extended by appending an unvisited node,
the construction neighbourhood may provide `Feature` instances for:

- the distance from the last visited node to the candidate node
  (`double`),
- the distance from the candidate node back to the starting node
  (`double`),
- the minimum distance from the candidate node to any remaining
  unvisited node (`double`),
- the fraction of nodes already visited in the partial solution
  (`double`), and
- whether the candidate move completes the tour (`bool`).

## Use cases

Instances of `Feature` serve as the building blocks for
**hyper-heuristics**, particularly generative hyper-heuristics for
constructive search:

- In **Genetic Programming (GP)** hyper-heuristics, the `Feature`
  instances provided by a construction neighbourhood form the *terminal
  set* of syntax trees (or graphs) that are evolved to synthesise
  priority rules for ordering candidate construction moves.
- In **Large Language Model (LLM)** hyper-heuristics, the names and
  descriptions of the `Feature` instances provide structured domain
  context for prompting the model to synthesise executable move-scoring
  functions, which evaluate candidate moves on demand via
  `feature_value`.

## See also

[Problem](./Problem.md),
[Solution](./Solution.md),
[Neighbourhood](./Neighbourhood.md),
[Move](./Move.md),
[description](../operations/description.md),
[features](../operations/features.md),
[feature\_value](../operations/feature_value.md),
[feature\_name](../operations/feature_name.md),
[lower\_bound\_increment](../operations/lower_bound_increment.md),
[objective\_value\_increment](../operations/objective_value_increment.md).
