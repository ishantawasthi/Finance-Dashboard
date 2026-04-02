# Finance Dashboard

A personal finance dashboard I built as part of a frontend internship assignment. The idea was simple — give users a clean way to see where their money is going, track transactions, and get a quick snapshot of their financial health.

---

## What's inside

The app has three main sections:

**Dashboard** — shows your total balance, income, and expenses at a glance, along with a balance trend chart and a spending breakdown by category.

**Transactions** — a full list of all transactions with search, filter by type (income/expense), and sort by date or amount. Admins can also add, edit, or delete transactions from here.

**Insights** — pulls out some useful numbers like your highest spending category, savings rate, average monthly expense, and a month-by-month income vs expense comparison.

---

## Tech used

- React (Vite)
- Tailwind CSS
- Recharts — for the charts
- React Router DOM — for navigation between pages
- Context API — for managing state across the app

No backend, no external APIs. Everything runs on mock data that I wrote by hand.

---

## How to run it locally

```bash
git clone https://github.com/your-username/finance-dashboard.git
cd finance-dashboard
npm install
npm run dev
```

Then open `http://localhost:5173` in your browser.

---

## Role-based UI

There's a role switcher in the top navbar. It's purely frontend — no auth, no tokens.

- **Viewer** — can browse everything but can't make changes
- **Admin** — gets the Add Transaction button, plus Edit and Delete on each row

Switch between them with the dropdown to see how the UI adapts.

---

## A few things worth noting

- Data persists across page refreshes via localStorage, so anything you add or edit won't disappear when you reload
- Dark mode is supported — toggle it with the moon/sun button in the navbar
- There's a CSV export button on the Transactions page if you want to download the data
- The app handles empty states — if you delete everything, you'll see a proper "no transactions found" message instead of a broken layout

---

## Assumptions I made

Since there's no backend, I used hardcoded mock data covering a few months of transactions across different categories (food, rent, salary, transport, etc.). The role switching is simulated on the frontend only — in a real app this would obviously be handled server-side.

The currency is in INR (₹) since that felt most natural for this context.

---

## Live demo

[Deployed on Vercel → your-link-here]

---

## Folder structure (quick reference)

```
src/
├── components/    # reusable UI pieces (cards, charts, table, form)
├── context/       # AppContext — global state
├── data/          # mock transaction data
├── pages/         # Dashboard, Transactions, Insights
└── utils/         # CSV export helper
```