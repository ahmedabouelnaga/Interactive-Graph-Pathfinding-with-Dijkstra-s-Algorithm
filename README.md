# Interactive Graph Pathfinding with Dijkstra's Algorithm

This repository features a comprehensive implementation of Dijkstra's algorithm for interactive graph pathfinding. Designed with a graphical user interface (GUI), this project demonstrates the application of advanced graph traversal techniques to compute shortest paths and visualize results dynamically.

## Table of Contents
- [Overview](#overview)
- [Project Features](#project-features)
- [Implementation Details](#implementation-details)
- [Graph Representation](#graph-representation)
- [How to Run](#how-to-run)
- [Files in the Repository](#files-in-the-repository)
- [License](#license)
- [Contribution](#contribution)

---

## Overview
This project models a network of cities connected by roads, using Dijkstra's algorithm to find and visualize the shortest paths. Leveraging a dynamic GUI, users can:
- Compute Euclidean distances between directly linked cities.
- Run Dijkstra's algorithm to determine the shortest path between any two cities.
- Visualize the results in an interactive map.

---

## Project Features
1. **Graphical Visualization**:
   - Displays a map of cities and their connections.
   - Highlights the shortest path computed by Dijkstra's algorithm.

2. **Interactive Controls**:
   - Compute and display Euclidean distances between linked cities.
   - Select source and target cities to calculate the shortest path.

3. **Custom Graph Implementation**:
   - Cities are represented as vertices, and roads as edges.
   - All computations are based on real-world Euclidean distances.

---

## Implementation Details
The core functionality is implemented in the following methods within `GraphProcessor.java`:

### 1. `computeAllEuclideanDistances()`
- Computes the Euclidean distance for all directly connected city pairs.
- Sets the weights of corresponding edges in the graph.
- Updates the GUI with computed distances.

### 2. `doDijkstra(String sourceCity)`
- Implements Dijkstra's algorithm to calculate the shortest paths from a source city to all other cities.
- Uses a simplified list-based approach instead of a priority queue for vertex selection.
- Updates the `distance` and `prev` attributes of each vertex for path reconstruction.

### 3. `getDijkstraPath(String sourceCity, String targetCity)`
- Constructs the shortest path from the source to the target city.
- Uses the `prev` attributes from `doDijkstra` to backtrack and build the path.
- Returns the path as a list of `Edge` objects for visualization in the GUI.

---

## Graph Representation
The graph is represented using the following classes:

1. **Vertex.java**:
   - Represents a city, storing attributes like name, coordinates, and bookkeeping fields (`distance`, `prev`, `known`).

2. **Edge.java**:
   - Represents a road between two cities, storing attributes like source, target, and weight (distance).

3. **GraphProcessor.java**:
   - Central class handling graph operations, including reading data files, computing distances, and executing Dijkstra's algorithm.

---

## How to Run

### Prerequisites
Ensure you have Java installed on your system.

### Steps
1. **Compile the Files:**
   ```bash
   javac *.java
