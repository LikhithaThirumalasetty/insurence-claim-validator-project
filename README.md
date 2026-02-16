Insurance Claim Validator
Agentic AI-Powered Multi-Agent Decision System

An end-to-end Agentic AI workflow that automates insurance claim validation using LLM-driven agents + deterministic risk logic + orchestration graph architecture.

Built with LangGraph, LangChain, Gemini (Google Generative AI), and Streamlit.

🚀 Why This Project Matters

Insurance claim processing is traditionally:

Manual

Time-consuming

Error-prone

Difficult to scale

This project demonstrates how Agentic AI systems can automate structured decision workflows with:

Multi-agent coordination

Supervisor-controlled execution

Hybrid AI + rule-based scoring

Explainable decision outputs

This is not just an LLM wrapper — it is a state-driven AI orchestration system.

🧠 Architecture Overview

Built using LangGraph, the system follows a Supervisor → Specialized Agents → Decision Pipeline architecture.

🔷 Core Design Pattern

State-based workflow using a TypedDict state schema:

class ClaimState(TypedDict):
    claim_data: Dict[str, Any]
    extracted_data: Dict[str, Any]
    policy_validation: Dict[str, Any]
    fraud_analysis: Dict[str, Any]
    risk_score: int
    final_decision: Dict[str, Any]
    next_step: str


The Supervisor Agent dynamically routes execution until completion.

🤖 Agent Responsibilities
1️⃣ Document Processing Agent

Extracts structured JSON from claim input using Gemini

Ensures machine-readable format for downstream agents

2️⃣ Policy Validation Agent

Validates policy authenticity

Returns structured decision:

{
  "is_valid": true/false,
  "reason": "text"
}

3️⃣ Fraud Detection Agent

Classifies fraud risk (Low / Medium / High)

AI-based reasoning layer

4️⃣ Risk Assessment Agent (Deterministic Logic)

Hybrid approach:

+50 → High fraud

+25 → Medium fraud

+30 → Claim amount > 50,000

5️⃣ Decision Agent

Final outcome:

❌ REJECTED → Invalid policy

🟡 MANUAL_REVIEW → Risk score > 60

✅ APPROVED → Otherwise

🛠️ Tech Stack

🐍 Python

🧠 LangChain

🔁 LangGraph

🤖 Google Gemini (gemini-2.5-flash)

🎨 Streamlit

JSON Structured Outputs

🔄 Execution Flow
User Input
   ↓
Supervisor Agent
   ↓
Document Processor
   ↓
Policy Validator
   ↓
Fraud Detector
   ↓
Risk Assessor
   ↓
Decision Agent
   ↓
Final Structured Output


Graph-based orchestration ensures modularity and extensibility.

📊 Sample Output
Verdict: MANUAL_REVIEW
Reason: High risk score
Risk Score: 80

💼 What This Demonstrates (Recruiter View)

✔️ Agentic AI system design
✔️ Multi-agent orchestration
✔️ State management with TypedDict
✔️ Hybrid AI + rule-based architecture
✔️ LLM structured JSON extraction
✔️ Explainable AI decision-making
✔️ Production-ready UI integration

🎯 Engineering Highlights

Zero hardcoded workflow sequence — dynamic routing via supervisor

Deterministic scoring combined with probabilistic LLM reasoning

Safe JSON extraction from model output

Modular architecture (each agent independently extensible)

UI + AI + orchestration integrated end-to-end
📂 How to Run
git clone https://github.com/LikhithaThirumalsetty/insurance-claim-validator.git 
cd insurance-claim-validator 
pip install -r requirements.txt 
streamlit run app.py

Then enter your Gemini API key inside the UI.

🔮 Future Improvements

Replace rule-based fraud scoring with ML model

Add database persistence

Add audit logs for compliance

Deploy via Docker

Add REST API layer

Add Human-in-the-loop override system

📌 Ideal Roles This Project Aligns With
AI Engineer
LLM Engineer
Applied ML Engineer
GenAI Developer
AI Automation Engineer
🧑‍💻 Author
T.Likhitha
AI/ML Enthusiast | Agentic AI Builder
