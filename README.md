# Support Ticket Triage Agent

An AI-powered customer support ticket triage system built using LangGraph, LangChain, Google Gemini, and SQLite.

## Project Overview

This project automates customer support ticket processing using an agentic workflow. It classifies tickets, detects urgency, routes them to appropriate handlers, generates responses, and reviews them before sending.

## Features

1 Ticket classification: Billing, Technical, and General.
2 Urgency detection.
3 Conditional routing to appropriate handlers.
4 Mock billing lookup using order ID.
5 LLM-based response generation.
6 Response review with feedback and retry mechanism (maximum 3 attempts).
7 Human approval for billing-related responses.
8 SQLite-based workflow checkpoint persistence.

## Tech Stack

- Python
- LangGraph
- LangChain
- Google Gemini
- SQLite
- Jupyter Notebook

## LLM Used

Google Gemini

**Model:** gemini-3.5-flash



## How to Run

1. Clone this repository:

```bash
git clone YOUR_GITHUB_REPOSITORY_URL
```

2. Navigate to the project folder:

```bash
cd support_ticket_triage_agent
```

3. Create and activate a virtual environment:

```bash
python -m venv venv
venv\Scripts\activate
```

4. Install dependencies:

```bash
pip install -r requirement.txt
```

5. Create a `.env` file and add your Gemini API key:

GOOGLE_API_KEY=API_KEY


6. Open `project.ipynb` in Jupyter Notebook or VS Code and execute the cells in order.

## One Challenging Part

One of the challenging parts was implementing conditional routing and the response review mechanism in LangGraph.

I had to manage different execution paths depending on ticket categories, handle rejected responses through a retry mechanism, and implement human approval for billing tickets. Managing state across these nodes and maintaining workflow persistence using SQLite also required careful implementation.


