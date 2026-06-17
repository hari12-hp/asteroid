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
│   ├── plot_3d_orbits.py         # 3D animated orbital plot (plotly)
│   ├── plot_route.py             # Highlight the mining route
│   └── plot_comparison.py        # Solver comparison charts
├── outputs/
│   └── .gitkeep
├── main.py                       # CLI entrypoint
└── notebooks/
    └── exploration.ipynb         # EDA + theory writeup
