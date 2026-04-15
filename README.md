COPILOT MASTER INSTRUCTION — CBE BERASEI BI
As software architect and full-stack AI engineer.

Your task is to design and implement the system called:

"CBE Berasei BI — AI-Driven Decision Intelligence Platform with Human-in-the-Loop"

This system replaces traditional BI dashboards with an AI-first decision system.

---

# 🎯 GOAL

Build a production-ready platform that:

1. Ingests and processes telecom/customer data
2. Runs machine learning models (churn, fraud, segmentation)
3. Uses an LLM to generate business recommendations
4. Sends recommendations to a Human-in-the-Loop review system
5. Allows humans to approve, modify, or reject decisions
6. Executes approved actions via external systems (SMS/CRM/API)
7. Stores all decisions for audit and model feedback

---

# 🏗️ SYSTEM ARCHITECTURE

Implement the system using this architecture:

Data Sources  
→ ETL Layer  
→ Data Warehouse (MySQL/PostgreSQL)  
→ ML Model Layer  
→ LLM Recommendation Engine  
→ FastAPI Decision API  
→ HITL Web Application (Custom Dashboard)  
→ Execution Layer (SMS/CRM/External APIs)  
→ Feedback Loop (Logging + Retraining)

---

# 🧠 CORE MODULES TO BUILD

## 1. Data Layer
- Customer data ingestion
- Telecom usage data (IMSI, MSISDN, behavior)
- Data cleaning and transformation pipelines

---

## 2. Machine Learning Layer
Implement models for:
- Churn prediction (classification model)
- Fraud detection
- Customer segmentation (clustering)

Output must include:
- probability score
- model explanation

---

## 3. LLM Recommendation Engine
Use an LLM to:
- Convert ML outputs into business actions
- Generate:
  - recommendation text
  - reason explanation
  - suggested action

Example:
Input:
- churn_score = 0.87

Output:
- "High-risk customer"
- "Offer 10% discount within 24 hours"
- "Send via SMS campaign"

---

## 4. API Layer (FastAPI)
Build REST APIs:

- GET /customers/{id}
- GET /risk-score/{id}
- GET /recommendation/{id}
- POST /decision
- GET /logs

All APIs must be production structured, clean, and modular.

---

## 5. HITL (Human-in-the-Loop) Web App
Build a custom dashboard (NOT Power BI or Tableau).

Frontend must include:

- Decision Queue
- Customer 360 View
- Recommendation Panel
- Action buttons:
  - Approve
  - Reject
  - Modify

Each decision must be recorded.

---

## 6. Execution Layer
Implement connectors for:
- SMS gateway (mock if needed)
- CRM system (mock API allowed)
- Notification service

Only execute actions AFTER human approval.

---

## 7. Feedback System
Store:
- user decisions
- modifications
- rejected recommendations
- final outcomes

This will be used for:
- model improvement
- LLM prompt tuning

---

# 🧪 NON-FUNCTIONAL REQUIREMENTS

- Scalable architecture (handle large datasets)
- Fast API response (<2 seconds)
- Secure RBAC (role-based access control)
- Full audit logging
- Modular and production-grade code structure

---

# 🧑‍💻 TECHNOLOGY STACK

Backend:
- Python
- FastAPI

ML:
- scikit-learn / TensorFlow

LLM:
- OpenAI API OR Qwen model

Database:
- MySQL or PostgreSQL

Frontend:
- React (preferred) OR simple web UI

DevOps:
- Docker
- CI/CD ready structure

---

# 📦 CODE ORGANIZATION (MANDATORY)

Structure code like:

/backend
  /api
  /models
  /services
  /llm
  /ml
  /db
  main.py

/frontend
  /components
  /pages
  /services

/infra
  docker-compose.yml

---

# ⚙️ DEVELOPMENT RULES

- Write clean, production-level code
- Use modular design
- Separate ML, API, and LLM logic
- Ensure all outputs are traceable
- Every AI recommendation must be logged
- Human approval is mandatory before execution

---

# 🚀 FINAL OUTPUT EXPECTATION

The system must behave as:

Data → ML Prediction → LLM Recommendation → Human Approval → Action Execution → Feedback Loop

---

# 🔥 IMPORTANT

Do NOT build a BI dashboard.

Instead, build a:
"Decision Intelligence System with Human-in-the-Loop automation."

---

Start by generating:
1. System folder structure
2. FastAPI backend skeleton
3. ML model template
4. LLM service module
5. HITL frontend UI structure

# PROJECT STRUCTURE
CBE-berasei-BI/
│
├── backend/
│   ├── app/
│   │   ├── api/
│   │   │   ├── customers.py
│   │   │   ├── recommendations.py
│   │   │   ├── decisions.py
│   │   │   ├── logs.py
│   │   │
│   │   ├── core/
│   │   │   ├── config.py
│   │   │   ├── security.py
│   │   │
│   │   ├── db/
│   │   │   ├── database.py
│   │   │   ├── models.py
│   │   │
│   │   ├── ml/
│   │   │   ├── churn_model.py
│   │   │   ├── fraud_model.py
│   │   │
│   │   ├── llm/
│   │   │   ├── engine.py
│   │   │
│   │   ├── services/
│   │   │   ├── decision_engine.py
│   │   │   ├── execution_service.py
│   │   │
│   │   └── main.py
│
├── frontend/
│   ├── src/
│   │   ├── pages/
│   │   │   ├── Dashboard.jsx
│   │   │   ├── Customer360.jsx
│   │   │   ├── ReviewQueue.jsx
│   │   │
│   │   ├── components/
│   │   │   ├── DecisionCard.jsx
│   │   │   ├── ActionPanel.jsx
│   │   │
│   │   └── App.js
│
├── infra/
│   ├── docker-compose.yml
│   ├── Dockerfile
│
└── README.md