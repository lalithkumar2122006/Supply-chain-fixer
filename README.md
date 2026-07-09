# Supply-chain-fixer
An interactive supply chain simulation that detects disruptions and demonstrates automated recovery across Supplier, Manufacturer, Distributor, and Retailer stages.
# 🚚 Supply Chain Fixer

An interactive web-based supply chain simulation that demonstrates how disruptions are detected and automatically resolved using a multi-agent system. The application visualizes the complete supply chain from Supplier to Retailer and showcases how a Fixer Agent restores operations when disruptions occur.

---

## 📖 Project Overview

Supply Chain Fixer is a browser-based simulation designed to model a real-world supply chain. Four autonomous agents manage different stages of the supply chain, while a dedicated Fixer Agent continuously monitors the system, detects disruptions, and performs recovery actions.

The project helps students understand supply chain management, logistics, disruption handling, and multi-agent coordination through an interactive dashboard.

---

## ✨ Features

- 📊 Real-time Supply Chain Dashboard
- 🤖 Multi-Agent Supply Chain Simulation
- ⚠️ Manual Disruption Simulation
- 🛠 Automatic Fixer Agent Recovery
- 📈 Service Level Performance Chart
- 📝 Live Event Log
- 💾 Save Simulation Run History
- 📱 Responsive User Interface
- 🎨 Modern Dark Theme Dashboard

---

## 🏭 Supply Chain Workflow

```text
Supplier
   │
   ▼
Manufacturer
   │
   ▼
Distributor
   │
   ▼
Retailer
   │
   ▼
Customer
```

The simulation runs one day at a time, allowing users to observe inventory movement, disruptions, and automated recovery.

---

## 🤖 Agents

### 🏭 Supplier Agent
- Produces raw materials
- Detects supplier delays
- Supplies manufacturers

### ⚙️ Manufacturer Agent
- Converts raw materials into finished products
- Handles quality defects
- Maintains production inventory

### 🚚 Distributor Agent
- Receives finished goods
- Ships products to retailers
- Detects transportation breakdowns

### 🏪 Retailer Agent
- Manages customer demand
- Tracks inventory
- Detects stock shortages

### 🛠 Fixer Agent
- Monitors all supply chain stages
- Detects operational disruptions
- Switches to backup suppliers
- Expedites emergency shipments
- Reroutes transportation
- Restocks retailer inventory
- Restores service levels

---

## ⚠️ Supported Disruptions

The simulation includes four disruption scenarios:

- Supplier Delay
- Demand Spike
- Distributor Vehicle Breakdown
- Manufacturer Quality Defect

The Fixer Agent automatically responds to each disruption to minimize service loss.

---

## 📊 Dashboard Features

- Current Simulation Day
- Service Level (%)
- Number of Fixes Applied
- Stockout Statistics
- Agent Status Indicators
- Live Supply Chain Metrics
- Event Log
- Service Level Trend Chart
- Saved Run History

---

## 🛠 Technologies Used

- HTML5
- CSS3
- JavaScript (ES6)
- HTML Canvas API
- Local Browser Storage

---

## 📂 Project Structure

```text
Supply-chain-fixer/
│
├── index.html
├── README.md
└── assets/
```

---

## 🚀 How to Run

1. Clone the repository

```bash
git clone https://github.com/your-username/Supply-chain-fixer.git
```

2. Open the project folder.

3. Open **index.html** in your web browser.

No installation or external dependencies are required.

---

## 🎮 How to Use

1. Click **Start** to begin the simulation.
2. Observe product movement across the supply chain.
3. Trigger disruptions using the available buttons.
4. Watch the Fixer Agent automatically recover the system.
5. Monitor service level, inventory, and event logs.
6. Save simulation results for future reference.

---

## 📸 Screenshots

Add screenshots of:

- Dashboard
- Supply Chain Pipeline
- Disruption Simulation
- Fixer Agent Response
- Event Log
- Service Level Chart

---

## 🎯 Learning Outcomes

This project demonstrates:

- Supply Chain Management
- Multi-Agent Systems
- Logistics Simulation
- Inventory Management
- Disruption Recovery
- Real-Time Monitoring
- Dashboard Design
- JavaScript Programming

---

## 🔮 Future Enhancements

- AI-based disruption prediction
- Machine Learning demand forecasting
- Database integration
- User authentication
- Cloud deployment
- Real-time analytics
- REST API integration
- Mobile support

---

## 👨‍💻 Author

**Lalithkumar N**

B.Tech – Artificial Intelligence and Data Science

College Project

---

## 📄 License

This project is developed for educational purposes as part of a college academic project.
