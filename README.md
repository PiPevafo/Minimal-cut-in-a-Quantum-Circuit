# Minimal Cut in Quantum Circuits

## Background: Minimum Cut and Entanglement

In quantum information theory, the **minimum cut** in a quantum circuit serves as an upper bound for the entanglement between two subsystems A and B. The concept of a minimal cut refers to partitioning the circuit into two disjoint subsets such that each one contains a subsystem A and B, and the total weight of the edges (circuits lines) crossing the partition is minimized. When applied to quantum circuits, finding this minimal cut can give insights into the degree of entanglement present, which is crucial for understanding the circuit's information flow.

Entanglement is a key resource in quantum computing, enabling tasks like superdense coding, quantum teleportation, and speeding up certain computations. By calculating a minimal cut, one can estimate the maximum amount of information that can be shared between two parts of a quantum system. This is particularly useful for analyzing the structure and efficiency of quantum circuits.

## Overview of the Algorithms

Firstly, the minimum cut of the circuit only depends on its geoemetric characteristics (architecture), this motivates mapping the circuit to a graph that preserves the same geometry.

### 1. Modified Karger’s Algorithm

The first approach presented here is a modification of **Karger’s algorithm**, which is a randomized algorithm for finding the minimum cut in a graph. The modification ensures that the cut occurs specifically between the designated subsystems of the quantum circuit that need to be divided. However, this algorithm is **non-deterministic** and randomized, meaning that it needs to be run multiple times to increase the probability of finding the true minimal cut. Additionally, its complexity increases with the number of qubits and gates in the circuit, making it less efficient for larger circuits.

### 2. Flow Graph Mapping and Dijkstra’s Algorithm

To address the limitations of Karger’s algorithm, we developed a more efficient solution by mapping the **minimum cut problem with constraints** to a flow graph. In this flow graph, the geometric characteristics of the quantum circuit are translated into a graph where each node represents a cycle, and edges represent possible transitions between these cycles.

The **Dijkstra’s algorithm** is then used to find the shortest path in this flow graph. This approach is equivalent to finding the minimum cut with the specified constraints in the original quantum circuit. The flow graph method is both deterministic and scalable, providing a more efficient solution for circuits with a large number of qubits and gates.

## Conclusion

This repository contains implementations of both algorithms, providing tools for researchers and practitioners interested in analyzing the entanglement properties of quantum circuits. The flow graph approach is particularly effective for complex circuits where the Karger-based method may struggle due to its randomness and scaling limitations.

![image](https://github.com/user-attachments/assets/33980421-7d25-4424-8fe1-640d87f540bc)
