# Supply-chain-fixer
An interactive supply chain simulation that detects disruptions and demonstrates automated recovery across Supplier, Manufacturer, Distributor, and Retailer stages.
# Supply Chain Fixer — Multi-Agent Simulation (Python + SQLite)

A multi-agent supply chain simulation with a real Python backend and a
persistent SQLite database, wrapped in a browser dashboard.

## What it models

Four autonomous agents run a supply chain, one simulated "day" at a time:

```
Supplier -> Manufacturer -> Distributor -> Retailer
```

A fifth agent, the **Fixer**, inspects the chain after every day and steps
in with a specific corrective action whenever it detects a problem:

| Problem detected                              | Fixer's response                                   |
|------------------------------------------------|-----------------------------------------------------|
| Supplier hit by a shipping delay                | Switches to a backup supplier                        |
| Manufacturer's raw-material buffer runs low     | Expedites an emergency raw-material shipment         |
| Distributor suffers a vehicle breakdown         | Reroutes the shipment through an alternate carrier    |
| Retailer faces a demand spike it can't cover    | Emergency-restocks retailer from distributor buffer   |

Each of these is a genuine, isolated fix — the Fixer never touches an agent
unless that agent's own state shows the matching problem.

## Architecture

```
supply_chain_fixer/
├── index.html

### Why a real database matters here

- **`sessions` table** — the full agent state (inventories, disruption
  timers, running totals) is written after every tick. Stop the server,
  start it again, and the simulation picks up exactly where it left off.
- **`events` table** — every disruption and every Fixer action is an
  append-only row, so the event log doubles as a durable audit trail you
  can query directly with SQL for the report/presentation.
- **`runs` table** — explicit "Save Run" snapshots (days run, average
  service level, fixes applied, stockouts) for comparing different
  simulation sessions side by side.

You can open `supply_chain.db` with any SQLite browser (e.g. `sqlite3
supply_chain.db` or "DB Browser for SQLite") to show the raw data during
a viva/demo.

## REST API

| Method | Endpoint            | Purpose                                   |
|--------|----------------------|--------------------------------------------|
| GET    | `/api/state`          | Current state of all agents + KPIs          |
| POST   | `/api/tick`            | Advance the simulation by one day           |
| POST   | `/api/reset`           | Reset the simulation                        |
| POST   | `/api/trigger`         | Body `{"type": "supplier_delay"}` etc.      |
| GET    | `/api/events?limit=N`  | Recent event log entries                    |
| GET    | `/api/runs`            | List saved run summaries                    |
| POST   | `/api/runs`            | Save the current run as a summary           |
| DELETE | `/api/runs/<id>`       | Delete a saved run                          |

Valid `type` values for `/api/trigger`: `supplier_delay`, `demand_spike`,
`distributor_breakdown`, `quality_defect`.

## Running it

```bash
pip install -r requirements.txt
python app.py
```



## Extending it (ideas for going further)

- Swap the fixed capacities/rates in `agents.py` for real historical data.
- Add safety-stock / reorder-point formulas to the Fixer's decision logic.
- Add more nodes (multiple suppliers, regional distributors) for a
  network topology instead of a single chain.
- Replace SQLite with Postgres by only touching `database.py` — the rest
  of the app doesn't know or care which database engine is behind it.
