# Open SWE — Open-Source AI Software Engineer

Open SWE is an open-source AI coding agent built using **LangChain**, designed to automate software engineering workflows similar to proprietary agents like Devin.  
It can plan, code, debug, and push changes — directly through GitHub or via a web interface.

---

## 1. Concepts to Understand Before Using Open SWE

Before setting up or running Open SWE, it’s important to understand the following theoretical concepts:

### a. Large Language Models (LLMs)
- LLMs like GPT, Claude, or Mixtral are core components of Open SWE.
- They generate code, explanations, and plans based on user prompts.
- Open SWE supports both open-weight (like Mistral, LLaMA) and API-based (like OpenAI or Anthropic) models.

### b. LangChain
- LangChain is a framework for building AI agents that can reason, plan, and take actions.
- It connects LLMs with tools like file systems, APIs, and databases.
- In Open SWE, LangChain powers the Planner and Programmer agents.

### c. Agent Architecture
- Open SWE uses a multi-agent system:
  - **Planner Agent:** Analyzes issues or goals and breaks them into actionable tasks.
  - **Programmer Agent:** Executes these tasks by writing or editing code.
- The agents communicate using structured reasoning steps and maintain context through memory.

### d. GitHub Integration
- Open SWE is designed to work with GitHub repositories.
- When an issue or pull request is labeled (e.g., `open-swe-auto`), the agent automatically starts processing it.
- It can:
  - Read repository code.
  - Plan a solution.
  - Generate commits.
  - Open or update pull requests.

### e. Workflow Automation
- Open SWE automates software development workflows end-to-end:
  - Issue analysis.
  - Planning and execution.
  - Code writing and debugging.
  - Version control actions (commits, PRs).
- Each step is logged and traceable in the web interface.

### f. Vector Databases and Embeddings (Optional)
- Open SWE can use vector databases to store and retrieve contextual information efficiently.
- Embeddings convert text/code into numerical vectors that capture semantic meaning, allowing better long-term context handling.

### g. Docker and Containerization
- Open SWE uses Docker to ensure consistent environments for agents.
- Each agent runs inside a containerized workspace to avoid dependency conflicts.

### h. Environment Variables and API Keys
- You’ll need API keys for the LLMs you choose (like OpenAI or Anthropic).
- Proper environment configuration is required for GitHub access and LLM connectivity.

### i. Frontend Interface
- The web UI provides:
  - Control over running agent sessions.
  - Logs and intermediate reasoning steps.
  - A visual workflow manager to observe the planning and coding process.

---

## 2. Core Features

- Fully open-source autonomous software engineer.
- GitHub integration for auto issue/PR handling.
- Modular agent-based design (Planner and Programmer).
- LangChain-powered reasoning and execution.
- Optional vector memory for long-term context.
- Web dashboard for management and monitoring.

---

## 3. How to Set Up Open SWE

### Step 1: Clone the Repository
```bash
git clone https://github.com/ynixon/open-swe.git
cd open-swe
```
### Step 2: Install Dependencies
```bash
pip install -r requirements.txt
```
### Step 3: Configure Environment Variables
```bash
OPENAI_API_KEY=your_openai_key
GITHUB_TOKEN=your_github_token
```
### Step 4: Run the Backend
```bash
python main.py
```
### Step 5: Run the Web Interface
```bash
cd frontend
npm install
npm run dev
```

## 4. GitHub Integration Flow

- Create or label an issue with a supported label (e.g., open-swe-auto).
- The Open SWE backend detects the label and triggers the Planner agent.
- The Planner generates a high-level plan and hands it to the Programmer.
- The Programmer writes or edits code in the repository.
- Commits are pushed automatically, and a pull request is created or updated.


## 5. Tech Stack Overview

- Backend: Python, LangChain, FastAPI
- Frontend: React, Next.js
- Database (optional): PostgreSQL or MongoDB for logs and vector data
- LLM Providers: OpenAI, Anthropic, Mistral, or other supported models
- Infrastructure: Docker, GitHub Actions

## Thats's it for now as I'll add more things as I proceed!!