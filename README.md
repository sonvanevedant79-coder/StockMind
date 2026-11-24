# StockMind – Online Stock Trading & Portfolio Management System

A beginner-friendly academic prototype based on the supplied SRS. It uses React + Vite, Express, SQLite, JWT and bcrypt. Trades use virtual cash and seeded sample prices; this is NOT connected to a broker or exchange and does not place real orders.

## Requirements
- Node.js 20 or newer (LTS recommended)
- VS Code (recommended)
- Internet connection for the first `npm install`

## 1. Start the backend
Open a terminal in the `server` folder:

```bash
npm install
```

Copy `.env.example` to `.env` (Windows PowerShell: `Copy-Item .env.example .env`; macOS/Linux: `cp .env.example .env`). Change `JWT_SECRET` to a long random value for any deployment.

Then run:

```bash
npm run dev
```

The API runs at http://localhost:5000. SQLite database `stockmind.db` is created automatically and seeded with sample stocks and an administrator account.

## 2. Start the frontend
Open a SECOND terminal in the `client` folder:

```bash
npm install
npm run dev
```

Open http://localhost:5173 in your browser.

## Demo administrator
- Email: `admin@stockmind.demo`
- Password: `Admin@123`

Create a normal investor account using the registration screen. Each new investor starts with ₹1,00,000 virtual cash.

## Implemented features
- Investor registration/login; passwords hashed with bcrypt; JWT authentication
- Sample stock search and market list
- Add/remove watchlist stocks
- Simulated buy/sell with quantity, cash and holdings validation
- Portfolio holdings, average purchase price, market value and unrealized P/L
- Transaction/order history
- Dashboard metrics and charts
- Admin user/order views and add-stock form
- Responsive layout inspired by the supplied StockMind reference images

## API routes
- `POST /api/auth/register`, `POST /api/auth/login`, `GET /api/auth/me`
- `GET /api/stocks?q=`
- `GET /api/dashboard`
- `GET /api/watchlist`, `POST /api/watchlist/:stockId`, `DELETE /api/watchlist/:stockId`
- `POST /api/trades`, `GET /api/orders`
- `GET /api/admin/users`, `GET /api/admin/orders`, `POST /api/admin/stocks`

## Important project notes
- Prices are sample values. They are not live NSE/BSE data and should not be described as real-time market prices.
- The app uses simulated cash only. It does not connect to a broker, payment service or exchange.
- Before production use, add HTTPS, stronger secrets, rate limiting, audit logging, validation, backups and security review. Do not deploy the demo admin credentials.
- The `stockmind.db` file stores local demo data. Stop the backend before deleting it to reset the database; it will be recreated and seeded at next start.

## Suggested 8-week academic plan (aligned to SRS)
1. Requirements and project setup
2. Database design and architecture/ER diagram
3. UI design and responsive frontend
4. Authentication and stock search
5. Buy/sell simulation and order records
6. Portfolio and P/L calculations
7. Testing, validation and bug fixing
8. User guide, screenshots, final report and presentation
