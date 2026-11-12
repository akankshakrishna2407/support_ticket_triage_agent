# Support Ticket Triage Agent

An AI-powered customer support ticket triage system built using **LangGraph, LangChain, GPT-OSS-20B, and SQLite**.

## LLM Used

**Provider:** Groq  
**Model:** "openai/gpt-oss-20b"

The project uses the GPT-OSS-20B open-weight language model through the Groq API for ticket classification, urgency detection, response generation, and response review.

## Project Overview

This project automates customer support ticket processing using an agentic workflow. It classifies incoming support tickets, detects urgency, routes them to appropriate handlers, generates responses, and reviews them before sending.

## Features

1. **Ticket Classification:** Classifies tickets into Billing, Technical, and General categories.
2. **Urgency Detection:** Identifies ticket urgency as Low, Medium, or High.
3. **Conditional Routing:** Routes tickets to the appropriate handler based on their category.
4. **Mock Billing Lookup:** Retrieves order details using the order ID from mock order data.
5. **AI-Powered Response Generation:** Generates customer support replies.
6. **Response Review:** Reviews generated replies and provides feedback with a retry mechanism (maximum 3 attempts).
7. **Human Approval:** Pauses billing-related responses for human approval before sending.
8. **Workflow Persistence:** Uses SQLite checkpointing to maintain workflow state.
9. **Conversation Management:** Maintains conversation state using LangGraph threads.

## Tech Stack

- Python
- LangGraph
- LangChain
- OpenAI GPT-OSS-20B
- SQLite
- Jupyter Notebook

## LLM Used

**Model:** `openai/gpt-oss-20b`

**Model Family:** GPT-OSS

The project uses the GPT-OSS-20B open-weight language model for AI-powered ticket classification, urgency detection, response generation, and response review.

## How to Run

### 1. Clone the Repository

```bash
git clone YOUR_GITHUB_REPOSITORY_URL
```

### 2. Navigate to the Project Folder

```bash
cd support_ticket_triage_agent
```

### 3. Create and Activate a Virtual Environment

```bash
python -m venv venv
```

For Windows:

```bash
venv\Scripts\activate
```

### 4. Install Dependencies

```bash
pip install -r requirements.txt
```

### 5. Configure Environment Variables

Create a `.env` file in the project folder and add the API key required by your model hosting provider.

```env
YOUR_PROVIDER_API_KEY=YOUR_API_KEY
```

Keep your API key private. Never upload your `.env` file to GitHub.

### 6. Run the Project

Open `project.ipynb` in Jupyter Notebook or VS Code and execute all cells in order.

## One Thing I Found Tricky

One of the most challenging parts was implementing conditional routing and the response review mechanism in LangGraph.

I had to manage different execution paths depending on ticket categories, handle rejected responses through a retry mechanism, and implement human approval for billing tickets. Managing state across multiple nodes and maintaining workflow persistence using SQLite also required careful implementation.

## Project Deliverables

- Python notebook containing the compiled LangGraph workflow.
- Rendered workflow graph (`graph.png`).
- README with project details and run instructions.
- Test outputs for Billing, Technical, and General support tickets.
