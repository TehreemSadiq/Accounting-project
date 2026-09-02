# Short Report — Ledger Assistant (Income & Expense Tracker with AI Agent)

**Subject:** Principles of Accounting (ACFC101)
**Assignment No. 02**

## Project Idea
A single-page web app that keeps a running ledger of transactions and includes a simple
rule-based "AI agent" (chat interface) that responds to plain-text commands by drawing
live charts and reporting totals — satisfying the requirement to show graphs, charts, and
dynamic views of accounting data through an agent/chatbot.

## Accounting Logic Implemented

1. **The Accounting Equation (Assets = Liabilities + Equity)**
   Every transaction entered is classified as either **income** (increases equity/assets)
   or **expense** (decreases equity/assets). The app's `type` field mirrors this classification.

2. **Revenue and Expense Recognition**
   Each transaction is recorded with a date, description, category, type, and amount —
   the same fields used in a real journal entry. Sales and capital deposits are recognized
   as income; rent, inventory purchases, and marketing costs are recognized as expenses.

3. **Net Profit / Loss Calculation**
   The core formula used throughout the app is:

   ```
   Net Profit = Total Income − Total Expenses
   ```

   This is recalculated live every time a new transaction is added, and displayed both
   as a number (dashboard card) and visually (bar chart comparing income, expenses, and
   net profit).

4. **Categorization (Chart of Accounts, simplified)**
   Transactions are grouped into categories (Capital, Sales, Inventory, Rent, Marketing).
   This mirrors how a real chart of accounts groups similar transactions, and lets the
   pie charts show which categories contribute most to income or expense.

5. **The Ledger / Journal**
   All transactions are displayed in a running table (the ledger), in the order they were
   recorded — analogous to a general journal in manual bookkeeping.

## How the "AI Agent" Works
The chat box accepts plain-English commands (`profit`, `expenses`, `income`,
`add [desc], [category], [income|expense], [amount]`). A simple keyword-matching function
interprets the command, updates the in-memory ledger array if needed, and redraws the
relevant Chart.js visualization — giving a dynamic, conversational view of the books
instead of a static report.

## Sample Transactions Demonstrated
1. Owner's capital deposit — PKR 50,000 (income)
2. Sold handmade candles — PKR 18,000 (income)
3. Bought raw wax & wicks — PKR 9,000 (expense)
4. Shop rent — PKR 12,000 (expense)
5. Instagram ad boost — PKR 3,000 (expense)
6. Sold gift boxes — PKR 9,500 (income)

## Tech Used
Plain HTML, CSS, and JavaScript, with Chart.js (via CDN) for visualizations. No backend
or database required — the whole project runs by opening `index.html` in a browser, which
also makes it easy to host on GitHub Pages for the demo.
