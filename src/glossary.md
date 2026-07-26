<!--
SPDX-FileCopyrightText: © 2025 Authors of the ROAR-NET API Specification <https://github.com/roar-net/roar-net-api-spec/blob/main/AUTHORS>

SPDX-License-Identifier: CC-BY-4.0
-->

# Glossary

## complete solution

A solution for which all (decision) components are decided on.

## construction neighbourhood

A neighbourhood structure for partial solutions where every neighbour
solution is more complete, in the sense that more components are
decided on, and may either be a partial or a complete solution. This
means that the consecutive application of (constructive) moves to a
given partial solution will eventually lead to a complete solution.

## decision space

The domain of the optimisation problem, which contains the set of all
partial and all complete (candidate) solutions for the given problem
definition.

## destruction neighbourhood

A neighbourhood structure for partial and for complete solutions where
every neighbour solution is less complete, in the sense that less
components are decided on, and is a partial solution. This means that,
the consecutive application of (destructive) moves to a given solution
will eventually lead to an empty solution.

## empty solution

A solution for which no components are decided on.

## feasible set

The subset of the decision space consisting of all feasible solutions.

## feasible solution

A solution for which the objective function is defined.

## infeasible solution

A solution for which the objective function is undefined.

## local neighbourhood

A neighbourhood structure for solutions that are complete and
feasible, and where each neighbour solution is also complete and
feasible.

## move

A description of, or a data structure encoding, a set of changes to be
applied to a solution to obtain a neighbour solution. A move is
assumed to always be associated to some neighbourhood structure.

## neighbour

A solution that, under a given neighbourhood structure, can be
obtained by applying a set of changes (a *move*) to a given solution,
in which case the former solution is called a neighbour of the latter.

## neighbourhood size

The total number of neighbours of a given solution under a given
neighbourhood structure.

## neighbourhood structure

A description of the neighbourhood of any given solution, which relies
on a set of rules that define which solutions are neighbours of the
given solution, and the *moves* that lead to them.

## objective function

A function mapping a solution in the decision space to an element of
the objective space (in this case, a real value). Minimisation is
assumed, that is, a solution is considered better than any other
solution with a greater objective value.

## objective space

The codomain of the objective function. In this specification, the
objective space is the set of real values, \\(\mathbb{R}\\).

## partial solution

A solution for which some of the components are not decided on.

## solution

An element of the decision space. A solution is described by a set of
(decision) components, which may or may not be decided on.

<!-- TODO: To be added (in a future version?) -->
<!-- ### invalid solution -->
<!-- ### valid solution -->
