# GO_SAFE 🚦  
### Safety-Aware Route Recommendation System

> **Safer routes, not just shorter ones.**

GO_SAFE is a safety-first routing system that extends traditional navigation logic by treating **user safety as a first-class routing signal**. Instead of optimizing only for distance or time, GO_SAFE computes **safer alternative routes** using risk-aware graph traversal.

This project is designed as a lightweight, extensible layer that can naturally integrate with platforms like Google Maps.

---

## 🔍 Problem Statement

Modern navigation systems primarily answer one question:

> *“How fast can I get there?”*

But in real-world travel, users often care more about:
- Poorly lit or isolated roads  
- Unsafe or crime-prone areas  
- Night-time or solo travel conditions  
- Human comfort and confidence while navigating  

Today, **safety is not treated as a routing decision** — it is either implicit or ignored.

---

## 💡 Core Idea

GO_SAFE reframes navigation as a **risk-aware optimization problem**.

- Locations are modeled as graph nodes (latitude–longitude points)
- Paths are graph edges
- Each node carries a **safety score**
- Routing minimizes **cumulative risk**, not just distance

The result:
- A baseline route (traditional)
- One or more **safer alternative routes**

---

## 🧠 System Architecture

User Input (Start → End)  
→ OSRM Route Generation  
→ Graph Construction (Lat/Long Nodes)  
→ Safety Score Assignment  
→ Risk-Weighted Dijkstra Algorithm  
→ Safest Route Selection  
→ User Output  

---

## ⚙️ Tech Stack

- **Language:** Dart / Flutter  
- **Routing Engine:** OSRM (Open Source Routing Machine)  
- **Algorithm:** Modified Dijkstra’s Algorithm  
- **Safety Data:** Hardcoded safety scores (prototype phase)  
- **APIs:** Public OSRM APIs  

The system is intentionally built **without private servers**.

---

## 🧮 Algorithmic Approach

### 1. Base Route Generation
OSRM generates one or more possible routes between source and destination.

### 2. Graph Modeling
Routes are decomposed into intermediate latitude–longitude points, each treated as a graph node.

### 3. Safety Scoring
Each node is assigned a safety weight.  
Lower score → safer region.

### 4. Risk-Aware Routing

Total Cost = Σ Safety Scores of Route Nodes  

The route with minimum total risk is selected.

---

## 🧪 Example Scenario

**Traditional Navigation**
- Chooses fastest route
- Passes through isolated or unsafe areas

**GO_SAFE Navigation**
- Slightly longer route
- Avoids high-risk segments
- Prioritizes safer paths

Result: safer, more confident travel.

---

## 🔐 Design Decisions & Constraints

### Why Hardcoded Safety Scores?
- Focus on routing logic
- Avoid unreliable datasets
- Enable deterministic testing

### Why No Custom Backend?
- Lightweight client-side experimentation
- Easy integration
- Low operational complexity

---

## 🚀 Scalability & Future Extensions

- Real-time crime statistics  
- Crowd density data  
- Lighting & road condition signals  
- Time-of-day safety weighting  
- ML-based safety prediction  

GO_SAFE can evolve into a **dedicated safety layer** for large-scale navigation platforms.

---

## 🎯 Why This Project Matters

- Human-centric system design  
- Real-world graph algorithms  
- Safety as a core signal, not an afterthought  

---

## 🧑‍💻 Contributor

**Riddhima Urankar**  
Computer Engineering Student

---

## 🟢 Project Status

- Prototype: Complete  
- Extensible: Yes  
- Internship-ready: Yes  

---

## 📣 Pitch Summary

GO_SAFE introduces safety-aware routing.

Instead of only asking *“What is the fastest route?”*, it asks:

**“What is the safest reasonable route?”**

---

## ✉️ Outreach Message

**Subject:** Safer routes shouldn’t be an afterthought — introducing GO_SAFE

Most navigation systems optimize for speed.  
GO_SAFE optimizes for safety.

We’ve built a working prototype that integrates safety directly into routing decisions and aligns naturally with modern navigation platforms.

We’d love to explore this further as interns — building safer navigation, not just faster navigation.

— Riddhima Urankar & Team

---

> **The future of navigation is not just faster. It is safer.**
