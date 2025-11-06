README

# 🧬 EOB SMA Simulation  
### A* Shortest Path + Slime Mould Algorithm (SMA) Interactive Demo

This project is a fully interactive simulation that demonstrates **A\*** (deterministic shortest pathfinding) and **Slime Mould Algorithm (SMA)** (bio-inspired emergent optimization).  
It was created as part of the **Engineering of Biology (EOB)** course to visualize biological optimization behaviours.

---

## 🚀 Live Demo  
Click the link below to open the simulation in the browser (GitHub Pages hosted):  
👉 **https://<your-username>.github.io/EOB_SMA_Simulation/**  
*(This link becomes active after Pages deployment.)*

---

## 📌 Features  
### ✅ **1. A\* Shortest Path Mode**  
- Click on the canvas to place points.  
- The simulation instantly computes:  
  - **Minimum Spanning Tree (MST)** between all points  
  - **A\* routed connections** avoiding obstacles  
- Real-time updates as you draw walls or erase sections  
- Useful for exact pathfinding demonstrations

### ✅ **2. SMA (Slime Mould Algorithm) Mode**  
- Enables a lightweight agent-based SMA visualization  
- Agents explore → approach food → converge  
- Shows emergent “vein-like” structures similar to *Physarum polycephalum*  
- Demonstrates biological optimization and adaptive network formation

### ✅ **3. Canvas Interactions**
- **Click** → place points  
- **W (hold)** → draw obstacles  
- **E (hold)** → erase obstacles  
- **Smooth white click ripples** for feedback  
- **Undo**, **Clear**, and mode toggle buttons  
- Adjustable:  
  - Diagonal movement  
  - Wall penalty  
  - Path thickness

### ✅ **4. Responsive, Aesthetic UI**
- Dark gradient background  
- Soft grain texture  
- Smooth animations  
- Clean control panels and legends

---

## 🧪 Slime Mould Algorithm – Quick Explanation

The **Slime Mould Algorithm (SMA)** mimics the optimisation behaviour of slime mould *Physarum polycephalum*.  
It operates in two phases:

### **1. Approach Food (Exploration)**  
Agents spread outward, influenced by:  
- Randomness  
- Fitness-based gradients  
- Influence of best-found positions  

### **2. Wrap Food (Exploitation)**  
Agents contract and thicken around promising regions, refining the path.  
Weights, oscillations, vb/vc vibrations ensure:  
- Avoiding local minima  
- Balancing exploration ↔ exploitation  
- Dynamic adaptation to food distribution

### **Mathematical Model Includes:**  
- Probability `p = tanh|S(i) - DF|`  
- Weight oscillation  
- Best-position attraction  
- Random exploration term  
- Time-dependent parameters

---

## 📂 File Structure  


---

## 💡 Usage  
1. Open the live link.  
2. Choose **A\*** or **SMA mode**.  
3. Interact with the canvas using click/W/E.  
4. Observe shortest-path formation or emergent SMA behaviour.

---

## 👨‍💻 Tech Used  
- **HTML5 Canvas**  
- **Vanilla JavaScript**  
- **A\* Pathfinding**  
- **MST (Minimum Spanning Tree)**  
- **Custom SMA implementation**  
- **CSS gradients + UI styling**

---

## 📜 Credits  
Developed by **Eashan Giri**  
Interactive logic and interface refined with guidance from an AI assistant.

---

## ✅ License  
This project is open-source for academic and demonstration use.