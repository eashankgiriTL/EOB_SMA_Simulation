# 🧭 Path Studio — A* Shortest Path + SMA Demo

An interactive, browser-based pathfinding visualizer built with vanilla HTML5 Canvas and JavaScript. Click to place points, draw walls, and watch either an exact **A\* shortest-path network** or a biologically-inspired **Slime Mould Algorithm (SMA)** route agents in real time.

> **Educational tool** — demonstrates classical graph search (A\*) alongside emergent, nature-inspired optimization (SMA) side by side.

---

## ✨ Features

- **A\* mode** — computes exact shortest paths between all placed points via a Minimum Spanning Tree (MST) backbone; each MST edge is routed individually with A\*
- **SMA demo mode** — 900 agents simulate slime mould foraging behaviour, sensing nearby points and leaving trails that converge toward efficient routes
- **Wall painting** — hold `W` to paint obstacle walls with configurable cost; hold `E` to erase them
- **Diagonal movement toggle** — switch between 4-directional and 8-directional grid movement
- **Adjustable wall penalty** — tune how strongly walls are avoided vs. passed through
- **Animated click ripples** — soft radial glow on every click for visual feedback
- **Undo / Clear** — step back one point or wipe the canvas entirely
- **Responsive layout** — three-column panel layout with a built-in SMA reference sidebar; collapses gracefully on narrower screens
- **Zero dependencies** — single self-contained HTML file, no build step

---

## 🖥️ Demo

Open `index.html` directly in any modern browser — no server required.

```bash
git clone https://github.com/eashankgiriTL/PhysProject_WindTunnelSim.git
cd PhysProject_WindTunnelSim
open index.html      # macOS
# or double-click index.html on Windows / Linux
```

---

## 🖱️ How to Use

| Action | How |
|---|---|
| **Add a point** | Left-click anywhere on the canvas |
| **Draw walls** | Hold `W` + click/drag |
| **Erase walls** | Hold `E` + click/drag |
| **Remove last point** | Click **↶ Undo** |
| **Clear everything** | Click **🧽 Clear** or double-click the canvas |
| **Switch algorithm** | **🧭 A\* shortest** / **🧬 SMA demo** buttons in the header |

Once two or more points are placed in A\* mode, the simulator instantly computes a Minimum Spanning Tree over the points and routes each link with A\*, drawing the optimal path network in amber.

In SMA mode, agents are seeded randomly across the field and steer toward placed points; trails accumulate in blue, forming organic-looking path networks over time.

---

## 🔧 Controls

| Control | Range | Description |
|---|---|---|
| **Diagonal movement** | On / Off | Allows 8-directional grid steps (Chebyshev distance heuristic) |
| **Wall penalty** | 1 – 200 | Extra cost added to any cell containing a wall |
| **Path thickness** | 1 – 10 px | Visual stroke width of the rendered path |

---

## 📐 Algorithms

### A\* + MST Network

Points are connected using **Prim's algorithm** to build a Minimum Spanning Tree (edge weight = grid distance between point pairs). Each MST edge is then individually routed using **A\* search**:

- **Heuristic** — Chebyshev distance (diagonal on) or Manhattan distance (diagonal off)
- **Wall cost** — soft penalty added per wall cell (not a hard block; tunable via slider)
- **Complexity** — O(E · (V + E log V)) where V, E are the grid cells and edges explored per A\* call

### Slime Mould Algorithm (SMA)

A lightweight agent-based simulation inspired by *Physarum polycephalum* foraging behaviour:

| Phase | Behaviour |
|---|---|
| **Approach food** | Each agent senses three directions (forward-left, forward, forward-right) and steers toward the highest concentration of nearby points |
| **Wrap food** | Agents deposit trail markers into the shared path set, thickening routes used by many agents |

**Update loop per agent (per step):**
```
sample fitness at centre, left-sensor, right-sensor
if left > right  →  turn left
if right > left  →  turn right
else             →  small random jitter
move forward by step, clamp to field bounds
mark current cell in pathSet
```

**Complexity:** ≈ O(T · N · (1 + log N + D)) where T = timesteps, N = agents, D = points.

**Key difference from A\*:**

| | A\* | SMA |
|---|---|---|
| Optimality | Exact shortest path | Near-optimal; not guaranteed |
| Nature | Deterministic graph search | Emergent, stochastic |
| Output | Minimal path network | Organic, evolving trail network |

---

## 🗂️ Project Structure

```
index.html       # Entire simulation — self-contained single file
README.md
```

---

## 🚀 Possible Extensions

- Export the computed path as a JSON coordinate list or SVG
- Add Dijkstra and Breadth-First Search modes for algorithm comparison
- Implement proper SMA weight oscillation and contraction operators (full Slime Mould Algorithm paper)
- Add a heatmap showing per-cell visit frequency for SMA trails
- Touch/stylus support for wall drawing on tablets

---

## 📄 License

MIT — free to use, modify, and distribute for educational or personal projects.

---

*Built as a CS/algorithms project by [Eashan K Giri](https://github.com/eashankgiriTL).*
