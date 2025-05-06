[![Python Version](https://img.shields.io/badge/python-3.8%2B-blue.svg)](https://www.python.org/) [![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

# Complex Network Analysis of Turkish Higher Education Programs

An exploratory network-science project using Python and NetworkX to simulate synthetic graphs (Erdős–Rényi, Cayley tree) and analyze a real weighted co-preference network of Turkish higher-education programs.

---

## Table of Contents

1. [Project Overview](#project-overview)
2. [Data](#data)
3. [Environment & Installation](#environment--installation)
4. [Usage](#usage)
5. [Project Structure](#project-structure)
6. [Analysis & Metrics](#analysis--metrics)
7. [Visualizations](#visualizations)
8. [References](#references)

---

## Project Overview

This project explores both **synthetic** and **real-world** networks:

* **Synthetic networks**

  * **Erdős–Rényi (ER)** model: random graph simulation.
  * **Cayley tree** (Bethe lattice): balanced tree structure.

* **Real co-preference network**

  * Nodes represent Turkish higher-education programs.
  * Edges weighted by co-preference frequency (from `co-preference-edges-weighted.txt`).
  * Computed node-level and graph-level metrics, then exported a GEXF file for interactive visualization in tools like Gephi.

All analyses are contained in `network_analysis.ipynb`.

---

## Data

* `co-preference-edges-weighted.txt` — tab-delimited weighted edge list.
* `Turkish_HigherEd_Programs.gexf` — output GEXF with computed node attributes.

---

## Environment & Installation

Requires Python 3.8+.

```bash
# Clone repository
git clone https://github.com/irmakerkol/Complex-Network-Analysis-of-Turkish-Higher-Education-Programs
cd Complex-Network-Analysis-of-Turkish-Higher-Education-Programs

# Create virtual environment (optional)
python3 -m venv venv
source venv/bin/activate

# Install dependencies
pip install \
  networkx \
  matplotlib \
  seaborn \
  pandas \
  numpy
```

---

## Usage

1. **Open the notebook**

   ```bash
   jupyter notebook network_analysis.ipynb
   ```
2. **Run all cells** to:

   * Simulate ER and Cayley-tree networks.
   * Load and analyze the co-preference network.
   * Compute metrics and generate plots.
   * Export enriched GEXF file:

     ```python
     nx.write_gexf(G, 'Turkish_HigherEd_Programs.gexf')
     ```
3. **Visualize**

   * Use Gephi or any GEXF-compatible tool to explore the exported network.

---

## Project Structure

```
.
├── network_analysis.ipynb         # Main analysis notebook
├── co-preference-edges-weighted.txt  # Raw weighted edge list
├── Turkish_HigherEd_Programs.gexf    # Enriched network export
├── README.md                        # Project overview and instructions
└── requirements.txt                 # (optional) pinned dependencies
```

---

## Analysis & Metrics

### Synthetic Networks

* **Erdős–Rényi**

  * Node degree distribution
  * Clustering coefficient, strength
  * Graph density, largest connected component size, radius, diameter

* **Cayley Tree**

  * Structure generation via NetworkX
  * Basic visual layout (spring layout)

### Real Co-preference Network

* **Node-level properties**

  * `degree`
  * `clustering` (local clustering coefficient)
  * `strength` (weighted degree)
  * `avg_neighbor_degree`
  * `is_eulerian`

* **Graph-level properties**

  * Density
  * Largest connected component size
  * Radius & diameter
  * Bridges detection

* **Assortativity**

  * Degree-degree heatmap
  * Assortativity coefficient

---

## Visualizations

* **Degree distribution** (linear or log scale depending on topology)
* **Degree-degree heatmap** for assortativity analysis
* **Network diagrams** for ER, Cayley tree, and real network
* Exported `.gexf` opened in Gephi for interactive exploration

---

## References

* NetworkX documentation: [https://networkx.org/documentation](https://networkx.org/documentation)
* Cayley tree (Bethe lattice) description: [https://en.wikipedia.org/wiki/Bethe\_lattice](https://en.wikipedia.org/wiki/Bethe_lattice)
* Shields.io for badges: [https://shields.io/](https://shields.io/)
