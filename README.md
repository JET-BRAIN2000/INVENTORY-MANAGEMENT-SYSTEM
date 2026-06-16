Jemima Inventory — Local Development

This project has a frontend (Vite + React) and a backend (`server/`) using MySQL.

Quick frontend setup

1. Create a root `.env` file (already present) containing the API URL used by the frontend:

```env
VITE_API_URL=http://localhost:4000
```

Vite reads `VITE_`-prefixed variables from the repository root `.env` file when running `vite`/`npm run dev`.

2. Install and run the frontend:

```bash
npm install
npm run dev
```

Backend & database

1. Configure the database credentials in `server/.env` (or use the provided `server/.env.example`).
2. Create the database and run the schema:

```bash
mysql -u root -p < server/migrations/schema.sql
```

3. Install and run the server, then seed sample data:

```bash
cd server
npm install
npm run seed      # inserts demo admin user, store, categories, inventory and sample sales
npm run dev
```

Login (demo credentials)

- username: `admin`
- password: `Admin@123`

Notes

- If you change backend port or host, update `VITE_API_URL` in the root `.env` accordingly.
- The frontend stores the JWT locally in `localStorage` as part of the auth flow; keep the API URL consistent to avoid CORS/auth issues.

