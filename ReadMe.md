# Week 1: Stochastic Programming

## Introduction
Stochastic programming is a mathematical framework for making decisions under uncertainty. Unlike deterministic optimization, where all parameters are fixed, stochastic programming incorporates randomness by modeling uncertain elements as random variables with known probability distributions. The goal is to find an optimal decision that performs well across various possible future scenarios.

## Key Concepts

### Decision Variables
These represent the quantities we want to optimize. For example:

- **In portfolio optimization:** The proportion of funds to invest in different assets
- **In supply chain management:** The number of units to produce or store

The objective is to determine the best values for these variables.

### Scenarios and Probabilities
Uncertainty is modeled using scenarios, each representing a possible future state of the world with an associated probability. For example:

- **Stock prices:** Might rise, fall, or stay constant, with specific probabilities
- **Demand levels:** Could be low, medium, or high, each with a likelihood

The decision-maker aims to optimize performance across these scenarios.

### Cost Functions
The objective function in stochastic programming often involves minimizing expected costs or maximizing expected returns. It may include:

- **Expected value calculations:** Averaging outcomes weighted by scenario probabilities
- **Risk measures:** Penalizing undesirable outcomes, like high losses
- **Penalty terms:** Adding extra costs for constraint violations

Example operators:

- `cp.pos(x)`: Computes `max(x, 0)` to model non-negative penalties
- `cp.multiply`: Multiplies vectors element-wise, useful for applying probabilities
- `cp.sum`: Computes the total across scenarios or decision variables

### Constraints
Constraints define the feasible region for decision variables. They can be:

- **First-stage constraints:** Must hold before uncertainty is revealed (e.g., budget limits)
- **Second-stage constraints:** Must hold after uncertainty is realized (e.g., demand fulfillment)
- **Non-negativity constraints:** Ensure variables represent realistic values (e.g., no negative inventory)

## Example Applications

### 1. Newsvendor Problem
A vendor must decide how many items to stock without knowing the exact demand. The goal is to minimize expected costs, balancing:

- **Overstock costs:** Money lost on unsold items
- **Understock costs:** Lost revenue from unmet demand

Optimal stocking levels depend on the probability distribution of demand.

### 2. Portfolio Optimization
In finance, investors allocate funds across assets to maximize expected returns while controlling risk. The problem involves:

- **Decision variables:** Asset allocation weights
- **Objective:** Maximize expected returns minus a risk penalty
- **Constraints:** Budget (weights sum to 1), non-negativity, diversification limits

The solution balances the trade-off between return and risk across various market scenarios.

## Assignment 1: Implementation and Analysis

In Assignment 1, we implemented key stochastic programming concepts using Python. Our work included:

- **Building a modeling framework** with CVXPY and NumPy
- **Solving the Newsvendor Problem** with different demand distributions
- **Optimizing investment portfolios** under uncertain returns
- **Visualizing solutions** with Matplotlib
- **Sensitivity analysis:** Studying how changes in uncertainty affect decisions

### Key Insights
- **Stochastic solutions outperform deterministic ones** when uncertainty is significant
- **Scenario selection impacts solution quality:** More scenarios improve accuracy but increase computation time
- **Risk aversion changes decisions:** Higher risk penalties lead to more conservative strategies

## Mathematical Formulation

A generic stochastic programming problem can be written as:

```math
\min \mathbb{E}[f(x, \xi)] \\
\text{subject to:} \\
    g(x) \leq 0 \\
    h(x, \xi) \leq 0
```

Where:

- \( x \) is the decision variable  
- \( \xi \) represents random parameters (e.g., demand, returns)  
- \( \mathbb{E}[\cdot] \) denotes the expectation over all scenarios  
- \( f(x, \xi) \) is the cost function  
- \( g(x) \) are deterministic constraints  
- \( h(x, \xi) \) are random constraints dependent on uncertainty  


## Solution Approaches

- **Sample Average Approximation (SAA):** Use Monte Carlo sampling to approximate expectations
- **Stochastic Gradient Descent:** Efficient for large-scale problems
- **L-shaped Method (Benders Decomposition):** Splits the problem into easier subproblems
- **Progressive Hedging:** Decomposes multi-stage problems into manageable parts

## Software Tools
We used Python libraries like CVXPY, NumPy, and Matplotlib to model, solve, and visualize stochastic optimization problems.

---

# Week 2: Introduction to Random Walks

## Definition of a Random Walk

A random walk describes a sequence of steps, where each step's direction and magnitude are determined randomly. Random walks model phenomena in various fields, from particle diffusion to financial markets.

## 1D Random Walk

In one dimension, a particle starts at position 0 and moves left or right with equal probability:

```math
X_t = X_{t-1} + S_t
```

Where:

- \( X_t \) is the position at time \( t \)
- \( S_t \) is a random step (+1 or -1)

After many steps, the position distribution becomes approximately normal, centered at the origin, with spread proportional to the square root of time.

## 2D Random Walk

In two dimensions, a particle starts at (0, 0) and moves to a neighboring grid point at each step:

```math
X_t = X_{t-1} + (dx_t, dy_t)
```

Where \( (dx_t, dy_t) \) is a random step vector. Over time, the particle diffuses outward in a circular pattern.

## Applications of Random Walks

- **Physics:** Molecular diffusion, Brownian motion
- **Finance:** Stock price dynamics (e.g., Geometric Brownian Motion)
- **Biology:** Animal foraging behavior, genetic drift
- **Computer Science:** Graph algorithms, Monte Carlo methods

Random walks lay the foundation for advanced stochastic processes like Markov chains, which model systems where the next state depends only on the current state.
