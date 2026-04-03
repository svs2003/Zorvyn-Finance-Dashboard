# FinTrack — Finance Dashboard

A clean, single-file finance dashboard built with vanilla HTML, CSS, and JavaScript.

## Setup

No build step needed. Just open `index.html` in a browser.

```bash
# Option 1 — open directly
open index.html

# Option 2 — serve locally
python3 -m http.server 8080
# then visit http://localhost:8080
```

## Features

### Dashboard Overview
- Summary cards: Total Balance, Income, Expenses, Transaction Count
- Line chart showing 6-month income vs expense trend
- Doughnut chart with spending breakdown by category

### Transactions
- Full transaction list with Date, Description, Category, Type, Amount
- Search by description or category
- Filter by type, category, and month
- Sort by any column (click headers)
- Admin role: Add, Edit, Delete transactions

### Role-Based UI
- Switch between **Admin** and **Viewer** roles via the sidebar dropdown
- Admin: Can add, edit, and delete transactions
- Viewer: Read-only — add/edit/delete controls are hidden

### Insights
- Top spending category
- Savings rate percentage
- Average monthly expense
- Month-over-month expense change
- Bar chart: monthly income vs expense comparison
- Line chart: category expense trend over 6 months

### Additional
- Dark mode toggle (top right)
- Export transactions to CSV
- Data persists via localStorage
- Fully responsive — works on mobile, tablet, desktop
- Handles empty/no-data states gracefully

## Tech Stack

- Vanilla HTML/CSS/JS — no framework, no build tools
- Chart.js (via CDN) for visualizations
- Google Fonts (DM Sans + DM Mono)
- localStorage for data persistence

## State Management

All state is managed in plain JS variables:
- `transactions` — array of transaction objects, synced to localStorage
- `role` — current user role (`admin` | `viewer`)
- `sortField` / `sortDir` — current sort state
- Filter values read directly from DOM inputs on each render

## Design Decisions

- Single file for simplicity and portability
- CSS variables for full dark/light theming with zero JS involvement
- Indian Rupee (₹) formatting with `en-IN` locale
- Sample data covers 6 months to make charts meaningful from first load
- Charts are destroyed and recreated on re-render to avoid Chart.js conflicts
