# Leave Request Management System

This project has:

- `client`: React + Vite frontend
- `server`: Express + MongoDB backend

## Local setup

### Backend

1. Go to `server`
2. Create `.env` from `.env.example`
3. Run:

```bash
npm install
npm run dev
```

### Frontend

1. Go to `client`
2. Create `.env` from `.env.example`
3. Run:

```bash
npm install
npm run dev
```

## Environment variables

### Backend `server/.env`

```env
PORT=5000
CLIENT_URL=http://localhost:5173
MONGODB_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret
MANAGER_AUTH_CODE=your_manager_authorization_code
```

### Frontend `client/.env`

```env
VITE_API_URL=http://localhost:5000/api
```

## Deploy backend on Render

1. Push this repo to GitHub
2. Log in to Render
3. Create a new `Web Service`
4. Connect this GitHub repo
5. Use these settings:

- Root Directory: `server`
- Build Command: `npm install`
- Start Command: `npm start`

6. Add environment variables:

- `CLIENT_URL` = your frontend URL
- `MONGODB_URI` = your MongoDB Atlas connection string
- `JWT_SECRET` = your secret key
- `MANAGER_AUTH_CODE` = your manager code

After deploy, your API URL will look like:

```text
https://your-render-service.onrender.com/api
```

## Deploy frontend on Vercel

1. Log in to Vercel
2. Import this GitHub repo
3. Set the root directory to `client`
4. Add environment variable:

- `VITE_API_URL` = `https://your-render-service.onrender.com/api`

5. Deploy

After deploy, your app URL will look like:

```text
https://your-project.vercel.app
```

## Important

After deploying frontend, update backend `CLIENT_URL` in Render to your real Vercel URL and redeploy the backend if needed.
