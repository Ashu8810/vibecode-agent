# ⚡ VibeCode Pro Agent · Enterprise v2.1

> Built 100% to the Official HireCrew Developer & Seller API Specification (`https://hirecrew.si/developers` & `https://hirecrew.si/seller/api-guide`).

[![HireCrew Verified](https://img.shields.io/badge/HireCrew-Official%20Seller%20Contract%20Compliant-emerald)](https://hirecrew.si/seller/api-guide)
[![API Contract](https://img.shields.io/badge/API-POST%20%2Fjobs%20%7C%20GET%20%2Fjobs%2F%3Cid%3E-blue)](#)
[![Engines](https://img.shields.io/badge/Vibe%20Engines-Cursor%20%7C%20Bolt%20%7C%20Lovable%20%7C%20v0-purple)](#)

---

## 📋 HireCrew Official Developer Specification Compliance

According to [hirecrew.si/developers](https://hirecrew.si/developers) and [hirecrew.si/seller/api-guide](https://hirecrew.si/seller/api-guide), all seller-hosted agents must implement:

### 1. Task Submission Contract (`POST /jobs`)
```http
POST https://your-agent.up.railway.app/jobs
Authorization: Bearer <reviewed integration token>
Idempotency-Key: <stable-order-key>
Content-Type: application/json

{
  "orderId": "hc-order-uuid-99",
  "brief": "Fix Next.js 15 hydration error in Navbar component"
}
```
**Immediate Response (Status 202 Accepted):**
```json
{
  "jobId": "vibecode-710f7d3cb2",
  "status": "queued"
}
```

### 2. Task Polling Contract (`GET /jobs/<jobId>`)
HireCrew polls the same endpoint with the safe job ID path segment:
```http
GET https://your-agent.up.railway.app/jobs/vibecode-710f7d3cb2
```
**Final Response (Status 200 OK):**
```json
{
  "jobId": "vibecode-710f7d3cb2",
  "status": "delivered",
  "report": "Root cause analysis, surgical code fix, and next action steps...",
  "sources": [
    { "title": "Cursor AI Rules Reference", "url": "https://docs.cursor.com/context/rules-for-ai" },
    { "title": "Next.js App Router Documentation", "url": "https://nextjs.org/docs/app" },
    { "title": "Bolt.new WebContainer Environment", "url": "https://webcontainers.io" }
  ]
}
```

### 3. Idempotency Key Handling
If HireCrew or the buyer retries a request with the same `Idempotency-Key` or `orderId`, VibeCode Pro instantly returns the existing `jobId` from cache to avoid duplicate billing and redundant executions.

---

## 🛠️ Dual-Interface System

1. **For HireCrew & Automated AI Buyers:**
   - `POST /jobs` — Asynchronous task dispatcher.
   - `GET /jobs/<jobId>` — Task polling endpoint.
   - `GET /benchmark` — Automated benchmark verification.

2. **For Human Vibe Coders (Web UI):**
   - Open `http://localhost:8080/` in any browser.
   - Interactive Glassmorphism UI with live diagnostics for:
     - 🐛 Debugging broken code & hydration errors.
     - ✍️ Crafting architecture prompts for Cursor & Bolt.
     - 📄 Generating `.cursorrules`.
     - 🔍 Auditing code for security and leaked API keys.
     - 🚀 Zero-downtime deployment recipes.

---

## 🚀 Deploy to Railway for Public URL (Ready for HireCrew)

1. Push this folder to GitHub:
   ```bash
   cd /Users/ashu/Desktop/vibecode-agent
   git init
   git add .
   git commit -m "HireCrew Compliant VibeCode Pro"
   # Push to your GitHub repo
   ```
2. Open **[Railway.app](https://railway.app)**:
   - Click **"New Project"** ➡️ **"Deploy from GitHub"** ➡️ Select `vibecode-agent`.
   - In **Variables**, add:
     - `PORT` = `8080`
     - `GEMINI_API_KEY` = your active key.
3. Your live endpoint is ready to submit at [hirecrew.si/seller](https://hirecrew.si/seller)!
