# **Cruise0 – Auth0 PoC (React + Node/Lambda)**

**Features**
- **Auth0 Universal Login** (custom: Cruise ship theme)
- **Disposable email block** (Pre-User Registration Action)
- **Post-Login**: **Require MFA** for non-social, **Geo-IP country**, **Enforce email verification**
- **Frontend**: React (Vite), **Login/Logout**, **email_verified UI check**, **Audience-based token**, **Bearer API call**
- **Backend**: Node.js Express (local) + **AWS Lambda + HTTP API** (SAM)
- **1-click deploy**: `frontend/deploy.ps1` (S3+CloudFront), `backend/deploy.ps1` (SAM)

## Local Run
```bash
# backend
cd backend && npm i && npm run dev

# frontend (new terminal)
cd frontend && npm i && cp .env.example .env.local
# fill DOMAIN, CLIENT_ID, AUDIENCE, API_BASE_URL=http://localhost:4000
npm run dev
