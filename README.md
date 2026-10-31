# Trade Journal

A self-hosted trading journal and analytics web platform to track trades, manage multiple accounts, and analyze risk metrics.

![Dashboard Preview](./docs/screenshots/dashboard.png)

## Features

- **Multi-Account Management**: Track demo and live accounts with balance, deposit, and withdrawal history.
- **Trade Logging**: Record entry and exit prices, lot sizes, P/L, R:R ratios, and strategy tags.
- **Chart Attachments**: Upload before-and-after trade charts with a built-in fullscreen viewer.
- **Performance Analytics**: Real-time Win Rate, Profit Factor, Average Win/Loss, Sharpe Ratio, and Max Drawdown.
- **Dark Terminal UI**: Minimalist, fast UI built with SvelteKit and Tailwind CSS.
- **Self-Hosted**: Go backend with PostgreSQL, MinIO (S3 object storage), JWT auth, and Docker Compose deployment.

## Quick Start (Docker)

Deploy the entire stack with Docker Compose:

```bash
# 1. Clone the repository
git clone https://github.com/RaihanStark/trade-journal.git
cd trade-journal

# 2. Set up environment variables
cp .env.example .env
cp web/.env.example web/.env

# 3. Start all services
docker compose up -d
```

Once started, access the services:
- **Frontend**: [http://localhost:3000](http://localhost:3000)
- **Backend API**: [http://localhost:8080](http://localhost:8080)
- **MinIO Console**: [http://localhost:9001](http://localhost:9001)

## Local Development

### Prerequisites
- Go 1.24+
- Node.js 18+ & pnpm
- Docker (for database & MinIO)

### Backend
```bash
# Start PostgreSQL & MinIO
make docker-up

# Run database migrations
make migrate-up

# Start API server (http://localhost:8080)
make run
```

### Frontend
```bash
cd web
pnpm install
pnpm dev
```
Frontend runs at [http://localhost:5173](http://localhost:5173).

## Tech Stack

- **Backend**: Go (Echo v4, sqlc, dbmate, Argon2, JWT)
- **Frontend**: SvelteKit (Svelte 5 runes, Tailwind CSS, Lucide)
- **Database & Storage**: PostgreSQL 16, MinIO
