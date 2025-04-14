A ground-up rebuild of the Composer AI platform using Llama Stack vLLM MCP OpenShift AI , , , , and GitOps , delivering an extensible, production-ready AI innovation platform.

## 🧠 Composer AI v3 - MVP Outline Project Scope:

## TECHNICAL REQUIREMENTS

## 🔧 1. Architecture &amp; Deployment

- ● Cluster: Rebuild ROSA (OpenShift) cluster
- ● Helm Charts: Separate stateful and stateless services (e.g., SQLite decoupling)
- ● GitOps: Leverage ArgoCD for version-controlled, declarative deployments
- ● CI/CD: Integrate GitHub Actions (or Tekton) for image builds and testing

## 2. Llama Stack

- ● Install base Llama Stack
- ● Extend with:
- ○ Agent list endpoint
- ○ Agent session management (creation, delete - read/update TBD)
- ○ MCP API support
- ● vLLM Inference: Granite, LLaMA, Embedding models
- ● Provider Support:
- ○ External OpenAI/Gemini
- ○ Models as a Service (non-prod)  Guillaume Moutier
- ○ Models.corp (prod)  Tom Benninger

## 3. Data Separation

- ● Move from local SQLite to PostgreSQL

## 4. RAG &amp; Vector DB

- ● Develop new Ingestion Pipeline
- ● Vector Store : PGVector (built-in to llama stack) then implement ElasticSearch
- ● GraphRAG (FUTURE) potential for advanced use cases

## FUNCTIONAL REQUIREMENTS

- ● UI Framework: Switch to PatternFly (test Claude compatibility)
- ● Frontend: Containerized, configurable (env + config.js)
- ● Functional Modules:
- ○ Models (CRUD)
- ○ Agents (CRUD)
- ○ Tools (CRUD)
- ○ RAG (CRUD)
- ○ MCP Connections (CRUD)
- ○ Evals (CRUD)

## Chat Interfaces

- ● Basic Chat w/ Model
- ○ Show time to first token, TPS, cost, total tokens
- ● Standalone &amp; Comparison Chatbots
- ○ Toggle RAG, compare up to 4 agents

## INFRASTRUCTURE REQUIREMENTS

## ⚙ Software

- ● OpenShift &gt;= 4.18
- ● OpenShift AI
- ● Python (RAG/data pipeline)
- ● Node/TypeScript or PatternFly frontend
- ● MCP Server examples (Miro, Trello, Jira, Kubernetes)

## STAGED DELIVERY PLAN

- ● Deploy Llama Stack locally

## 🚧 🏗 Phase 1: MVP - Agent Enablement (Week 1-2)

- ● Port over IT Productivity agents
- ● Enable agent list, create/delete
- ● Set up the UI for agent chat
- ● Run PatternFly UI tests (Claude compatibility)

## 📦 Phase 2: Platform Infrastructure (Week 2-4)

- ● Helm chart refactor (split DB)
- ● Deploy to OpenShift ROSA
- ● GitOps pipelines configured
- ● UI containerized and deployed
- ● Frontend switch to PatternFly (if feasible)

## 📚 Phase 3: RAG &amp; Data Pipeline (Week 4-6)

- ● Select and deploy Vector DB
- ● Rebuild ingestion pipeline (Trevor lead)
- ● Enable RAG CRUD in UI
- ● Start initial GraphRAG integration (optional)

## 🤝 Phase 4: MCP Integration (Week 5-7)

- ● Add MCP registration APIs
- ● Build UI to register/view/activate MCP servers
- ● MVP use case: Trello or Jira issue creation

## 🔬 Phase 5: Evals &amp; Comparison (Week 6-8)

- ● Add evaluation support (manual/test scripts)
- ● Standalone vs Comparison chatbot features
- ● Add agent metrics visualization

## 🔍 MILESTONES

| Milestone                          | Target Date   | Owner(s)     | PM    |
|------------------------------------|---------------|--------------|-------|
| Llama Stack Local MVP              | Week 1        | Peter + Mike | Evert |
| UI Agent Chat                      | Week 3        | Peter + Mike | Evert |
| ROSA Cluster Rebuild + Helm Charts | Week 4        | Jamie        | Tim   |
| RAG Ingestion Working              | Week 6        | Trevor       | Brent |
| MCP Server Integration             | Week 8        | TBD          | TBD   |
| Full Demo Environment              | Week 8        | Whole Team   | TBD   |