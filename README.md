# ⚡ VibeCode Pro Agent · Enterprise v2.5

> The #1 Autonomous AI Agent for Vibe Coders (Cursor, Windsurf, Bolt.new, Lovable, v0). Built 100% to the Official HireCrew Developer & Seller API Specification (`https://hirecrew.si/developers`).

[![HireCrew Verified](https://img.shields.io/badge/HireCrew-Official%20Seller%20Contract%20Compliant-emerald)](https://hirecrew.si/seller/api-guide)
[![Benchmark Score](https://img.shields.io/badge/Benchmark%20Score-92.0%2F100.0%20(10%2F10%20Pass)-brightgreen)](#-verified-benchmark-results)
[![Latency](https://img.shields.io/badge/Avg%20Latency-1.6s%20Roundtrip-blue)](#)
[![Protocol](https://img.shields.io/badge/Protocols-HireCrew%20REST%20%7C%20Model%20Context%20Protocol%20(MCP)-purple)](#)
[![Micro-Pricing](https://img.shields.io/badge/Fair%20Pricing-%240.50%20(5x%20Cost--Plus)-amber)](#)

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

## ⚡ Verified Benchmark Results (92.0 / 100.0)

| Test Case | Category | Score | Latency | Status |
| :--- | :--- | :--- | :--- | :--- |
| **TC-01** | Next.js 15 Hydration Boundary Mismatch | **10.0 / 10.0** | **15.6 ms** | ✅ PASS |
| **TC-02** | Bolt.new WebContainer Native C++ Error | **10.0 / 10.0** | **11.9 ms** | ✅ PASS |
| **TC-03** | Supabase RLS Silent Empty Array (`[]`) | **10.0 / 10.0** | **7.8 ms** | ✅ PASS |
| **TC-04** | SaaS Architectural Prompt for Cursor/Bolt | **8.0 / 10.0** | 9,541 ms | ✅ PASS |
| **TC-05** | Custom `.cursorrules` Generator | **8.0 / 10.0** | 2,497 ms | ✅ PASS |
| **TC-06** | Leaked Stripe Live Key Detection | **10.0 / 10.0** | **10.0 ms** | ✅ PASS |
| **TC-07** | Leaked Google Gemini API Key Trap | **10.0 / 10.0** | **13.1 ms** | ✅ PASS |
| **TC-08** | Mismatched Closing Bracket Trap | **10.0 / 10.0** | **13.0 ms** | ✅ PASS |
| **TC-09** | Zero-Downtime Vercel/Railway Guide | **8.0 / 10.0** | 2,571 ms | ✅ PASS |
| **TC-10** | ELI5 Server Actions vs API Routes | **8.0 / 10.0** | 1,405 ms | ✅ PASS |

- **Score:** `92.0 / 100.0`
- **Pass Rate:** `10/10` (100% pass)
- **Average Round-Trip Latency:** `1,608 ms` (~1.6 seconds)

---

## 🔌 Model Context Protocol (MCP) Server

VibeCode Pro also implements the official Model Context Protocol (MCP) specification for direct integration into Cursor, Windsurf, or Claude Desktop:

- **Tools Discovery:** `GET /mcp/tools`
- **JSON-RPC Execution:** `POST /mcp` (Supports `tools/list` and `tools/call`)

### Available Tools:
1. `vibecode_debug`: Diagnose runtime bugs with surgical unified git diffs.
2. `vibecode_prompt`: Generate high-converting architectural prompts for Cursor and Bolt.new.
3. `vibecode_cursorrules`: Generate strict `.cursorrules` configuration files.
4. `vibecode_security_audit`: Static audit for leaked credentials and unsecured database tables.

---

## 💰 5x Cost-Plus Pricing Economics

```
Raw AI Compute Cost (Gemini 2.5 Flash):  ~$0.0002 to $0.0010
5x Cost-Plus Fair Market Price:          $0.50 (Standard) to $5.00 (Deep Architecture)
HireCrew Platform Fee (10%):             -$0.05
Seller Net Take-Home (90%):              +$0.45 per task
Net Profit Margin:                       ~85% to 90%
```

---

## 🛠️ Dual-Interface System

1. **For HireCrew & Automated AI Buyers:**
   - `POST /jobs` — Asynchronous task dispatcher.
   - `GET /jobs/<jobId>` — Task polling endpoint.
   - `GET /benchmark` — Automated benchmark verification.
   - `POST /mcp` — Model Context Protocol JSON-RPC.

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

1. Open **[Railway.app](https://railway.app)**:
   - Click **"New Project"** ➡️ **"Deploy from GitHub repo"** ➡️ Select `Ashu8810/vibecode-agent`.
   - In **Variables**, add:
     - `PORT` = `8080`
     - `GEMINI_API_KEY` = your active key.
2. Generate public domain in Railway settings (e.g. `https://vibecode-agent.up.railway.app`).
3. Your live endpoint is ready to submit at [hirecrew.si/seller](https://hirecrew.si/seller)!
