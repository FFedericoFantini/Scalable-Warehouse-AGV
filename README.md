# 🏭 Warehouse AGV Simulation

A complete **warehouse automation simulation** developed in **Python**, featuring:
- Multiple **AGVs (Automated Guided Vehicles)**
- Dynamic **path planning** on a graph
- **Collision avoidance**
- **Pallet storage and retrieval**
- Real-time **Tkinter GUI**
- Integration with **CoppeliaSim**

---

## 🚀 Features

- 📦 Automatic pallet spawning and storage
- 🤖 Multi-AGV coordination
- 🧭 Graph-based navigation with shortest path computation
- 🔄 Dynamic edge reservation to avoid collisions and deadlocks
- 📊 Real-time warehouse statistics
- 🖥️ Interactive GUI for simulation control
- 🗂️ Configurable warehouse layout (aisles, shelves, levels)

---

## 🧱 Warehouse Model

The warehouse is structured as:

- **Aisles** (`n_aisles`)
- **Two shelf sides per aisle** (`S1` and `S2`)
- **Columns per shelf**
- **Levels per shelf**

📐 **Total storage capacity formula:**

```text
capacity = n_aisles × columns_per_shelf × levels_per_shelf
```
---

## 🧠 System Architecture

### Main Components

#### `generate_waypoints.py`
Generates all warehouse nodes, including:
- Aisles
- Shelves
- Corridors
- Meeting areas

#### `path_generator.py`
Converts discrete waypoints into continuous paths using **linear interpolation**.

#### `move_agv_along_path.py`
Handles AGV motion with:
- Time-based interpolation  
- Collision checking  
- Minimum distance enforcement  

#### `order_simulator.py`
Generates warehouse orders following a **Gaussian distribution**.

#### `PalletScheduler`
Core scheduling logic responsible for:
- Pallet storage
- Order-based retrieval
- AGV task assignment
- Edge reservation and deadlock prevention

#### `MenuGUI`
Tkinter-based GUI used to:
- Start / stop the simulation
- Visualize the warehouse graph
- Display real-time statistics

---

## 🖥️ Graphical User Interface

The GUI allows you to:

- 📊 Visualize the navigation graph  
- ▶ Start / ⏹ Stop the simulation  
- 📈 Monitor warehouse statistics in real time  
- 🚪 Exit safely while stopping all AGVs  

---

## 📁 Project Structure

```
Project_simulation/
Project_simulation/
├── Agvs_Model/
│ └── Omnidirectional Platform.ttm

├── File_CSV/
│ └── warehouse_config.json
│ └── waypoints.csv
│ └── graph.json
│ └── graph.csv

├── images/
│ └── advanced_config.png
│ └── basic_config.png

├── Path_Generation/
│ └── move_along_path.py
│ └── path_generator.py

├── Presentation/
│ └── Config_GUI.py
│ └── Menu_GUI.py

├── Task_Management/
│ └── order_simulator.py
│ └── pallet_scheduler.py

├── Warehouse_Creation/
│ └── clean_scene.py
│ └── create_area.py
│ └── create_floor.py
│ └── create_graph.py
│ └── create_shelves.py
│ └── export_nodes.py
│ └── generate_waypoints.py
│ └── import_agvs.py
│ └── save_scene.py
│ └── visualize_graph.py

├── init.py
├── main.py
└── Warehouse.ttt
```


---


## ⚙️ Requirements

### Software
- Python **3.9+**
- **CoppeliaSim**

### Python Dependencies
Install required packages with:

```bash
pip install numpy networkx pandas matplotlib plotly pillow
```

## ▶️ How to Run

1. Open **CoppeliaSim**
2. Open the file main.py
3. Run main.py
4. Configure the warehouse using the GUI
5. Attent the creation of the scene
6. Click **Visualize Graph** to visualize the graph of the warehouse
7. Click **Start Simulation** on GUI to start simulation
8. Click **Show Statistic** to show statistic regarding the running simulation

---

## 📊 Statistics Example
Displayed via the **Show Statistics** button:

- Pallets in storage  
- Available shelf slots  
- Total stored pallets  
- Busy / free AGVs  
- Completed orders  

---

## 🛠️ Customization

You can configure the following parameters:

- Number of AGVs  
- Number of aisles  
- Shelf dimensions  
- Columns and levels per shelf  
- AGV speed  
- Pallet spawn interval  

All parameters are adjustable via:
- GUI  


---

## 🧪 Collision Avoidance Strategy

The simulation implements a robust collision avoidance system based on:

- Minimum AGV distance enforcement  
- Time-based motion interpolation  
- Edge reservation with bidirectional blocking  
- Automatic wait-and-retry mechanism  

---

## 📄 License

This project is released under a **custom license**.  
See the `LICENSE` file for details.

---

## 👨‍💻 Author

Developed by **Fantini Federico & Alessio Romagnoli**  
🎓 Automation & Robotics Engineering  

---

## ⭐ Acknowledgements

- CoppeliaSim  
- NetworkX  
- Python Open Source Community  


