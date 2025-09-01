LangGraph Powered AI Assistant
==============================

This project demonstrates a sophisticated, stateful AI Assistant built using LangGraph. The assistant is designed to handle complex, multi-turn conversations and execute tasks by leveraging a graph-based architecture. This allows for more robust and flexible agentic workflows compared to traditional linear agent chains.

Overview
--------

This AI Assistant is not just a simple chatbot. By leveraging LangGraph, it can maintain a persistent state, use a variety of tools, and make decisions on how to proceed in a cyclical manner. This enables it to perform actions like searching the web, calling APIs, and refining its answers based on new information or user feedback, making it a powerful and versatile tool.

Key Features
------------

*   **Graph-Based Logic:** The assistant's workflow is defined as a graph, allowing for complex loops, branches, and conditional transitions.
    
*   **State Management:** The conversation and intermediate results are managed in a central state object, ensuring context is never lost.
    
*   **Tool Integration:** Seamlessly integrates with LangChain tools to give the assistant real-world capabilities (e.g., web search, calculations).
    
*   **Cyclical Reasoning:** Unlike linear chains, the graph structure allows the assistant to loop back to previous steps, refine its approach, and correct its mistakes.
    
*   **Extensible by Design:** New tools, agents, and logic paths (nodes and edges) can be easily added to enhance the assistant's capabilities.
    

How It Works: The LangGraph Architecture
----------------------------------------

LangGraph models agent workflows as a state machine. The core components are:

1.  **State Object:** A central Python class that holds all the information relevant to the current task, such as conversation history, tool outputs, and intermediate steps. The graph's state is updated as it progresses.
    
2.  **Nodes:** These are the fundamental units of work in the graph. Each node is a Python function or a LangChain runnable (like an agent or a tool). A node receives the current state as input and returns an update to the state.
    
3.  **Edges:** These connect the nodes and determine the flow of logic.
    
    *   **Conditional Edges:** These are used to route the flow based on the current state. For example, after an agent acts, a conditional edge might check if a tool was called and route to a tool execution node, or route back to the user if the agent is ready to respond.
        
    *   **Entry/Finish Points:** The graph has a defined entry point and can have multiple finish points.
        

The workflow typically looks like this:

1.  The user's input is added to the state.
    
2.  The graph starts at the entry point, usually an "agent" node.
    
3.  The agent node decides whether to use a tool or respond directly to the user.
    
4.  A conditional edge directs the flow to either a "tool" node or the end of the graph.
    
5.  If a tool is used, its output is added to the state, and the flow loops back to the agent node for the next step.
    
6.  This cycle continues until the agent can provide a final answer.
    

Technology Stack
----------------

*   **Language:** Python 3.x
    
*   **Core Framework:** LangGraph, LangChain
    
*   **LLM:** OpenAI GPT-4 (or other LangChain-compatible models)
    
*   **Tools:** Can be configured with any LangChain tools (e.g., Tavily Search for web access).
    

Setup and Installation
----------------------

Follow these steps to set up and run the project locally.

### 1\. Prerequisites

*   Python 3.8 or higher
    
*   An OpenAI API Key
    
*   API keys for any tools you wish to use (e.g., Tavily AI API Key for search).
    

### 2\. Clone the Repository

Plain textANTLR4BashCC#CSSCoffeeScriptCMakeDartDjangoDockerEJSErlangGitGoGraphQLGroovyHTMLJavaJavaScriptJSONJSXKotlinLaTeXLessLuaMakefileMarkdownMATLABMarkupObjective-CPerlPHPPowerShell.propertiesProtocol BuffersPythonRRubySass (Sass)Sass (Scss)SchemeSQLShellSwiftSVGTSXTypeScriptWebAssemblyYAMLXML`   git clone [https://github.com/abhijit-d01/AI-Agents.git](https://github.com/abhijit-d01/AI-Agents.git)  cd AI-Agents/LangGraph/AI Assistant   `

### 3\. Create a Virtual Environment

Plain textANTLR4BashCC#CSSCoffeeScriptCMakeDartDjangoDockerEJSErlangGitGoGraphQLGroovyHTMLJavaJavaScriptJSONJSXKotlinLaTeXLessLuaMakefileMarkdownMATLABMarkupObjective-CPerlPHPPowerShell.propertiesProtocol BuffersPythonRRubySass (Sass)Sass (Scss)SchemeSQLShellSwiftSVGTSXTypeScriptWebAssemblyYAMLXML``   python -m venv venv  source venv/bin/activate  # On Windows, use `venv\Scripts\activate`   ``

### 4\. Install Dependencies

Plain textANTLR4BashCC#CSSCoffeeScriptCMakeDartDjangoDockerEJSErlangGitGoGraphQLGroovyHTMLJavaJavaScriptJSONJSXKotlinLaTeXLessLuaMakefileMarkdownMATLABMarkupObjective-CPerlPHPPowerShell.propertiesProtocol BuffersPythonRRubySass (Sass)Sass (Scss)SchemeSQLShellSwiftSVGTSXTypeScriptWebAssemblyYAMLXML`   pip install -r requirements.txt   `

### 5\. Set Up Environment Variables

Create a .env file in the project's root directory and add your API keys.

Plain textANTLR4BashCC#CSSCoffeeScriptCMakeDartDjangoDockerEJSErlangGitGoGraphQLGroovyHTMLJavaJavaScriptJSONJSXKotlinLaTeXLessLuaMakefileMarkdownMATLABMarkupObjective-CPerlPHPPowerShell.propertiesProtocol BuffersPythonRRubySass (Sass)Sass (Scss)SchemeSQLShellSwiftSVGTSXTypeScriptWebAssemblyYAMLXML`   OPENAI_API_KEY="your-openai-api-key"  # Example for Tavily Search API  # TAVILY_API_KEY="your-tavily-api-key"   `

Usage
-----

Run the main application from the terminal. This will launch an interactive chat session where you can converse with the AI assistant.

Plain textANTLR4BashCC#CSSCoffeeScriptCMakeDartDjangoDockerEJSErlangGitGoGraphQLGroovyHTMLJavaJavaScriptJSONJSXKotlinLaTeXLessLuaMakefileMarkdownMATLABMarkupObjective-CPerlPHPPowerShell.propertiesProtocol BuffersPythonRRubySass (Sass)Sass (Scss)SchemeSQLShellSwiftSVGTSXTypeScriptWebAssemblyYAMLXML`   python main.py   `

Type your queries into the console and press Enter. To exit the application, type exit.

Project Structure
-----------------

*   **main.py**: The entry point for the application. It handles the command-line interface and the main conversation loop.
    
*   **graph.py**: Defines the LangGraph workflow, including the state object, nodes, and edges that constitute the AI assistant's logic.
    
*   **tools.py**: Contains the definitions for the custom tools that the assistant can use.
    
*   **requirements.txt**: A list of all Python dependencies.
    

Example
-------

Plain textANTLR4BashCC#CSSCoffeeScriptCMakeDartDjangoDockerEJSErlangGitGoGraphQLGroovyHTMLJavaJavaScriptJSONJSXKotlinLaTeXLessLuaMakefileMarkdownMATLABMarkupObjective-CPerlPHPPowerShell.propertiesProtocol BuffersPythonRRubySass (Sass)Sass (Scss)SchemeSQLShellSwiftSVGTSXTypeScriptWebAssemblyYAMLXML`   $ python main.py  > Starting AI Assistant... Type 'exit' to quit.  You: What was the score of the latest world cup final and who scored the goals?  > Assistant is thinking... (Calling Agent -> Using Tool: tavily_search_results_json)  Assistant: The final of the 2022 FIFA World Cup between Argentina and France ended in a 3-3 draw after extra time. Argentina won the subsequent penalty shootout 4-2.  The goal scorers were:  - **Argentina:** Lionel Messi (2 goals), Ángel Di María (1 goal).  - **France:** Kylian Mbappé (3 goals - a hat-trick).   `