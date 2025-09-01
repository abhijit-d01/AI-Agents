# AI Assistant with the OpenAI Agent SDK

This project is a foundational implementation of a stateful AI assistant using the official OpenAI Agent SDK (Assistants API v2). It demonstrates how to create a persistent assistant, manage conversations in threads, and equip the assistant with tools like Code Interpreter and custom functions to solve user-defined tasks.

## Overview

The OpenAI Assistants API provides a powerful framework for building complex AI applications. This project serves as a clear, practical example of its core concepts. Instead of managing conversation history manually, this assistant uses `Threads` to maintain context, allowing for more natural and extended interactions. The assistant can be instructed to use tools to access external information or perform specific actions, making it highly capable and extensible.

## Key Features

-   **Persistent Assistants:** An assistant is created once with specific instructions and tools and can be reused across many conversations.
    
-   **Stateful Threads:** Each user conversation is managed in a separate `Thread`, which automatically handles the message history.
    
-   **Tool Usage:** Demonstrates how to enable built-in tools like Code Interpreter and how to define custom Python functions for the assistant to call.
    
-   **Asynchronous Workflow:** The assistant processes messages in a `Run`, which operates asynchronously, allowing for non-blocking execution.
    
-   **File Handling:** Shows how the assistant can access files provided by the user for analysis (e.g., analyzing a CSV file with Code Interpreter).
    

## How It Works: The Assistants API Flow

The application follows the standard lifecycle for an interaction with the Assistants API:

1.  **Create an Assistant:** An `Assistant` object is created with a specific model, system instructions (persona), and a set of enabled tools (e.g., Code Interpreter, custom functions).
    
2.  **Create a Thread:** When a new conversation begins, a `Thread` is created to represent it.
    
3.  **Add a Message:** The user's query is added as a `Message` to the thread.
    
4.  **Create a Run:** To get a response, we `Run` the `Assistant` on the `Thread`. This initiates the process where the assistant reads the thread and decides how to respond.
    
5.  **Poll the Run Status:** A `Run` can have several statuses (`queued`, `in_progress`, `completed`, `failed`, `requires_action`). The application polls the status until it is no longer `in_progress`.
    
6.  **Handle Tool Calls:** If the status is `requires_action`, it means the assistant wants to call one of its tools. The application executes the specified function(s) with the arguments provided by the assistant and submits the results back to the `Run`.
    
7.  **Retrieve the Response:** Once the `Run` status is `completed`, the application retrieves the latest messages from the thread. The new messages added by the assistant contain the final response.
    

## Technology Stack

-   **Language:** Python 3.x
    
-   **AI Framework:** OpenAI Python SDK (`openai>=1. Assistants API v2`)
    
-   **LLM:** OpenAI GPT-4 (or other compatible models)
    

## Setup and Installation 

Follow these steps to set up and run the project locally.

### 1\. Prerequisites


-   Python 3.8 or higher
    
-   An OpenAI API Key
    

### 2\. Clone the Repository

    git clone [https://github.com/abhijit-d01/AI-Agents.git](https://github.com/abhijit-d01/AI-Agents.git)
    cd AI-Agents/OpenAI%20Agent%20SDK
    

### 3\. Create a Virtual Environment

It's highly recommended to use a virtual environment to manage dependencies.

    python -m venv venv
    source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
    

### 4\. Install Dependencies

Install all the required Python packages from `requirements.txt`.

    pip install -r requirements.txt
    

### 5\. Set Up Environment Variables

Create a `.env` file in the project's root directory and add your API key.

    OPENAI_API_KEY="your-openai-api-key"
    

## Usage

Run the main application from the terminal. This will start an interactive chat session with the assistant.

    python main.py
    

You can now type your questions or requests. The assistant will use its tools as needed to provide an answer.

## Project Structure

-   **`main.py`**: The entry point for the application. It handles the interactive chat loop and user input.
    
-   **`assistant_manager.py`**: Contains the core logic for creating, running, and interacting with the Assistant and Threads.
    
-   **`tools.py`**: Defines the custom Python functions that are made available to the assistant as tools.
    
-   **`requirements.txt`**: A list of all Python dependencies required to run the project.
    

## Example

    $ python main.py
    > Starting AI Assistant... Type 'exit' to quit.
    You: What is the current stock price of NVIDIA (NVDA)?
    
    > Assistant is processing...
    > Status: requires_action
    > Calling tool: get_stock_price with arguments {'ticker': 'NVDA'}
    > Submitting tool output...
    > Status: in_progress
    > Status: completed
    
    Assistant: The current stock price for NVIDIA (NVDA) is $131.84.
    

## Disclaimer

This application may use third-party APIs for its tools. Ensure you understand and comply with the terms of service of any data provider you integrate. Stock prices provided are for informational purposes only and do not constitute financial advice.