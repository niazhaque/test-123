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

## **Repo layout**
# frontend (new terminal)
cd frontend && npm i && cp .env.example .env.local
# fill DOMAIN, CLIENT_ID, AUDIENCE, API_BASE_URL=http://localhost:4000
npm run dev

cruise0-auth0-poc/
├─ README.md
├─ .gitignore
├─ frontend/
│  ├─ .env.example
│  ├─ deploy.ps1
│  ├─ index.html
│  ├─ package.json
│  ├─ vite.config.ts
│  └─ src/
│     ├─ main.tsx
│     ├─ App.tsx
│     ├─ api.ts
│     ├─ auth.tsx
│     ├─ assets/
│     │  ├─ cruise-logo.png        (placeholder, replaceable)
│     │  └─ cruise-bg.jpg          (placeholder, replaceable)
│     └─ styles.css
├─ backend/
│  ├─ deploy.ps1
│  ├─ package.json
│  ├─ server.local.ts
│  ├─ lambda.ts
│  ├─ jwt.ts
│  ├─ tsconfig.json
│  └─ template.yaml                (AWS SAM: Lambda + HTTP API)
└─ auth0/
   ├─ universal-login.html
   ├─ action-pre-user-registration.js
   └─ action-post-login.js
