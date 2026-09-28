# BizHub React + Express + MongoDB Connected Version

This ZIP contains the original React frontend and Express backend with the first real frontend/backend integration added.

## What is connected

- React login -> `POST /api/auth/login`
- React registration -> `POST /api/auth/register`
- React catalog -> `GET /api/products`
- React category data -> `GET /api/categories`
- React vendor data -> `GET /api/vendors`
- JWT is stored in `localStorage` as `bizhub_token`
- Logged-in user is stored as `bizhub_user`
- Existing UI is preserved; local mock data remains as a fallback if the backend is unavailable.

## Requirements

- Node.js
- MongoDB running locally on `mongodb://127.0.0.1:27017`

## 1. Start backend

Open terminal:

```text
cd backend/backend
npm install
npm run seed
npm run dev
```

Backend:

`http://localhost:5000`

## 2. Start frontend

Open another terminal:

```text
cd frontend/react
npm install
npm run dev
```

Frontend:

`http://localhost:5173`

## Demo credentials

- Buyer: `buyer@acme.com` / `password123`
- Vendor: `vendor@apex.com` / `password123`
- Admin: `admin@bizhub.com` / `password123`

## Important

The current backend product model uses MongoDB ObjectIds, while the old React UI used mock IDs such as `PRD-101`. `src/api.js` normalizes the MongoDB response into the shape expected by the existing React catalog.

The remaining cart/order/RFQ/dashboard actions are still using the existing frontend state. They can be migrated to their Express endpoints next without changing the overall architecture.
