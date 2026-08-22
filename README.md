<div align="center">

# Hi, I'm Sakshi 👋

### Final-year Information Science engineer building backend systems, full-stack platforms, and AI-powered tools

[![Email](https://img.shields.io/badge/Email-sakshidesai1165%40gmail.com-D14836?style=flat-square&logo=gmail&logoColor=white)](mailto:sakshidesai1165@gmail.com)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](www.linkedin.com/in/sakshimdesai)
[![Location](https://img.shields.io/badge/Based%20in-Bengaluru%2C%20India-informational?style=flat-square)]()

</div>

---

## About Me

I care about shipping things that actually work — not just in theory. Most of what's below started as "how do I solve this specific, annoying problem" rather than "what would look good on a resume." That shows up in the architecture decisions as much as in the feature lists.

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
`Gemini API` `LLM App Development` `Prompt Engineering` `Groq / LLaMA`

**Frontend**
![React](https://img.shields.io/badge/-React-61DAFB?style=flat-square&logo=react&logoColor=black)
![Flutter](https://img.shields.io/badge/-Flutter-02569B?style=flat-square&logo=flutter&logoColor=white)
`Chart.js` `Streamlit`

---

## 💼 Experience

**Software Engineering Intern — UnknwnAI Ltd** (UK-based startup, Remote) · Mar – May 2026

Independently built event-driven ERP ↔ Shopify integration pipelines spanning 30–40 files and 10+ modules:
- Designed the **inventory sync** system using the **Outbox Pattern**, checkpointing, latest-event coalescing, retry handling, and dead-letter recovery — catching stale updates and recovering cleanly from failures.
- Built **Shopify Dispatch Sync**, mapping ERP orders to Shopify fulfillment via GraphQL, verified end-to-end in Shopify.
- Validated the system through 40–60 API executions and 10+ E2E scenarios, debugging across PostgreSQL, queues, workers, and the Shopify/GraphQL layer.

`TypeScript` `NestJS` `PostgreSQL` `Redis` `BullMQ` `Shopify GraphQL API`

---

## 🚀 Featured Projects

### 🕸️ GhostRoute — Runtime API Mock Generation Platform
*"YourAPI, before it exists."*

Turns an uploaded OpenAPI spec into a **live, configurable mock server** — no backend code, no server restart. The core engineering problem: FastAPI registers routes via decorators at startup, but GhostRoute's endpoints aren't known until *after* a spec is uploaded — possibly long after the server is already running. Solved it with a single catch-all route and a custom regex-based request dispatcher instead of fighting FastAPI's routing model.

- Dynamic mock endpoints generated at runtime, with path-parameter matching via compiled regex
- Per-endpoint latency simulation and error-rate injection — non-blocking, via `asyncio.sleep()` inside async handlers
- Response override system, request logging, and a live React dashboard — all persisted in SQLite via SQLAlchemy
- Fully Dockerized: multi-stage frontend build + Docker Compose, verified working end-to-end

`React` `FastAPI` `SQLite` `SQLAlchemy` `Docker`

---

### 📦 OpsFlow — Mini ERP + CRM Operations Portal
Full-stack ERP/CRM system for a wholesale/distribution business, built solo end-to-end and deployed live.

- CRM, product & inventory management, and sales-challan workflows across 18 REST endpoints
- Challan-to-inventory pipeline that validates stock before confirming a sale, blocks negative inventory, and auto-generates IN/OUT stock movement records with transaction-level snapshots
- JWT-based RBAC across 4 roles (Admin / Sales / Warehouse / Accounts), enforced with NestJS guards and global DTO validation — verified via role-restricted 403 testing
- Deployed: NestJS backend on Render, React frontend on Vercel, PostgreSQL via TypeORM

`NestJS` `TypeScript` `PostgreSQL` `TypeORM` `React` `JWT`

---

### 🎣 PhishDetect-India — ML-Based Multilingual Phishing Detection
Phishing/scam detection tuned for Indian patterns that Western-trained tools (like Google Safe Browsing) systematically miss — fake UPI pages, IRCTC/DigiLocker impersonation, Hinglish urgency language, regional SMS scams.

- Two independent pipelines: **URL detection** (structural features + Random Forest) and **SMS detection** (TF-IDF + 17 handcrafted features across English, Hindi, Kannada, Hinglish, Konglish)
- Stress-tested the model on reward-phishing SMS, found it collapsing to 18.18% accuracy, diagnosed the vocabulary gap, and closed it with targeted sample generation
- **99.56% accuracy, 100% recall, 99.99% ROC-AUC**, zero phishing false negatives on the final SMS classifier
- SHAP values explain individual predictions; reusable prediction modules with confidence outputs

`Python` `Random Forest` `TF-IDF` `SHAP` `Flask` `React` `SQLite`

---

### 🩺 Hormone Harmony — PCOS Wellness & Behavioral Analytics Platform
Built for a gap generic period trackers ignore: PCOS breaks the standard 28-day cycle model. No cycle prediction, no diagnosis — ethics built into the architecture, not bolted on.

- 13–15 Flask endpoints, 6 SQLite tables — symptom/cycle logging, myth-busting (India-specific), meal guidance, and an education hub covering all four PCOS clinical subtypes
- **Symptom Correlation Engine**: pandas + `scipy.stats.pearsonr` computing real statistical correlations (sleep↔fatigue, stress↔acne, exercise↔mood, and more) between lifestyle factors and PCOS symptoms — every pair chosen for a documented clinical mechanism, not arbitrarily
- **AI Wellness Summaries**: a Gemini-powered layer that narrates the *computed* correlations in plain English — the LLM only ever sees pre-computed facts, never raw logs, so it can't hallucinate patterns it wasn't given
- Output is validated to filter diagnostic language before it ever reaches the user

`Flask` `SQLite` `pandas` `scipy` `Gemini API` `Chart.js`

---

### 🔁 Reflexion Code Agent — Self-Correcting Agentic Code Generation
A closed-loop system that doesn't stop at generating code: it runs it, captures the real runtime error, feeds that back to the LLM, and retries until the code actually works.

- Generate → execute (via subprocess) → reflect on the error → fix → repeat
- Built on LLaMA 3.1 via Groq, with a Streamlit UI exposing full iteration history and debug logs

`Python` `Groq API` `LLaMA 3.1` `Streamlit`

---

### ✍️ LinkGen AI — Multi-Model LinkedIn Content Generator
Compares how LLaMA 3.1 8B vs. 70B handle the *same* prompt side by side, and generates formal + casual tone variants in one click — with distinct prompt conditioning per tone rather than keyword swaps. Supports English, Hindi, and Kannada.

`Python` `Groq API` `Streamlit` `Prompt Engineering`

---

### 🧾 GroupReceipt — Evidence-Gated Group Contribution Tracker
Solves a specific problem: self-reported hours in group projects are unverifiable and easy to game. GroupReceipt makes it structurally impossible to mark a task done without a real proof link (GitHub, Doc, Figma, Drive), then generates a shareable "receipt" with each member's completion % and a verdict — *Carried / Solid / Barely There / Ghost*.

- No accounts — join a project with a 5-character code, stored locally via SharedPreferences
- Firestore-backed live board so every member sees every other member's task status and evidence in real time

`Flutter` `Dart` `Firebase Firestore`

---

## 🧪 Other Builds

- **Fashion Product Retrieval (OpenCLIP)** — AlgoUniversity GenAI Bootcamp assessment. One shared OpenCLIP embedding pipeline powering three tasks: complementary-product recommendation (category-filtered + cosine similarity), near-duplicate detection (embedding clustering), and natural-language product search (text↔image cross-modal retrieval) — all without task-specific training.
- **Placement Hub** — Flask + SQLite platform serving DSA/aptitude/HR prep content, deployed on Render. The admin panel was deliberately removed before launch to cut attack surface on a public-facing, read-only system.
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
  <img height="165" src="https://github-readme-stats.vercel.app/api?username=<your-github-username>&show_icons=true&theme=tokyonight" alt="GitHub stats" />
  <img height="165" src="https://github-readme-stats.vercel.app/api/top-langs/?username=<your-github-username>&layout=compact&theme=tokyonight" alt="Top languages" />
</div>

---

<div align="center">

### 📫 Let's connect

📧 sakshidesai1165@gmail.com · 💼 [LinkedIn](<www.linkedin.com/in/sakshimdesai>) · 🌐 Bengaluru, India

*Always building. Open to SWE / Backend / AI roles.*

</div>
