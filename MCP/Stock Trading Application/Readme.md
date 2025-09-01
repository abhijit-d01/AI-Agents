# MCP-Based AI Agent for Stock Trading Analysis

This project implements an advanced agentic AI application for stock trading analysis using a Multi-Collaborator Persona (MCP) framework and the OpenAI Agent SDK. The system leverages multiple specialized AI agents that work together to provide comprehensive insights and analysis on specified stocks.

## Overview

Traditional stock analysis can be time-consuming and requires expertise across different domains. This application automates the process by simulating a team of financial experts with distinct roles. By providing a stock ticker, the user can initiate a collaborative workflow where different AI personas research, analyze, and synthesize information to produce a detailed report on whether to buy, hold, or sell the stock.

## Key Features

-   **Multi-Agent Collaboration:** Utilizes a team of AI agents with specialized personas (e.g., Researcher, Financial Analyst, Trader).
    
-   **Dynamic Tool Usage:** Agents can use various tools to fetch real-time stock data, company news, and financial statements.
    
-   **Stateful Conversations:** Maintains the context of the analysis across different agent interactions.
    
-   **Asynchronous Workflow:** Agents work in parallel and pass information to each other, mimicking a real-world team.
    
-   **Comprehensive Analysis:** Delivers a final report that includes quantitative data, qualitative insights, and a final recommendation.
    

## How It Works: The MCP Architecture

The application is built on the concept of Multi-Collaborator Personas (MCP), where each AI agent has a unique role and set of instructions. The workflow is orchestrated as follows:

1.  **User Input:** The user provides a stock ticker (e.g., AAPL, GOOGL).
    
2.  **Orchestrator Agent:** The main agent receives the request and defines a master plan. It delegates tasks to specialized agents.
    
3.  **Researcher Agent:** This agent is responsible for gathering raw data. It uses tools to fetch:
    
    -   Current stock price and historical data.
        
    -   Latest company news and press releases.
        
    -   Quarterly and annual financial reports.
        
4.  **Financial Analyst Agent:** This agent receives the data from the Researcher. Its primary role is to:
    
    -   Analyze the financial statements (Balance Sheet, Income Statement, Cash Flow).
        
    -   Calculate key financial ratios (P/E, Debt-to-Equity, etc.).
        
    -   Perform a qualitative analysis based on news and market sentiment.
        
5.  **Trader Agent:** This agent takes the structured analysis from the Financial Analyst and views it from a market perspective. It:
    
    -   Analyzes technical indicators and market trends.
        
    -   Considers the risk-reward profile.
        
    -   Formulates a final, actionable recommendation: **Buy**, **Hold**, or **Sell**.
        
6.  **Final Report:** The insights from all agents are compiled into a single, coherent report for the user.
    

## Technology Stack

-   **Language:** Python 3.x
    
-   **AI Framework:** OpenAI Agent SDK
    
-   **LLM:** OpenAI GPT-4 (or other compatible models)
    
-   **Data Sources:** Assumed to use a financial data API like Alpha Vantage, Yahoo Finance (yfinance), or similar.
    

## Setup and Installation

Follow these steps to set up and run the project locally.

### 1\. Prerequisites

-   Python 3.8 or higher
    
-   An OpenAI API Key
    
-   An API key for your chosen financial data provider (if applicable)
    

### 2\. Clone the Repository

```Bash
git clone [https://github.com/abhijit-d01/AI-Agents.git](https://github.com/abhijit-d01/AI-Agents.git)  
cd AI-Agents/MCP/Stock%20Trading%20Application`
```
### 3\. Create a Virtual Environment

It's highly recommended to use a virtual environment to manage dependencies.

```Bash
python -m venv venv  
source venv/bin/activate  # On Windows, use `venv\Scripts\activate` ``
```
### 4\. Install Dependencies

Install all the required Python packages from requirements.txt.

```Bash
pip install -r requirements.txt`
```
### 5\. Set Up Environment Variables

Create a .env file in the project's root directory and add your API keys.

```Bash
OPENAI_API_KEY="your-openai-api-key"  # Add any other required API keys, e.g.,  # ALPHA_VANTAGE_API_KEY="your-alpha-vantage-key"`
```
## Usage

Run the main application from the terminal. The script will prompt you to enter a stock ticker for analysis.

```Bash
python main.py
```
The application will then execute the agentic workflow and print the final analysis report to the console.

## Project Structure

Here is a brief overview of the key files in the project:

-   **main.py**: The entry point for the application. It handles user input and kicks off the agentic workflow.
    
-   **mcp\_agent.py**: Contains the core logic for the agent orchestration, including the definitions for the different agent personas and their collaborative process.
    
-   **prompts.py**: Stores the detailed system prompts and instructions for each AI agent persona (Researcher, Analyst, Trader).
    
-   **tools.py**: Defines the custom tools that the agents can use, such as functions to fetch stock data or news from external APIs.
    
-   **utils.py**: Includes helper functions and utility classes used across the project.
    
-   **requirements.txt**: A list of all Python dependencies required to run the project.
    

## Example

```Bash
$ python main.py  Enter the stock ticker you want to analyze (e.g., MSFT): AAPL  > Initializing MCP Agentic Workflow for AAPL...  > Orchestrator: Planning the analysis for Apple Inc.  > Researcher: Fetching stock data, news, and financials for AAPL.  > Financial Analyst: Analyzing data... P/E ratio is 28.5, recent news about Vision Pro is positive.  > Trader: Market sentiment is bullish. Strong support at $180.  > Generating Final Report...  -----------------------------------------  Stock Analysis Report: Apple Inc. (AAPL)  -----------------------------------------  ### Quantitative Analysis:  - Current Price: $190.45  - P/E Ratio: 28.5  - Market Cap: $2.98T  - Key Financials: Revenue growth is steady at 5% YoY...  ### Qualitative Analysis:  - Market Sentiment: Positive. Recent news about the new product launches and strong App Store performance has been well-received.  - Competitive Landscape: Apple maintains a strong position in the premium smartphone market...  ### Final Recommendation:  Based on the comprehensive analysis of financial health, market position, and positive sentiment, the recommendation is **BUY**.  -----------------------------------------`
```
## Disclaimer

This application is for educational and informational purposes only. It is not financial advice. The stock market is volatile, and you should always do your own research or consult with a qualified financial advisor before making any investment decisions.