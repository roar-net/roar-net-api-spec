<!--
SPDX-FileCopyrightText: © 2025 Authors of the ROAR-NET API Specification <https://github.com/roar-net/roar-net-api-spec/blob/main/AUTHORS>

SPDX-License-Identifier: CC-BY-4.0
-->

# Problem

## Signature

```text
Problem
```

## Description

The type `Problem` specifies the data structure to represent the
particular *instance* of the problem to solve.  An instance of a
problem is the definition of the data related to the specific example
of the abstract problem to solve.  Data can be numerical or
categorical values and specify, for example, the size of solutions,
the presence or not of particular constraints, the values of
coefficients in mathematical constraints or objectives.

## Use cases

In the travelling salesman problem, `Problem` is a data structure
containing at least the number of nodes to visit and the matrix of
distances between the nodes. If the instance is geographical then the
distance matrix can be replaced by the GPS coordinates of the nodes
and by the formula to calculate the distance (Euclidean, haversine).

If the problem is finding the inputs to a simulator that yield the
desired results then the instance may be the number of parameters
input to the simulator and their domain. If these parameters are
conditioned over other parameters then the values of the conditioning
parameters must be defined in `Problem`.

## See also

[Solution](./Solution.md),
[Neighbourhood](./Neighbourhood.md),
[empty\_solution](../operations/empty_solution.md),
[random\_solution](../operations/random_solution.md),
[construction\_neighbourhood](../operations/construction_neighbourhood.md),
[destruction\_neighbourhood](../operations/destruction_neighbourhood.md),
[local\_neighbourhood](../operations/local_neighbourhood.md).
