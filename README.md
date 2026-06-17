# Asteroid Mining Optimizer 

An optimization and visualization framework for planning profitable asteroid mining missions. The project models orbital mechanics, resource extraction potential, and route optimization using both exact and heuristic algorithms.

## Project Structure

```text
asteroid-mining-optimizer/
├── README.md
├── requirements.txt
├── .gitignore
├── config.py
├── data/
│   ├── fetch_asteroids.py        # Pull from NASA JPL Small Body DB
│   ├── asteroid_cache.json       # Cached asteroid data (committed to repo)
│   └── preprocess.py             # Clean + enrich with resource estimates
├── physics/
│   ├── orbital_mechanics.py      # Hohmann transfer delta-v calculations
│   ├── dynamic_graph.py          # Time-varying graph of asteroid distances
│   └── resource_model.py         # Estimate water/metal yield per asteroid type
├── solvers/
│   ├── brute_force.py            # Exact solver (tiny N only, shows NP-hardness)
│   ├── genetic_algorithm.py      # GA solver (main workhorse)
│   └── greedy_baseline.py        # Greedy nearest-neighbor baseline
├── visualization/
│   ├── plot_3d_orbits.py         # 3D animated orbital plot (Plotly)
│   ├── plot_route.py             # Highlight the mining route
│   └── plot_comparison.py        # Solver comparison charts
├── outputs/
│   └── .gitkeep
├── main.py                       # CLI entrypoint
└── notebooks/
    └── exploration.ipynb         # EDA + theory writeup
```

---

## Features

* Fetch real asteroid data from NASA databases
* Estimate mining potential (water, metals, rare resources)
* Compute inter-asteroid transfer costs using orbital mechanics
* Build dynamic mission graphs that evolve over time
* Compare optimization approaches:

  * Brute Force (exact)
  * Greedy Baseline
  * Genetic Algorithm
* Interactive 3D orbital visualizations
* Route comparison and performance analysis

---

## Optimization Problem

Given:

* A set of candidate asteroids
* Resource value estimates
* Fuel and transfer costs
* Mission constraints

Find a mining sequence that maximizes:

```math
Profit = Resource\ Value - Travel\ Cost
```

This problem resembles a time-dependent Traveling Salesman Problem (TSP) and is computationally NP-hard.

---

## Installation

```bash
git clone https://github.com/yourusername/asteroid-mining-optimizer.git
cd asteroid-mining-optimizer

pip install -r requirements.txt
```

---

## Usage

### Fetch Asteroid Data

```bash
python data/fetch_asteroids.py
```

### Preprocess Data

```bash
python data/preprocess.py
```

### Run Optimization

```bash
python main.py
```

### Generate Visualizations

```bash
python visualization/plot_3d_orbits.py
```

---

## Algorithms

### Brute Force

* Evaluates every possible route
* Produces optimal solutions
* Feasible only for very small datasets

### Greedy Baseline

* Selects the locally best next asteroid
* Fast but often suboptimal

### Genetic Algorithm

* Evolves candidate routes
* Scales to larger asteroid sets
* Balances solution quality and runtime

---

## Future Improvements

* Multi-spacecraft mission planning
* Reinforcement learning route optimization
* More realistic orbital propagation
* Economic market simulations
* In-situ resource utilization (ISRU) modeling
* Parallelized optimization

---

## Technologies

* Python
* NumPy
* Pandas
* NetworkX
* Plotly
* SciPy
* NASA JPL Small-Body Database

---

## License

MIT License
