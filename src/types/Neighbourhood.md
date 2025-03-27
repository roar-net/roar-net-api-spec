<!--
SPDX-FileCopyrightText: © 2025 Authors of the ROAR-NET API Specification <https://github.com/roar-net/roar-net-api-spec/blob/main/AUTHORS>

SPDX-License-Identifier: CC-BY-4.0
-->

# Neighbourhood

## Signature

```text
Neighbourhood
```

## Description

The `Neighbourhood` type represents a particular neighbourhood
structure defined over the decision space of a given problem
instance. Neighbourhood structures are constructive or destructive if
they work with partial candidate solutions and local if they work with
complete solutions.  Constructive neighbourhood structures consist of
changes that add components to partial candidate solutions yielding
partial or complete solutions.  Destructive neighbourhoods structures
consist of changes that remove components from complete or partial
solutions yielding partial solutions. Local neighbourhood structures
consist of changes that leave solutions complete.

Formally, a neighbourhood structure \\(\cal N\\) can be defined as:

- a function \\(N : S_{\pi} \to 2^{S_{\pi}}\\)
- a function \\(N : S_{\pi} \times S_{\pi} \to \{T , F \} \\)
- a subset of pairs of candidate solutions \\(N \subseteq S_{\pi}
  \times S_{\pi}\\)
- a subset of candidate solutions for every solution \\(s\\): \\(N(s)
  := \{s' \in S \| N (s, s')\}\\)

Neighbourhoods are also characterised by:

- their size defined as \\(|N(s)|\\)
- symmetricity if \\(s' \in N(s) \implies s \in N(s')\\)
- neighbourhood graph of \\(\(S, N, \pi\)\\) a directed graph: \\(G_N
  := (V , A)\\) with \\(V = S\\) and \\((uv) \in A \iff v \in N(u)\\)
  (if symmetric neighbourhood then undirected graph)

## Use cases

The algorithms will need to access the `Neighbourhood` instances
associated with the problem. The related operations
`construction_neighbourhood`, `destruction_neighbourhood` and
`local(-search)-neighbourhoods` are used by algorithms to determine
the instances of the `Neighbourhood` types implemented.

## See also

[Problem](./Problem.md),
[Solution](./Solution.md),
[Move](./Move.md),
[construction\_neighbourhood](../operations/construction_neighbourhood.md),
[destruction\_neighbourhood](../operations/destruction_neighbourhood.md),
[local\_neighbourhood](../operations/local_neighbourhood.md),
[moves](../operations/moves.md).
