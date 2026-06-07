# Hi, I'm Sakshi !

I'm a final-year  Engineering student, building backend systems, full-stack web apps, and AI-powered tools. I care about shipping things that actually work — not just in theory.

📍 Bengaluru, India &nbsp;|&nbsp; 📧 sakshidesai1165@gmail.com &nbsp;|&nbsp; [LinkedIn](https://linkedin.com/in/sakshimdesai) &nbsp;

---

## 🛠️ What I work with

**Languages:** Python · JavaScript · TypeScript · SQL  
**Backend:** Flask · Node.js · NestJS · REST APIs · GraphQL  
**Databases:** PostgreSQL · SQLite · Redis  
**AI/ML:** LLM Application Development · Prompt Engineering · Generative AI · scikit-learn  
**Tools:** Git · BullMQ · Postman · Render · Streamlit  

---

## 💼 Experience

**Software Engineering Intern — UnknwnAI Ltd (UK-based Startup, Remote)** *(Mar–May 2026)*  
Built an event-driven inventory synchronization system between an ERP and Shopify using NestJS, PostgreSQL, Redis, and BullMQ. Implemented queue-based processing with retry handling, checkpoint tracking, and event coalescing. Worked on the Dispatch integration using the Outbox Pattern, architected async fulfillment pipelines, and wrote technical documentation for onboarding and future development.  
*Stack: TypeScript · NestJS · PostgreSQL · Redis · BullMQ · Shopify GraphQL API*

---

## 🚀 Projects

### [Reflexion Code Agent](https://github.com/sakshimdesai/Reflexion-Code-Agent) — *Agentic AI · Python · Groq · Streamlit*
Most AI code tools give you code. You still have to run it, hit errors, paste them back, and repeat. This agent closes that loop entirely — it generates Python code, executes it via subprocess, captures runtime errors, feeds them back to the LLM, and retries until the code actually works. It's not a chatbot wrapper. It's a closed-loop generate → execute → reflect → fix system built on LLaMA 3.1 via Groq, with a Streamlit UI showing full iteration history and debug logs.

### [LinkGen AI](https://github.com/sakshimdesai/linkgen-ai) — *Generative AI · Python · Streamlit · Groq*
Not another LinkedIn post generator — this one lets you compare how LLaMA 3.1 8B vs 70B handle the exact same prompt side by side, and generates formal + casual tone variations in one click. The interesting part is the prompt engineering underneath: each tone has custom conditioning, not just keyword swaps. Supports English, Hindi, and Kannada. Built to show that model orchestration and prompt design produce meaningfully different outputs — not interchangeable ones.

### [Placement Hub](https://placement-hub-xpmr.onrender.com) — *Full-Stack · Flask · SQLite · HTML/JS*
The interesting architectural decision here: the backend serves heterogeneous content — DSA questions with Python + Java solutions, aptitude with single explanations, HR with text guidance — all from one Flask + SQLite backend with conditional rendering logic per category. The admin panel was completely removed before production (not hidden, removed) — a deliberate call to reduce attack surface and ship a stable, read-only system. 

### [Hormone Harmony](https://github.com/sakshimdesai/Hormone-Harmony) — *Full-Stack · Flask · SQLite · Chart.js*
Built for a gap that generic period trackers ignore: PCOS introduces irregular cycles, hormonal variability, and symptoms that don't fit the standard 28-day model. This platform focuses on symptom logging, pattern visualization over time, cycle phase education (with PCOS-specific context), a myth-busting module targeting Indian misconceptions, and a meal guidance section. Hard constraint: no cycle prediction, no medical diagnosis — ethics baked into the architecture, not bolted on.

### [GroupReceipt](https://github.com/sakshimdesai/group_receipt) — *Flutter · Dart · Firebase Firestore*
Built to solve a specific frustration: in group projects, self-reported hours are unverifiable and easily gamed. GroupReceipt makes it structurally impossible to mark a task done without pasting a real proof link — GitHub, Google Doc, Figma, Drive, anything with a URL. At the end, the app generates a shareable visual receipt with each member's contribution percentage and a verdict: Carried / Solid / Barely There / Ghost. No accounts, no friction — join by a 5-character code.

### Phishing URL & SMS Detection *(Final Year Project — In Progress)*
The research gap this addresses: tools like Google Safe Browsing are trained almost entirely on Western phishing data and systematically miss India-specific patterns — fake UPI pages mimicking PhonePe/GPay, IRCTC/DigiLocker impersonations, Hinglish urgency language, regional SMS scams in Kannada and Hindi. Building a Random Forest + XGBoost pipeline on the PhiUSIIL dataset (235K URLs), extended with manually collected Indian phishing samples. SHAP values explain per-prediction reasoning. The research contribution is the gap analysis itself: how Western-trained models fail on Indian phishing.

---

## 🏆 Hackathons

- **Walmart Global Tech Sparkathon 2025** — Proposed *Smart Cart*, a location-based grocery discovery system that matches users' dietary preferences to real-time store inventory
- **Varroc Eureka Challenge 3.0** *(results awaited)* — Team Synara proposed an AI-driven design intelligence system for early-stage CAD validation, enabling real-time automated design checks and deviation detection within CAD environments
- **Tata Elxsi TELIPORT Season 3 Ideathon 2026** — Proposed *SafetyGate GenAI*, an AI-assisted safety validation framework for software-defined vehicle workflows and engineering decision support
- **UNESCO Youth Hackathon 2025** — Prototyped *News Nutrition Label*, an NLP-based framework for analyzing news credibility, bias, and factual reliability

---

*Always building. Open to SWE / backend / AI roles.*
