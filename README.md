# NanoCommSim

**NanoCommSim** is a molecular communication simulation project built using AnyLogic. It models a biological nanonetwork consisting of two transmitters and a single receiver, allowing the study of absorption behavior, molecule collisions, message recognition, and the impact of geometry and transmission frequency on communication efficiency.

---

## 📌 Project Overview

This simulation explores how information molecules are transmitted and absorbed in nanoscale biological environments.

### Key Features:
- Two Transmitters emitting molecules (Type 0 and Type 1)
- One Receiver agent absorbing molecules and recording detailed statistics
- Geometric configurations at **90° and 180°**
- Optional **elastic collisions** between molecules
- Circular absorption tracking in **36 angular sectors**
- Dynamic **sending intervals** (from 100s to 30s)
- Message detection via **upper/lower threshold** system

---

## 🧪 Experimental Scenarios

The project compares 4 main configurations:

| Scenario                  | Collisions | Total Absorption | Notes                                      |
|--------------------------|------------|------------------|---------------------------------------------|
| 90° without collisions   | No         | High             | Symmetrical and efficient absorption        |
| 90° with collisions      | Yes        | Reduced          | Significant interference and message loss   |
| 180° without collisions  | No         | High             | Linear coverage with lateral concentration  |
| 180° with collisions     | Yes        | Reduced          | Randomized paths and irregular absorption   |

Message recognition experiments were also conducted by:
- Adjusting **sending frequency** (shorter intervals)
- Using **threshold logic** to detect valid molecular pulses
- Measuring the number of correctly detected messages over time

---

## 📊 Visualization

The simulation includes real-time visual elements:
- Line plots showing total and per-type absorption over time
- Bar charts of absorption per sector (0°–360° split into 36 sectors)
- Time-based plots of in-range molecules for threshold detection
- Collision counter and message detection statistics

---

## ⚙️ Technologies Used

- **AnyLogic** (agent-based simulation environment)
- **Java** (internal code logic for events, movement, and detection)
- **Python + Matplotlib** *(optional)* for data visualization if exporting CSV

---

## 📁 Structure

- `Main` – Simulation environment setup and global parameters
- `Transmitter` – Agent emitting molecules of a given type
- `Information_Molecule` – Mobile agent with optional collision behavior
- `Receiver` – Tracks absorbed molecules and detects messages
- `Charts & Events` – Show real-time simulation metrics

---

## 🚀 How to Run

1. Open the project in **AnyLogic (University or Professional Edition)**
2. Click **Run** from the Main class
3. Adjust parameters in the GUI (e.g. `sendingInterval`, `collisionsEnabled`)
4. View live charts and absorption counters

---

## 🔍 Future Improvements

- Multi-receiver support
- Molecule degradation and timed disappearance
- More advanced message encoding schemes
- Automatic threshold tuning via learning

---

## 📄 License

This project is open for academic and research use.  
You may fork, cite, or modify it with proper attribution.

---

## 👨‍💻 Author

**[Pavlos Daratzis]**  
Department of Informatics, Aristotle University of Thessaloniki  
Field of Interest: Biological Nanonetworks & Molecular Communications
