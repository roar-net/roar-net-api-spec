<!--
SPDX-FileCopyrightText: © 2025 Authors of the ROAR-NET API Specification <https://github.com/roar-net/roar-net-api-spec/blob/main/AUTHORS>

SPDX-License-Identifier: CC-BY-4.0
-->

# ROAR-NET API Specification

## About ROAR-NET API

The ROAR-NET API defines a **framework for black-box optimisation
problem modelling**. It is based on abstractions aimed at unifying
black-box optimisation problems, and on a clear **separation between
problem modelling and randomised optimisation algorithms**. The
resulting standardisation of black-box problem modelling leads to the
following advantages:

- Different optimisation algorithms can operate on the same problem
  model, e.g., branch-and-bound and local-search.
- Different optimisation problems (or models) can be solved by the same
  algorithms.

## Conceptualisation

The goal of this specification is to define a minimal,
programming-language agnostic, interface to the optimisation problems
that a wide variety of **Randomised Optimisation Algorithms (ROAs)** can
use to solve these problems. In doing this, the specification should
facilitate modelling of real life problems that can be solved by a wide
range of algorithms and make it possible to easily benchmark problem
models and ROAs.

The specification defines the **types** and **operations** that have to
be implemented when modelling an optimisation problem in order to allow
supported ROAs to function.

The API specification has the following design principles:

- it is **agnostic of the programming language**.
- it is **agnostic of the programming paradigm**.
- requires implementations of the API to **only store problem-specific
  information**. They must be completely free of any information about
  the optimisation algorithm to be used.

## Supported features

The API supports a broad range of problems and Randomised Optimisation
Algorithms (ROAs).  The current version of the specification covers, but
is not limited to, the following classes of **single-objective**
optimisation problems:

- **combinatorial problems**
- **discrete problems**

Furthermore, it considers the following main algorithmic approaches:

- **Constructive search**: solutions are constructed iteratively. For
  example, by adding a component, or assigning the value of a decision
  variable, on each iteration.
  - Example of algorithms include, backtracking, branch-and-bound,
    greedy algorithms, and GRASP.
  - Some of these algorithms may provide guarantees on the quality of
    the solution.
- **Local search**: solutions are found by modifying feasible
  solutions. For example, by exchanging some components of the solution,
  or changing the value of a decision variable.
  - Examples of algorithms include, first and best improvement local
    search, iterated local search, and simulated annealing.
  - These algorithms typically do not provide a guarantee on the quality
    of the solution found but are usually able to find good
    approximations in a reasonable amount of time.

Extensions to multiple objectives, uncertainty settings, and support for
further algorithms are currently under discussion on the [Github
repository](https://github.com/roar-net/roar-net-api-spec),
where everyone is welcome to contribute and propose new ideas.

## Acknowledgement

This specification is based upon work from COST Action [Randomised
Optimisation Algorithms Research Network
(ROAR-NET)](https://www.roar-net.eu/), CA22137, supported by COST
(European Cooperation in Science and Technology).

COST ([European Cooperation in Science and
Technology](https://www.cost.eu)) is a funding agency for research and
innovation networks. Our Actions help connect research initiatives
across Europe and enable scientists to grow their ideas by sharing them
with their peers. This boosts their research, career and innovation.

<br/>
<img
  src="https://raw.githubusercontent.com/roar-net/.github/refs/heads/main/images/costeu.png"
  alt="COST and European Union Logos"
  width=460px
/>
