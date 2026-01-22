# 🌯 Burrito Game Analysis — Logistics Optimization

**Integer Programming & Sensitivity Analysis project focused on profit-maximizing food truck operations under real-world constraints.**

This project models a multi-day logistics optimization problem where burritos are distributed from mobile trucks to demand locations. Using mathematical optimization, we determine optimal truck deployment, delivery quantities, and pricing strategies to maximize profit while respecting demand and distance-based constraints.

---

## 🚀 Project Overview

**Objective:**  
Maximize total profit from burrito sales by deciding:
- Which trucks to activate
- How many burritos each truck delivers to each demand node
- How pricing, ingredient cost, and fleet size affect profit and coverage

**Key Challenge:**  
More trucks do not always mean higher profit — distance constraints, fixed costs, and demand saturation create non-linear tradeoffs.

---

## 📦 Data Inputs

- **Truck Nodes:** (x, y) coordinates of available food trucks  
- **Demand Nodes:** Locations and burrito demand per node  
- **Distance Matrix:** Distance between each truck and demand node  
- **Scaled Demand:** Distance-based delivery limits  
- **Economic Parameters:**
  - Burrito price
  - Ingredient cost
  - Fixed truck operating cost

---

## 🧠 Optimization Model

### Decision Variables
- `x_j ∈ {0,1}` — whether truck *j* is deployed  
- `y_ij ≥ 0` — burritos delivered from truck *j* to demand node *i*

### Objective Function
Maximize total profit:
Maximize Σ (p − c) * y_ij − Σ t * x_j


Where:
- `p` = burrito price  
- `c` = ingredient cost  
- `t` = truck operating cost  

### Constraints
- Demand limits per node  
- Distance-based (scaled) delivery constraints  
- Binary truck activation  
- Non-negativity of deliveries  

---

## 🔧 Methodology

- Integer Programming (LP/IP)
- Python-based optimization
- Multi-day scenario analysis (5 days)
- Extensive sensitivity analysis on:
  - Price
  - Ingredient cost
  - Fleet size

---

## 📊 Results Summary

### 💰 Total Profit (5 Days): **$19,102**

| Day | Profit |
|----|--------|
| Day 1 | $1,225 |
| Day 2 | $3,880 |
| Day 3 | $2,777 |
| Day 4 | $1,615 |
| Day 5 | $9,605 |

---

## 🗓 Key Insights by Day

### Day 1 — Limited Reach
- Optimal fleet: 4 trucks  
- 93.7% demand served  
- Improving **price and ingredient cost** is more effective than changing fleet size

### Day 2 — Strong Demand
- Optimal fleet: 5 trucks  
- 100% demand served  
- Moderate price increases can nearly **double profit**

### Day 3 — Low Margin
- Ingredient cost is the strongest lever  
- Every $0.10 cost reduction ≈ +$126 profit  
- Cost reduction unlocks fleet expansion and near-full coverage

### Day 4 — Network Constraint
- Maximum achievable coverage: 74%  
- Adding trucks beyond 6 reduces profit  
- Best strategy: 6 trucks + price increase

### Day 5 — High Demand
- Optimal fleet: 7 trucks  
- Profit: $9,605  
- At price ≥ $12, an 8th truck becomes profitable

---

## 🔍 Sensitivity Analysis — Key Takeaways

- **Price optimization** is the strongest and most consistent profit driver  
- **Ingredient cost reduction** enables scale and higher coverage  
- **Fleet expansion alone rarely improves profit** unless margins support it  
- Network geometry can impose hard limits on achievable demand coverage

---

## 💡 Managerial Insights

- Optimize unit economics before expanding operations  
- More trucks ≠ more profit  
- Strategic pricing often outperforms operational complexity  
- Structural network limits matter as much as cost

---

## 🛠 Tech Stack

- Python  
- Integer / Linear Programming  
- Optimization solvers (Gurobi-compatible formulation)  
- pandas, NumPy  
- Jupyter Notebook  

**Course:** BAN 630 — Optimization & Analytics

