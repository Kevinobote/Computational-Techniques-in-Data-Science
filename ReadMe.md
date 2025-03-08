# Week 1: Stochastic Programming

## Introduction
Stochastic programming is a framework for modeling optimization problems that involve uncertainty. Unlike deterministic optimization problems, where all parameters are known with certainty, stochastic programming handles scenarios where certain parameters are random variables with known probability distributions.

## Key Concepts

### Decision Variables
In stochastic programming, decision variables represent the quantities we want to optimize. These can be continuous (like investment amounts) or discrete (like binary yes/no decisions). The optimal values of these variables are what we're solving for.

### Scenarios and Probabilities
A fundamental concept in stochastic programming is modeling uncertainty through scenarios. Each scenario represents a possible future state, with an associated probability of occurrence. The collection of all scenarios and their probabilities forms a discrete approximation of the underlying continuous probability distribution.

### Cost Functions
The cost function (or objective function) in stochastic programming often involves:
- Expected value calculations across scenarios
- Risk measures
- Penalty terms for constraints that might be violated under certain scenarios

Common operators include:
- `cp.pos()`: Represents max(x, 0), useful for modeling one-sided costs or penalties
- `cp.multiply()`: Element-wise multiplication, often used with probability vectors
- `cp.sum()`: Summation operation, used to compute total costs or expected values

### Constraints
Constraints in stochastic programming can be:
- First-stage constraints: Applied before uncertainty is revealed
- Second-stage constraints: Applied after uncertainty is revealed, possibly different for each scenario
- Non-negativity constraints: Ensuring variables take only meaningful values

## Example Applications

### Newsvendor Problem
A classic stochastic optimization problem where a vendor must decide how many items to stock before knowing the exact demand. The goal is to minimize the expected cost considering:
- Overstocking costs (items left unsold)
- Understocking costs (missed sales opportunities)

The optimal decision balances these competing costs based on the probability distribution of demand scenarios.

### Portfolio Optimization
Portfolio optimization involves allocating investments across different assets to maximize expected return while controlling risk. In the stochastic programming framework:

- **Decision Variables**: Weights representing the fraction of the portfolio invested in each asset
- **Objective**: Typically maximizes expected return minus a risk term
- **Risk Measurement**: Can use variance, standard deviation, or other norm-based proxies
- **Constraints**: 
  - Budget constraint (weights sum to 1)
  - Non-negativity (no short selling)
  - Possibly other diversification constraints

The optimization balances the trade-off between expected return and risk across multiple possible future scenarios of asset returns.

## Assignment 1: Implementation and Analysis

In Assignment 1, we implemented and analyzed several stochastic programming concepts using Python:

### Implementation Highlights
- Built a stochastic programming framework using CVXPY and NumPy
- Solved the Newsvendor Problem with various demand distributions
- Performed Portfolio Optimization under uncertainty
- Visualized results using Matplotlib
- Analyzed sensitivity of solutions to changes in uncertainty parameters
- Compared deterministic solutions to stochastic solutions

### Insights Gained
- Demonstrated how accounting for uncertainty leads to more robust decisions
- Quantified the value of stochastic solutions versus deterministic approximations
- Explored the computational challenges in solving multi-stage stochastic programs
- Examined trade-offs between solution quality and computational complexity

## Mathematical Formulation
A standard form of a stochastic optimization problem is:

```
minimize E[f(x, ξ)]
subject to:
    g(x) ≤ 0
    h(x, ξ) ≤ 0
```

Where:
- x is the decision variable
- ξ represents random parameters
- E[·] is the expected value operator
- f is the objective function
- g represents first-stage constraints
- h represents second-stage constraints

## Solution Approaches
- **Sample Average Approximation (SAA)**: Using Monte Carlo sampling to approximate the expected value
- **Stochastic Gradient Descent**: For large-scale problems with many scenarios
- **L-shaped Method (Benders Decomposition)**: For problems with special structure
- **Progressive Hedging**: For multi-stage problems

## Software Tools
Stochastic programming problems can be modeled and solved using convex optimization libraries like CVXPY, which provides a Python interface for defining and solving convex optimization problems.