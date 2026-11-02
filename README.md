# VOLT — BYD EV Service Center

A full-stack graduation-project MVP for a BYD electric-vehicle maintenance center. It includes a responsive customer website, a BYD wireframe hero visual based on the image supplied in the conversation, service booking, an Express API, a SQLite database, admin authentication, and a bookings dashboard.

## Requirements
- Node.js 18 or newer
- npm

## Run locally
Open a terminal in this folder and run:

```bash
npm run install:all
```

Copy `server/.env.example` to `server/.env`, then change `JWT_SECRET`, `ADMIN_EMAIL`, and `ADMIN_PASSWORD` before using real customer data.

```bash
npm run dev
```

- Website: http://localhost:5173
- API health: http://localhost:5000/api/health
- Admin: click **Staff login** in the website footer

Default local demo login:
- Email: `admin@bydevcenter.com`
- Password: `ChangeMe123!`

Change these credentials and the JWT secret before deployment.

## Vehicle visual / optional real 3D model
The supplied BYD wireframe image is included at `client/public/byd-wireframe.png` and displayed in the hero with a subtle perspective and floating animation. It is a 2D image presentation, not a rotatable 3D mesh. The Three.js viewer is already wired to load a real model from:

`client/public/models/byd-car.glb`

If you later obtain a GLB, place it at that exact path. The viewer will load it automatically and replace the image fallback. No purchase is required to run the current project.

## Main API routes
- `POST /api/auth/login` — admin login
- `POST /api/appointments` — public booking submission
- `GET /api/appointments` — protected bookings list (`status`, `search` query filters)
- `GET /api/dashboard/stats` — protected dashboard counters
- `PATCH /api/appointments/:id/status` — update status
- `DELETE /api/appointments/:id` — delete booking

## Notes before production
This is a local graduation-project MVP, not a deployed production service. Before accepting real customer data, configure HTTPS, a strong secret and admin password, database backups, rate limiting, input validation, notification delivery, privacy/consent text, and a production database strategy. Add the center's real address, phone, maps link, and confirmed service policies. Do not claim authorized BYD dealer/service-partner status unless that authorization is confirmed.
