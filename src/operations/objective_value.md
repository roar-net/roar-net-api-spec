<!--
SPDX-FileCopyrightText: © 2025 Authors of the ROAR-NET API Specification <https://github.com/roar-net/roar-net-api-spec/blob/main/AUTHORS>

SPDX-License-Identifier: CC-BY-4.0
-->

# Objective value

## Signature

```text
objective_value(Solution) : double[0..1]
```

## Description

This function produces the value of the objective function at the
given solution if the solution is feasible, and no value otherwise. A
solution is feasible if it satisfies all constraints of the
problem. The objective value of an infeasible solution is undefined.

In general, both complete and partial solutions may be feasible or
infeasible.  Feasible partial solutions are common, for example, in
models of the knapsack problem, as even an empty knapsack is a
feasible solution. Infeasible complete solutions may arise, for
example, when constructing solutions for the travelling salesman
problem on incomplete graphs.

Evaluation of the objective function must occur before this function
returns, but the time at which the evaluation actually occurs is
otherwise unspecified.

It is assumed that the objective function is to be minimised.

## Use cases

Objective-value evaluation is required by all optimisation algorithms.

## See also

[Solution](../types/Solution.md),
[lower\_bound](./lower_bound.md),
[objective\_value\_increment](./objective_value_increment.md).
