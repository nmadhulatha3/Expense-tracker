# Expense Tracker

A responsive full-stack expense tracker for recording income and expenses, reviewing totals, and maintaining transaction history in a persistent SQLite database.

## Features
- Add income and expense transactions with title, category, amount, and date.
- Client-side form checks and independent server-side validation.
- Dashboard summary for total income, total expenses, balance, and savings rate.
- Transaction history with category/type information and delete action.
- SQLite persistence: transactions remain available after the server restarts.
- REST API health endpoint and category endpoint.
- Responsive layout for desktop and mobile screens.

## Technology stack
- Frontend: React, Vite, CSS
- Backend: Node.js, Express
- Database: SQLite using `better-sqlite3`
- HTTP: REST API, JSON

## Requirements
- Node.js 20 or newer (Node.js 22 LTS recommended)
- npm

## Run locally (Windows CMD)
1. Extract the ZIP file.
2. Open CMD in the extracted `Expense-Tracker` folder.
3. Install backend dependencies:

   ```cmd
   npm install
   ```
4. Install frontend dependencies:

   ```cmd
   npm --prefix client install
   ```
5. Start both services:

   ```cmd
   npm run dev
   ```
6. Open the frontend at **http://localhost:5173**. The API runs at **http://localhost:5000**.

Keep the CMD window open while using the app. Press `Ctrl+C` to stop the services.

## API endpoints
| Method | Endpoint | Purpose |
|---|---|---|
| GET | `/api/health` | API health check |
| GET | `/api/categories` | Available income and expense categories |
| GET | `/api/transactions` | List transactions |
| GET | `/api/summary` | Income, expenses, balance, and savings rate |
| POST | `/api/transactions` | Create a transaction |
| DELETE | `/api/transactions/:id` | Delete a transaction |

Base URL: `http://localhost:5000`.

## Database
On first start, the server creates `server/data/expenses.db` and the required `transactions` table automatically. The database directory is generated at runtime and is excluded from Git.

## Suggested manual test checklist
- Add a valid income transaction and confirm the income total changes.
- Add a valid expense transaction and confirm expenses and balance change.
- Try an empty title, invalid category, zero/negative amount, and invalid date; confirm validation rejects them.
- Delete a transaction and confirm the totals recalculate.
- Restart the backend and confirm saved transactions remain.
- Resize the browser to check mobile responsiveness.

## Repository hygiene
`server/data/` and `node_modules/` are excluded by `.gitignore`. Do not commit database files, passwords, API keys, or other private credentials.


