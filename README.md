# ✈️ RED — Trip Splitter

**RED** is a high-precision group expense tracking and settlement application tailored for group travel, combining fintech financial clarity with travel simplicity. Built natively in pure JavaScript (React + Node.js Express).

---

## 🏗️ Architecture: Clean Frontend & Backend Separation

```
Trip_Splitter/
├── backend/                  # Node.js + Express REST API Server (Pure JS)
│   ├── src/
│   │   ├── server.js         # REST endpoints & Express server
│   │   ├── initialData.js    # Default participant profiles (clean zero mock trips)
│   │   ├── routes/           # Express routers (/api/trips, /api/users)
│   │   ├── controllers/      # Business logic & expense handler
│   │   ├── models/           # In-memory clean store
│   │   └── services/         # Greedy Min-Cash-Flow Debt Simplification Algorithm
│   ├── test/
│   │   └── api.test.mjs      # Server & settlement engine automated unit tests
│   └── package.json          # Express, CORS, Dotenv dependencies
│
├── frontend/                 # Vite + React 19 + Tailwind CSS v4 (Pure JS / JSX)
│   ├── src/
│   │   ├── components/       # Reusable fintech components (Linear/Ramp inspired)
│   │   │   ├── dashboard/    # Consolidated travel balances & KPI overview
│   │   │   ├── trips/        # Trip Details workspace, tabs, and creation modals
│   │   │   ├── expenses/     # Add Expense modal (instant split calculator) & ledger
│   │   │   ├── settlements/  # "WHO OWES WHOM" directional transfers & Settle Up
│   │   │   ├── people/       # Group companion list & individual balance allocations
│   │   │   ├── insights/     # Recharts category distribution & spend timelines
│   │   │   └── layout/       # Sidebar with Perspective Switcher & Mobile Nav
│   │   ├── services/         # API integration layer with zero-latency store sync
│   │   └── hooks/            # Reactive trip store hooks
│   ├── package.json
│   └── vite.config.js
│
└── package.json              # Monorepo runner scripts
```

---

## 🚀 Quick Start

### 1. Run the Backend API (Port 3001)
In a dedicated terminal:
```bash
cd backend
npm start
# API running on http://localhost:3001
```

### 2. Run the Frontend UI (Port 5173)
In a second terminal:
```bash
cd frontend
npm start
# Web application accessible on http://localhost:5173
```

### 3. Run Automated Tests
```bash
cd backend
npm test
```

---

## 📐 Greedy Min-Cash-Flow Debt Simplification

When $N$ travelers share expenses, traditional expense logging results in complex, circular cross-payments. RED's engine runs an $O(N \log N)$ greedy min-cash-flow algorithm:

1. Computes exact net balance for each traveler:
   $$\text{netBalance}(i) = \text{totalPaidIn}(i) - \text{consumedShare}(i)$$
2. Verifies the Zero-Sum Invariant ($\sum \text{netBalance} = 0$).
3. Separates debtors and creditors, matching maximum debtor to maximum creditor.
4. Generates direct, non-circular transfer instructions guaranteeing at most $N - 1$ transactions to achieve 100% equilibrium.

---

## 🎨 Visual Rules

- **Palette**: `#F8F8F5` background, `#FFFFFF` surfaces, `#176B50` deep forest primary, `#E9EAE5` hairline borders.
- **Typography**: Tabular numerals (`tabular-nums`) for currency alignment.
- **Unslop**: Subtle borders instead of heavy shadows; zero neon, zero glassmorphism, zero AI-slop.
