# Multi-Agent AI Research Assistant

This project implements a multi-agent system using the `crewai` framework to automate the process of finding, analyzing, and reporting on recent AI research papers from ArXiv.

## Overview

The system leverages a team of two specialized AI agents powered by Google's Gemini Pro model:

1. **Researcher Agent**: Connects to the ArXiv academic database to search for papers based on a specific date and identifies the top 10 most relevant publications.
2. **Frontend Engineer Agent**: Takes the research findings and compiles them into a polished, well-formatted HTML report.

The entire workflow is orchestrated within a Jupyter Notebook (`researchAgent.ipynb`), which provides a clear, step-by-step guide to the process.

## Features

- **Automated Research**: Automatically fetches and ranks the latest AI papers from ArXiv.
- **Dynamic Reporting**: Generates a clean HTML report (`ai_research_report.html`) summarizing the findings.
- **Multi-Agent System**: Utilizes `crewai` to manage a sequential workflow between specialized agents.
- **Custom Tools**: Includes a custom `FetchArxivPapersTool` to extend agent capabilities for interacting with the ArXiv API.
- **Secure Configuration**: Manages API keys and sensitive information using a `.env` file.

## Technologies Used

- **Framework**: `crewai`
- **LLM**: Deepseek V3 (deepseek-chat-v3-0324:free)

## Setup and Installation

1. **Clone the repository:**

   ```bash
   git clone <your-repo-url>
   cd ResearchAgent
   ```
2. **Create a virtual environment and activate it:**

   ```bash
   conda create -n <Your Env Name> python=3.10 -y
   conda activate <Your Env Name>
   ```
3. **Install the required dependencies:**

   ```bash
   pip install -r requirements.txt
   ```
4. **Configure Environment Variables:**

   - Create a file named `.env` in the root directory by copying the example file:
     ```bash
     cp .env.example .env
     ```
   - Open the `.env` file and add your API keys. You primarily need the `GOOGLE_API_KEY` for this project to run.
     ```
     SERPER_API_KEY="your_serper_api_key_here" # Optional, for web search tool
     GOOGLE_API_KEY="your_google_api_key_here"
     OPENROUTER_API_KEY="your_openrouter_api_key_here" # Optional
     ```

## How to Run

1. **Launch Jupyter Notebook:**

   ```bash
   jupyter notebook
   ```
2. **Open the notebook:**

   - In the Jupyter interface, open `researchAgent.ipynb`.
3. **Run the cells:**

   - Execute the cells in order from top to bottom.
   - The final cell, which calls `arxiv_research_crew.kickoff()`, will start the agent workflow.

## Output

Upon successful execution, the script will generate a file named `ai_research_report.html` in the root directory. This file contains the formatted list of the top 10 AI research papers for the specified date.
