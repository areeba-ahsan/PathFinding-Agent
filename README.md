# Dynamic Pathfinding Agent

A visual pathfinding agent using **A\*** and **Greedy BFS** to navigate a dynamic grid with real-time obstacles — built with Python Tkinter.

---

## Features

- **Two Algorithms:** A* and Greedy Best-First Search
- **Two Heuristics:** Manhattan and Euclidean distance
- **Live Visualization:** Watch the agent explore nodes in real-time
- **Dynamic Obstacles:** Random walls appear during movement, forcing the agent to re-plan
- **Custom Grid Size:** Set any N×M grid dimensions
- **Draw Walls:** Click or drag to manually place obstacles
- **Random Map:** Auto-generate a map with 30% wall density
- **Stats Display:** Tracks Nodes Expanded, Path Cost, and Execution Time

---

## Color Guide

| Color | Meaning |
|-------|---------|
| 🟩 Green | Start / Visited path |
| 🟥 Red | Goal |
| ⬛ Black | Wall / Obstacle |
| 🟡 Yellow | Frontier (being explored) |
| 🔵 Light Blue | Already explored |
| 🟣 Purple | Agent's current position |

---

## How to Run

### Requirements
- Python 3.x
- Tkinter (comes built-in with Python)

### Run
```bash
python pathfinding.py
```

---

## How to Use

1. **Set grid size** using the Rows/Cols fields and click **Update Grid**
2. **Choose algorithm** (A* or Greedy BFS) and **heuristic** (Manhattan or Euclidean)
3. **Draw walls** by clicking/dragging on the grid, or click **Random Map**
4. Click **START** to launch the agent
5. Watch it find and walk the path — dodging new obstacles in real-time
6. Click **Clear** to reset the board

---

## How It Works

### A* Search
Combines actual cost `g(n)` and heuristic `h(n)` → `f(n) = g(n) + h(n)`. Guarantees the shortest path.

### Greedy BFS
Only uses the heuristic `h(n)`. Faster but does not guarantee the shortest path.

### Dynamic Replanning
During movement, a 5% chance exists that a new random wall appears. If it blocks the current path, the agent **immediately recalculates** a new route from its current position.

---

## Project Structure

```
├── pathfinding.py    # Main application
└── README.md         # This file
```

---

## Concepts Used

| Concept | Details |
|---------|---------|
| A* Search | Optimal pathfinding with cost + heuristic |
| Greedy BFS | Heuristic-only fast search |
| Priority Queue | Efficient frontier management via `heapq` |
| Dynamic Replanning | Re-runs search when path is blocked |
| Tkinter Canvas | Real-time grid rendering and interaction |
