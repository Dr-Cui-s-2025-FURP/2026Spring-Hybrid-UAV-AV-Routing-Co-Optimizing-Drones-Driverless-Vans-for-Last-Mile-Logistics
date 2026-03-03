# Hybrid-UAV-AV-Routing-Co-Optimizing-Drones-Driverless-Vans-for-Last-Mile-Logistics


---

## 📖 1. Project Background & Overview (Start Here)

### 1.1 The "Last-Mile" Problem

Imagine you order a cup of coffee and a new laptop online. The journey of these packages from the factory to your local city is very fast (the "first" and "middle" miles). However, delivering that package from the local city depot directly to your front door is notoriously slow, chaotic, and expensive. This final step is called **Last-Mile Delivery**, and it accounts for over 50% of total shipping costs globally due to urban traffic, narrow streets, and the fact that a massive delivery truck often has to stop just to drop off one tiny envelope.

### 1.2 The Hybrid Solution: Trucks meet Drones

To solve this, researchers introduced the **Hybrid Vehicle Routing Problem (HVRP)**. Instead of just using a delivery truck, what if the truck acted as a "mobile aircraft carrier"?

- The **Autonomous Vehicle (Truck)** drives along main roads carrying heavy packages and acts as a charging station.
- The **Unmanned Aerial Vehicles (UAVs / Drones)** launch from the driving truck, fly straight over the traffic gridlock to deliver small packages to hard-to-reach places, and then fly back to land on the moving truck to recharge.
  This "Tandem Operation" is incredibly efficient, aiming to reduce costs by 30-40% and drastically improve delivery speeds in dense urban areas.

### 1.3 The Mathematics of the Chaos

While this sounds amazing, computing *how* they should cooperate is mathematically terrifying. The computer must simultaneously calculate: Which package goes to the drone? Where does the truck park to wait for the drone? What if the drone runs out of battery? What if the wind is too strong today? In this project, you will combine **Operations Research (Optimization Algorithms)** with **Digital Twin Simulations** and **Robotics (ROS 2)** to solve this exact problem.

### 1.4 Your Mission

You will start by creating the mathematical equations to model this energy-aware routing problem. Then, you will develop an advanced AI/Optimization algorithm (like a Genetic Algorithm) to "solve" it. Following that, you will simulate the downtown traffic and drone flights in a "Digital Twin". Finally, for the ultimate challenge, you will implement this code on physical hardware: coordinating real DJI drones and navigating robotic ground vehicles!

---

## 🎯 2. Research Objectives & Goals

| Priority           | Objective                                                                                                                     |
| ------------------ | ----------------------------------------------------------------------------------------------------------------------------- |
| **Primary**  | Develop an energy-aware Mixed Integer Linear Programming (MILP) model for truck-drone tandem routing.                         |
| **Primary**  | Design and implement a hybrid optimization solver (e.g., ALNS-GA) to generate routes computing joint energy-time costs.       |
| **Primary**  | Build an urban Digital Twin using SUMO (traffic) and AirSim (drones) for dynamic re-planning and simulation.                  |
| **Extended** | Implement ROS-based fleet coordination for physical physical demonstration with 3 laboratory drones and 1 Autonomous Vehicle. |

---

## 🗺️ 3. Project Milestones (9 Nodes)

This project condenses an intense 14-week industrial-grade R&D lifecycle into 9 trackable FURP Nodes.

### Phase 1: Mathematical Modeling & Solver Design (The Fundamentals)

*Objective: Formulate the rules of physics and logistics into code.*

- [ ] **Node 1: VRP Literature & Power Modeling**
  - Read required papers on HVRP and UAV energy consumption.
  - Formulate the time-energy joint cost mathematical function, factoring in UAV range and payload weight.
- [ ] **Node 2: Baseline Mathematical Formulation (MILP)**
  - Use Python (OR-Tools or PuLP) to create a pure MILP formulation for a mini-dataset (e.g., 5 drop-offs).
  - *Deliverable:* Submit the math formulation document and a working brute-force/exact Python script.
- [ ] **Node 3: Metaheuristic Algorithm Development**
  - Because MILP is too slow for real cities, develop a faster, smarter solver using Adaptive Large Neighborhood Search (ALNS) or a Genetic Algorithm (GA).
  - *Deliverable:* The `HVRP-Connect` Python Algorithm core, validated against standard VRP datasets.

### Phase 2: Simulation & Digital Twin (The Core Work)

*Objective: Put the mathematical solver into a simulated, chaotic urban environment.*

- [ ] **Node 4: Urban Network Mapping**
  - Use `OSMnx` to import real city street maps (e.g., downtown area) to analyze nodes, edges, and distances.
  - *Deliverable:* An interactive map visualization showing optimal truck corridors and calculated drone flight paths.
- [ ] **Node 5: Digital Twin Construction (SUMO + AirSim)**
  - Integrate SUMO (for ground traffic simulation) with AirSim (for 3D drone simulation) to create a mock urban testbed.
- [ ] **Node 6: Dynamic Handover & Obstacle Rules**
  - Write code enabling the drone and the truck to electronically "handshake" and meet at optimal rendezvous points dynamically despite traffic delays.
  - *Deliverable:* A simulation video showing a drone taking off from the truck, performing a delivery, and landing on the truck at a *different* location.

### Phase 3: Hardware Integration & Performance Analysis (The Research Frontier)

*Objective: Translate the simulation to hardware and finalize scientific analysis.*

- [ ] **Node 7: Multi-Agent ROS 2 Communication**
  - Develop a ROS 2 package to allow communication between DJI Enterprise framework and the Jetson-based ground AV platform (e.g., TurtleBot3).
  - *Deliverable:* ROS 2 node architecture graph and tested topic publishing setup.
- [ ] **Node 8: Physical Package Handoff Demo**
  - Implement visual servoing (using cameras) so the real drone can precisely locate the AV's landing pad and execute a safe return protocol.
  - *Deliverable:* A video of physical laboratory hardware demonstrating the aerial/ground synchronization loop.
- [ ] **Node 9: KPIs Evaluation & Poster Preparation**
  - Calculate key metrics: Energy-per-parcel, Delivery time reliability, and Fleet size scale effects.
  - *Deliverable:* Final Industry White Paper / Poster submission for the FURP Showcase.

---

## 🎓 4. Evaluation & Certificate Requirements

To successfully complete this FURP project and receive the official participation certificate, students **must** meet the following criteria:

1. **Milestone Completion**: Successfully complete and push code for at least **50% of the project milestones (5 out of 9 Nodes)**.
2. **Poster Submission**: Submit the final academic poster and industry white paper for the annual **FURP Showcase event**.
3. **Repository Standard**: All evaluations are strictly based on the code, MILP math formulations, and simulations pushed to this GitHub repository.

---

## 🛠️ 5. Skill Requirements & Time Commitment

**Time Commitment:** ~14-16 hours/week. Includes lab equipment access and a mid-term simulation hackathon.

**Recommended Prerequisites:**

- **Optimization:** MILP formulation, Metaheuristics (ALNS/GA knowledge is a plus).
- **Programming:** Python (OR-Tools, PuLP), basic ROS 2 navigation stack.
- **GIS / Mapping:** Familiarity with OSMnx or NetworkX for urban network analysis.

---

## 🗂️ 6. Repository Structure Requirements

Create a repository named `FirstnameLastname-HVRP` within the designated GitHub Organization:

```text
FirstnameLastname-HVRP/
├── README.md                    # Project introduction 
├── docs/                        # Mathematical models, algorithm design, reports
├── logs/                        # Weekly work logs (e.g., logs/2026-03-10.md)
├── src/                         # Core Python solvers (ALNS/GA), ROS 2 packages
├── sim/                         # SUMO & AirSim Digital Twin configuration files
├── data/                        # City GIS networks, experiment datasets
├── assets/                      # Maps, algorithm convergence graphs, videos
└── poster/                      # Final FURP Showcase poster (PDF + Source)
```
