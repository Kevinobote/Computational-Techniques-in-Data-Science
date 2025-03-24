# Computational Techniques in Data Science

## Week 1: Stochastic Programming
Stochastic programming is an optimization approach for decision-making under uncertainty. It models randomness using probability distributions and optimizes decisions across multiple future scenarios. Key concepts include:

- **Decision Variables:** Represent quantities to optimize (e.g., asset allocation in portfolio optimization, inventory levels in supply chains).
- **Scenarios & Probabilities:** Capture uncertainties like stock price fluctuations or varying demand levels.
- **Cost Functions:** Often involve minimizing expected costs or maximizing expected returns while considering risk.
- **Constraints:** Ensure feasibility, such as budget limitations or demand fulfillment.

### Applications:
1. **Newsvendor Problem:** Determines optimal stocking levels under uncertain demand.
2. **Portfolio Optimization:** Allocates assets to maximize returns while controlling risk.

### Solution Approaches:
- **Sample Average Approximation (SAA)**: Uses Monte Carlo sampling.
- **Stochastic Gradient Descent**: Suitable for large problems.
- **L-shaped Method (Benders Decomposition)**: Solves two-stage problems efficiently.
- **Progressive Hedging**: Handles multi-stage problems.

Python tools like CVXPY, NumPy, and Matplotlib facilitate modeling and solving stochastic programming problems.

---

## Week 2: Introduction to Random Walks
A random walk is a sequence of steps where each step is determined randomly, used to model various phenomena.

### Types of Random Walks:
- **1D Random Walk:** Moves left or right with equal probability.
- **2D Random Walk:** Moves in random directions on a grid, spreading in a circular pattern over time.

### Applications:
- **Physics:** Molecular diffusion, Brownian motion.
- **Finance:** Stock price modeling (Geometric Brownian Motion).
- **Biology:** Animal movement, genetic drift.
- **Computer Science:** Graph algorithms, Monte Carlo simulations.

Random walks serve as a foundation for Markov chains and other stochastic processes.

---

## Week 3: Linear Programming
Linear programming (LP) optimizes a linear objective function subject to linear constraints. Key components include:

- **Objective Function:** A linear function to be maximized or minimized.
- **Constraints:** Linear restrictions on decision variables.
- **Decision Variables:** Quantities that decision-makers optimize.

### Example Applications:
1. **Diet Optimization:** Minimizing food costs while meeting nutritional requirements.
2. **Resource Allocation:** Distributing limited resources efficiently.

LP problems are commonly solved using methods like the Simplex Algorithm and Interior-Point Methods.

---

## Week 4: Introduction to Graph Theoretic Models
Graph theoretic models use graphs to represent relationships between objects. A graph consists of **nodes (vertices)** and **edges (links between nodes)**.

### Key Concepts:
- **Types of Graphs:**
  - **Directed vs. Undirected Graphs:** Edges have direction or not.
  - **Weighted vs. Unweighted Graphs:** Edges have weights (e.g., distances in a road network).
  - **Bipartite Graphs:** Nodes are divided into two sets, with edges only between sets.
  
- **Graph Representations:**
  - **Adjacency Matrix:** A matrix representation of connections.
  - **Adjacency List:** A list of neighboring nodes.

### Applications:
1. **Social Networks:** Representing relationships between users.
2. **Transportation Networks:** Modeling roads, flight routes, and logistics.
3. **Internet & Web Search:** PageRank algorithm for ranking web pages.
4. **Biological Networks:** Protein interactions and gene regulatory networks.

Graph algorithms, such as Dijkstra’s shortest path, PageRank, and minimum spanning trees, are used for optimizing real-world networks.