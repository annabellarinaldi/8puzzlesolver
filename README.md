# 8-Puzzle Solver

This project implements multiple search algorithms to solve the classic 8-puzzle game. It was completed as part of COMP 560: Artificial Intelligence at UNC Chapel Hill.

---

## 🎯 Project Overview

The 8-puzzle consists of a 3x3 grid with 8 numbered tiles and one empty space (represented as `0`). The objective is to reach a goal configuration by sliding tiles into the empty space.

**Goal State:**
```
[[1, 2, 3],
 [4, 5, 6],
 [7, 8, 0]]
```

On each move, a tile adjacent to the empty space is shifted into it. The challenge is to reach the goal state from a given starting configuration using various search strategies.

---

## 🧠 Algorithms Implemented

### 🔹 1. Breadth-First Search (BFS)
- Explores the shallowest nodes first using a queue.
- Graph search approach with a closed set to avoid redundant expansions.
- State tie-breaking follows a fixed priority: down → right → up → left.
- Metrics recorded: solution path, number of nodes expanded, execution time.

### 🔹 2. Iterative Deepening Search (IDS)
- Combines the space-efficiency of DFS with the completeness of BFS.
- Tracks visited states with associated depths to allow valid re-expansions.
- Supports re-expansion if a state is found at a shallower depth.
- Metrics recorded for both easy and hard test cases.

### 🔹 3. A* Search with Heuristics
- Uses a priority queue and evaluates nodes with:
  \[
  f(n) = g(n) + h(n)
  \]
  where \( g(n) \) is the path cost and \( h(n) \) is a heuristic estimate.

#### Heuristics:
- **Misplaced Tiles**: Counts how many tiles are in the wrong position.
- **Manhattan Distance**: Sum of the distances of each tile from its goal position.

### 🔹 4. Performance Analysis
- Compares BFS, IDS, and A* (with both heuristics) across:
  - Execution time
  - Number of nodes expanded
  - Solution quality (path length)

---

## 📁 File Structure

- `Node` class: Represents each search node with parent, state, and depth
- `PriorityQueue` class: For managing A* frontier
- `BfsSearcher`, `IdsSearcher`, `AStarSearcher`: Implement search logic
- `main.ipynb`: Execution environment (Google Colab)
- `README.md`: You’re here!

---

## 🚀 How to Run

1. Open the [Colab notebook](https://colab.research.google.com/drive/1p7PKknH2OAwqlB1nGDEe8hTut8YkzW_Z?usp=drive_link)
2. Define an initial board state, e.g.:
   ```python
   start = [[1, 2, 3], [4, 0, 6], [7, 5, 8]]
   ```
3. Choose and run any of the search strategies
4. The code will print:
   - Solution path
   - Execution time
   - Number of nodes expanded

---

## 🛠️ Tools and Technologies

- **Language:** Python  
- **Platform:** Google Colab  
- **Libraries:** time, copy, queue

---

## 📚 Course Info

- **Course:** COMP 560 – Artificial Intelligence  
- **Institution:** UNC Chapel Hill  
- **Semester:** Spring 2025  

---

## 📌 Notes

- All search methods implement a graph search version with appropriate closed set tracking.
- Tie-breaking for successor order strictly follows the down → right → up → left rule.
- IDS handles depth-specific revisits to ensure completeness.

---
