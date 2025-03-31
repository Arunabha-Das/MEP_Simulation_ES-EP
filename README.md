# MEP_Simulation_ES-EP
Multipath Entanglement Purification Simulation
This repository contains Python code to simulate and compare multipath entanglement purification (MEP) strategies in quantum networks, as described in the paper "Multipath entanglement purification strategies for quantum networks". The code evaluates two strategies—Shortest-Path First (SPF) and Shortest-Path Last (SPL)—across various network topologies and analyzes their effectiveness in enhancing entanglement concurrence.

Key Features
Network Topologies: Simulates five network models:

RN: Erdős-Rényi Random Network

BAN: Barabási-Albert Scale-Free Network

TLN: Triangular Lattice Network

SLN: Square Lattice Network

HLN: Hexagonal Lattice Network

Entanglement Purification: Implements Deutsch's protocol for entanglement pumping to calculate concurrence for SPF and SPL strategies.

Path Analysis: Determines path lengths between nodes using geometric properties (for lattices) or shortest-path algorithms (for random/scale-free networks).

Visualization: Generates plots comparing average concurrence vs. shortest-path length for different topologies and strategies.

Dependencies
Python 3.x

networkx (graph generation and analysis)

numpy (numerical computations)

matplotlib (plotting)

Install dependencies via:

bash
Copy
pip install networkx numpy matplotlib
Usage
Clone the repository:

bash
Copy
git clone https://github.com/yourusername/quantum-mep-simulation.git
cd quantum-mep-simulation
Run the simulation:

bash
Copy
python simulation.py
Results are displayed in a Matplotlib window showing the average concurrence for SPF and SPL strategies across topologies (example below).

Example Output

Parameters
Network Size:

num_nodes = 10000 (nodes)

num_edges = 50000 (edges)

Edge Concurrence:

delta = 0.02 (1 - mean edge concurrence)

Edge concurrence values are sampled uniformly from [0.97, 0.99].

Simulation Settings:

l0_values = range(1, 7) (shortest-path lengths evaluated)

num_samples = 10000 (S-D pairs sampled per topology and l0).

Key Results
SPL-MEP Outperforms SPF-MEP: The "Shortest-Path Last" strategy consistently achieves higher concurrence across all topologies, especially for larger l0.

Topology Independence: SPL-MEP reduces dependence on network structure, enabling robust entanglement distribution.

Crossover Distance: MEP becomes advantageous over single-path strategies for l0 ≥ 3 in regular lattices and at shorter distances in random/scale-free networks.

Code Structure
generate_network(): Constructs networks using NetworkX with node positions for lattices.

find_paths(): Computes path lengths based on topology-specific geometric rules or shortest paths.

calculate_C(): Computes concurrence using the analytical formula from the paper.

Simulation Loop: Aggregates results for SPF/SPL strategies by sampling S-D pairs.

Plotting: Visualizes results with labeled markers and line styles for clarity.

Reference
This code accompanies the paper:
Md Sohel Mondal and Siddhartha Santra, "Multipath entanglement purification strategies for quantum networks" (2024).
