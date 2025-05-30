<!--
SPDX-FileCopyrightText: © 2025 Authors of the ROAR-NET API Specification <https://github.com/roar-net/roar-net-api-spec/blob/main/AUTHORS>

SPDX-License-Identifier: CC-BY-4.0
-->

# Move

```text
Move
```

## Description

The `Move` type identifies the changes between two neighbouring
solutions.  Formally, for a problem instance \\(\pi\\), candidate
solution space \\(S_{\pi}\\), and a neighbourhood structure \\({\cal
N}(\pi) \subseteq \(S\times S\)\\), there is an instance of `Move` for
every pair of candidate solutions, \\(s, s' \in S\\), \\(s,s'\\) in
\\(\cal N(\pi)\\) containing the information used by an operator
function \\(\delta\\) that applied to \\(s\\) yields \\(s'\\), that
is, \\(s'=\delta(s)\\). The operation `apply` implements the operator
function.

It follows that a particular neighbourhood structure \\({\cal N}(\pi)
\subseteq \(S\times S\)\\) can be fully represented by a collection of
operator functions \\(\Delta\\) and that for each candidate solution
\\(s\in S\\) the neighbourhood set \\(N(s)\\) associated to \\(\cal
N\\) is generated by a subset of operator functions \\(\Delta(s)
\subseteq \Delta\\). Hence, \\(s'\in N(s) \iff
s'=\delta(s),\delta\in\Delta(s)\\). For each solution \\(s\\) the
operator functions \\(\delta \in \Delta(s)\\) are described by a set
of instantiations of `Moves` that is generated by move generators,
like the operations `moves`.

As an example, for candidate solutions that are linear permutations, a
possible neighbourhood structure defines as neighbouring two solutions
if they differ only in the position of two adjacent elements in the
permutation. This neighbourhood structure can be represented by a
`Move` with information about the position of the first element to
swap. The operator function that uses this information will change the
element indexed by `Move` with the following element in the
permutation. The generator `moves` will instantiate all moves that are
needed to reach all neighbouring solutions. In this case, there are as
many moves as are the elements in the permutation each specifying a
different index.

## Use cases

Each neighbourhood structure defines its own moves that are generated
by move generators such as `moves` and are used by the operator
`apply` to implement the changes to the solution. Hence, we need a
different definition for `Move`, `moves` and `apply` for each
neighbourhood structure.

## See also

[Neighbourhood](./Neighbourhood.md),
[Solution](./Solution.md),
[moves](../operations/moves.md),
[apply\_move](../operations/apply_move.md),
[invert\_move](../operations/invert_move.md),
[lower\_bound\_increment](../operations/lower_bound_increment.md),
[objective\_value\_increment](../operations/objective_value_increment.md).
