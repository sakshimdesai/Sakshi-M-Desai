<div align="center">

# Hi, I'm Sakshi 👋

### Final-year Information Science engineer building backend systems, full-stack platforms, and AI-powered tools

[![Email](https://img.shields.io/badge/Email-sakshidesai1165%40gmail.com-D14836?style=flat-square&logo=gmail&logoColor=white)](mailto:sakshidesai1165@gmail.com)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-sakshimdesai-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/sakshimdesai)
[![GitHub](https://img.shields.io/badge/GitHub-sakshimdesai-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/sakshimdesai)
[![Location](https://img.shields.io/badge/Based%20in-Bengaluru%2C%20India-informational?style=flat-square)]()

</div>

---

## About Me

I care about shipping things that actually work — not just in theory. Almost everything below started with "how do I fix this specific, annoying problem" rather than "what would look good on a resume." That shows up in the architecture decisions as much as the feature lists: a mock server that generates routes it doesn't know about yet, an AI health layer that's structurally forbidden from hallucinating, an ERP that refuses to let inventory go negative.

Final year of **B.E. Information Science & Engineering** at Dayananda Sagar Academy of Technology and Management (graduating 2027) — currently open to **SWE / Backend / AI Engineering** roles.

---

## 🛠️ Tech I Work With

**Languages**
![Python](https://img.shields.io/badge/-Python-3776AB?style=flat-square&logo=python&logoColor=white)
![TypeScript](https://img.shields.io/badge/-TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white)
![JavaScript](https://img.shields.io/badge/-JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black)
![SQL](https://img.shields.io/badge/-SQL-4479A1?style=flat-square&logo=postgresql&logoColor=white)

**Backend**
![Flask](https://img.shields.io/badge/-Flask-000000?style=flat-square&logo=flask&logoColor=white)
![NestJS](https://img.shields.io/badge/-NestJS-E0234E?style=flat-square&logo=nestjs&logoColor=white)
![FastAPI](https://img.shields.io/badge/-FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white)
![Node.js](https://img.shields.io/badge/-Node.js-339933?style=flat-square&logo=node.js&logoColor=white)
![GraphQL](https://img.shields.io/badge/-GraphQL-E10098?style=flat-square&logo=graphql&logoColor=white)

**Data & Infra**
![PostgreSQL](https://img.shields.io/badge/-PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![SQLite](https://img.shields.io/badge/-SQLite-003B57?style=flat-square&logo=sqlite&logoColor=white)
![Redis](https://img.shields.io/badge/-Redis-DC382D?style=flat-square&logo=redis&logoColor=white)
![Docker](https://img.shields.io/badge/-Docker-2496ED?style=flat-square&logo=docker&logoColor=white)

**AI / ML**
![scikit-learn](https://img.shields.io/badge/-scikit--learn-F7931E?style=flat-square&logo=scikit-learn&logoColor=white)
![Pandas](https://img.shields.io/badge/-Pandas-150458?style=flat-square&logo=pandas&logoColor=white)
`Gemini API` `LLM App Development` `Prompt Engineering` `Groq / LLaMA` `OpenCLIP`

**Frontend**
![React](https://img.shields.io/badge/-React-61DAFB?style=flat-square&logo=react&logoColor=black)
![Flutter](https://img.shields.io/badge/-Flutter-02569B?style=flat-square&logo=flutter&logoColor=white)
`Chart.js` `Streamlit`

---

## 💼 Experience

**Software Engineering Intern — UnknwnAI Ltd** (UK-based startup, Remote) · Mar – May 2026

Independently owned an event-driven ERP ↔ Shopify integration spanning 30–40 files across 10+ modules and 3 APIs:
- Designed the **inventory sync** system using the **Outbox Pattern**, checkpointing, latest-event coalescing, retry handling, and dead-letter recovery — so stale updates get caught and failures recover cleanly instead of silently corrupting state.
- Built **Shopify Dispatch Sync**: ERP-to-Shopify order and fulfillment mapping via GraphQL, with fulfillment creation and tracking updates verified end-to-end in Shopify.
- Validated the system through 40–60 API executions and 10+ E2E scenarios, debugging across 10–12 failure categories spanning PostgreSQL, queues, workers, and the Shopify/GraphQL layer.

`TypeScript` `NestJS` `PostgreSQL` `Redis` `BullMQ` `Shopify GraphQL API`

---

## 🚀 Featured Projects

### 🕸️ [GhostRoute](https://github.com/sakshimdesai/GhostRoute) — Runtime API Mock Generation Platform
*"YourAPI, before it exists."*

Turns an uploaded OpenAPI spec into a **live, configurable mock server** — instantly, with zero backend code. The interesting problem: FastAPI resolves routes via decorators at *startup*, but GhostRoute's endpoints don't exist yet at that point — they're only known once someone uploads a spec, which could happen anytime after the server is already running and serving other projects. Looping over the spec and registering routes post-startup is fragile and fights the framework. Instead, the entire app runs on **one catch-all route** (`/mock/{project_id}/{full_path:path}`), with a hand-rolled dispatcher underneath: incoming requests get matched against a table of regex-compiled path patterns (`{id}` → named capture group), resolved to the right project, and routed through an 8-stage pipeline — lookup → route match → parameter extraction → config lookup → override check → mock generation → logging → response.

- Schema-driven fake data generation, recursing through nested JSON Schema objects/arrays across all 6 primitive types
- Per-endpoint latency simulation and error-rate injection — non-blocking, via `asyncio.sleep()` inside async handlers, so one slow mock doesn't stall the others
- Response overrides + full request logging, surfaced on a live React dashboard, all persisted in SQLite via SQLAlchemy so state survives a restart
- Solo-built in ~3 weeks (~30 commits, 70% backend), fully Dockerized with a multi-stage frontend build and Docker Compose, verified working end-to-end

`React` `FastAPI` `SQLite` `SQLAlchemy` `Docker`

---

### 📦 [OpsFlow](https://github.com/sakshimdesai/OpsFlow) — Mini ERP + CRM Operations Portal
A 48-hour solo case-study build that behaves like production software, not a demo: a full-stack ERP/CRM for a wholesale/distribution business, built end-to-end and deployed live.

- CRM, product & inventory management, and sales-challan workflows across **18 REST endpoints**
- The core design decision: the **challan-to-inventory pipeline** validates stock *before* confirming a sale, blocks the system from ever going negative, then auto-deducts quantities and writes IN/OUT stock-movement records with transaction-level product snapshots — so every inventory change is auditable after the fact
- **JWT-based RBAC across 4 roles** (Admin / Sales / Warehouse / Accounts), enforced with NestJS guards and a global `ValidationPipe` (`whitelist`, `forbidNonWhitelisted`) that rejects any request carrying fields it doesn't expect — verified via role-restricted 403 testing
- Deployed live: NestJS backend on Render, React frontend on Vercel, PostgreSQL via TypeORM

`NestJS` `TypeScript` `PostgreSQL` `TypeORM` `React` `JWT`

---

### 🎣 [PhishDetect-India](https://github.com/sakshimdesai/PhishDetect-India) — ML-Based Multilingual Phishing Detection
Most phishing detectors — including Google Safe Browsing — are trained almost entirely on Western data, and miss India-specific attack patterns: fake UPI pages impersonating PhonePe/GPay, IRCTC/DigiLocker spoofs, KYC and account-blocking scams, and urgency-driven Hinglish/Kannada SMS. This project targets exactly that gap.

- Two independent pipelines: **URL detection** (structural features + Random Forest) and **SMS detection** (TF-IDF + 17 handcrafted features), covering **5 language/script categories** — English, Hindi, Kannada, Hinglish, and Konglish
- Stress-tested the model specifically on reward-phishing SMS, watched it collapse to **18.18% accuracy**, traced it to a vocabulary gap in training data, and closed it by generating 60 targeted samples — producing a final balanced set of 2,260 SMS samples across 5,962 features
- **99.56% accuracy, 100% recall, 99.99% ROC-AUC, zero phishing false negatives** on the final classifier
- SHAP values explain every individual prediction; structured as a production-style Python package (`src/data`, `src/features`, `src/prediction`) rather than notebook code, so the trained models are reusable, not one-off

`Python` `Random Forest` `TF-IDF` `SHAP` `Flask` `React` `SQLite`

---

### 🩺 [Hormone Harmony](https://github.com/sakshimdesai/Hormone-Harmony) — PCOS Wellness & Behavioral Analytics Platform
Generic period trackers assume a 28-day cycle. PCOS breaks that model entirely — irregular cycles, hormonal variability, symptoms that don't fit standard tracking. Hard constraint from day one: **no cycle prediction, no diagnosis** — the ethics are architectural, not a disclaimer bolted on afterward.

- 13–15 Flask endpoints, 6 SQLite tables: symptom/cycle logging, a myth-busting module targeting real Indian misconceptions, PCOS-specific meal guidance (each recipe tagged with *why* it helps — insulin, cortisol, or androgen pathway, not generic "healthy eating"), and an education hub covering all **four clinically distinct PCOS subtypes** (insulin-resistant, inflammatory, adrenal, post-pill)
- **Symptom Correlation Engine**: pandas + `scipy.stats.pearsonr` computing real statistical correlations — sleep↔fatigue, stress↔acne, exercise↔mood, and more — where every single pair was chosen for a documented PCOS clinical mechanism, not picked arbitrarily
- **AI Wellness Summaries**: a Gemini-powered layer that narrates the *computed* correlations in plain English. The architecture is deliberately **compute → constrain → communicate**: the LLM never sees raw logs, only pre-computed statistical facts, so it can describe real patterns but can't invent ones that aren't there — and every response is validated to strip diagnostic language before a user sees it

`Flask` `SQLite` `pandas` `scipy` `Gemini API` `Chart.js`

---

### 🔁 [Reflexion Code Agent](https://github.com/sakshimdesai/Reflexion-Code-Agent) — Self-Correcting Agentic Code Generation
Most AI code tools stop at generating code — you still run it, hit the error, and paste it back yourself. This closes that loop entirely.

- Generate → execute (via `subprocess`) → capture the *real* runtime error → feed it back to the LLM → retry, until the code actually runs
- Built on LLaMA 3.1 via Groq, with a Streamlit UI exposing the full iteration history and debug logs — not a black box, you can see every attempt

`Python` `Groq API` `LLaMA 3.1` `Streamlit`

---

### ✍️ [LinkGen AI](https://github.com/sakshimdesai/LinkGen-AI) — Multi-Model LinkedIn Content Generator
Not another single-shot LinkedIn post generator. Lets you compare how LLaMA 3.1 8B vs. 70B handle the *identical* prompt side by side, and generates formal + casual tone variants in one click — with genuinely distinct prompt conditioning per tone, not keyword swaps. Supports English, Hindi, and Kannada.

`Python` `Groq API` `Streamlit` `Prompt Engineering`

---

### 🧾 [GroupReceipt](https://github.com/sakshimdesai/GroupReceipt) — Evidence-Gated Group Contribution Tracker
Self-reported hours in group projects are unverifiable and trivially gameable. GroupReceipt makes it **structurally impossible** to mark a task done without pasting a real proof link — GitHub, a Doc, Figma, Drive, anything with a URL. No link, no "done."

- Generates a shareable visual receipt with each member's completion % and a verdict — *Carried / Solid / Barely There / Ghost* — built to be sent straight to a professor or group chat
- No accounts, no friction: join a project with a 5-character code, identity persisted locally via `SharedPreferences`
- Firestore-backed live board so every member sees everyone else's task status and evidence links in real time — social accountability throughout the project, not just a reckoning at the end

`Flutter` `Dart` `Firebase Firestore`

---

## 🧪 Other Builds

- **Fashion Product Retrieval (OpenCLIP)** — AlgoUniversity GenAI Bootcamp assessment. One shared OpenCLIP embedding pipeline powering three distinct retrieval tasks — complementary-product recommendation (category-filtered + cosine similarity), near-duplicate detection (embedding clustering), and natural-language product search (text↔image cross-modal retrieval) — with zero task-specific training.
- **Placement Hub** — Flask + SQLite platform serving DSA/aptitude/HR prep content, deployed on Render. The admin panel was deliberately removed before launch — not hidden, removed — to cut attack surface on a public-facing, read-only system.
- **Sabai Mini** — AI health check-in agent (n8n + Telegram + Claude)- Includes a deterministic red-flag safety gate that intercepts urgent-symptom keywords and routes straight to an escalation message *before* the LLM ever sees the message.

---

## 🏆 Hackathons & Recognition

- **American Express CodeStreet 2026** — *Consent Rail*: a governance layer for autonomous financial agents (trust scoring, policy enforcement, audit logging, authorization)
- **SEBI Securities Market TechSprint 2026** — *Compliance Evolution Engine*: converts regulatory circulars into structured compliance actions via obligation extraction and clause-backed recommendations
- **Varroc Eureka Challenge 3.0** — AI-driven design intelligence system for early-stage CAD validation (Team Synara)
- **Tata Elxsi TELIPORT Season 3** — *SafetyGate GenAI*, a safety-validation framework for software-defined vehicle workflows
- **UNESCO Youth Hackathon 2025** — *News Nutrition Label*, an NLP framework for scoring news credibility and bias
- **Walmart Global Tech Sparkathon 2025** — *Smart Cart*, location-based grocery discovery matched to dietary preferences

## 📜 Certifications

- **SAP Certified – Data Analyst (SAP Analytics Cloud, C_SAC)** — enterprise analytics, dashboard design, analytical data modeling and planning

---

## 📊 GitHub Activity

<div align="center">
  <img height="165" src="https://github-readme-stats.vercel.app/api?username=sakshimdesai&show_icons=true&theme=tokyonight" alt="GitHub stats" />
  <img height="165" src="https://github-readme-stats.vercel.app/api/top-langs/?username=sakshimdesai&layout=compact&theme=tokyonight" alt="Top languages" />
</div>

---

<div align="center">

### 📫 Let's connect

📧 sakshidesai1165@gmail.com · 💼 [LinkedIn](https://www.linkedin.com/in/sakshimdesai) · 💻 [GitHub](https://github.com/sakshimdesai) · 🌐 Bengaluru, India

*Always building. Open to SWE / Backend / AI roles.*

</div>
