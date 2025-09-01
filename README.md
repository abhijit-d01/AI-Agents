# A Collection of Agentic AI Framework Implementations

Welcome to the AI Agents repository! This collection serves as a practical, hands-on guide to building applications with various leading agentic AI frameworks. Each sub-directory contains a self-contained project demonstrating the core concepts and capabilities of a specific framework.

Whether you're exploring multi-agent collaboration with AutoGen, building stateful assistants with the OpenAI SDK, or designing complex workflows with LangGraph, you'll find a working example here to get you started.

## Projects in this Repository

Below is a summary of the agentic frameworks and the example applications included in this repository.

| Framework | Project Example | Description |
| --- | --- | --- |
| [**OpenAI Agent SDK**](https://www.google.com/search?q=./OpenAI%2520Agent%2520SDK "null") | AI Assistant | A stateful assistant that uses tools and maintains conversation history using Threads. Demonstrates the core Assistants API v2 workflow. |
| [**AutoGen**](https://www.google.com/search?q=./AutoGen "null") | Multi-Agent Group Chat | A collaborative system where Coder, Critic, and Executor agents work together to write, review, and run code to solve a given task. |
| [**LangGraph**](https://www.google.com/search?q=./LangGraph/AI%2520Assistant "null") | AI Assistant | A sophisticated, stateful assistant built with a graph-based architecture, allowing for cyclical and more flexible agentic workflows. |
| [**MCP**](https://www.google.com/search?q=./MCP/Stock%2520Trading%2520Application "null") | Stock Trading Application | A multi-agent system designed for a specific domain, likely demonstrating a protocol for collaboration between specialized financial agents. |

## Getting Started

To get started with any of the projects, first clone this main repository to your local machine.

    git clone [https://github.com/abhijit-d01/AI-Agents.git](https://github.com/abhijit-d01/AI-Agents.git)
    cd AI-Agents
    

Once cloned, navigate to the specific project directory you are interested in.

    # Example: To explore the AutoGen project
    cd AutoGen
    

Each project folder is self-contained and includes its own `Readme.md` with detailed setup and usage instructions, along with a `requirements.txt` file for its specific dependencies.

## Frameworks at a Glance

### 🤖 OpenAI Agent SDK

-   **Core Idea:** A framework for building powerful, stateful assistants that can be given instructions and access tools (like Code Interpreter or custom functions).
    
-   **Key Features:** Persistent `Assistants`, state managed in `Threads`, and asynchronous `Runs`.
    
-   **Best For:** Creating robust, tool-augmented assistants that can handle multi-turn conversations and file analysis.
    

### 👥 AutoGen (from Microsoft)

-   **Core Idea:** A framework for orchestrating conversations between multiple AI agents that can collaborate to solve tasks.
    
-   **Key Features:** Customizable agents with specific roles and "human-in-the-loop" capabilities.
    
-   **Best For:** Automating complex workflows by simulating a team of specialized AI experts.
    

### 🕸️ LangGraph

-   **Core Idea:** An extension of LangChain for building agent runtimes that are cyclical and stateful, modeled as a graph.
    
-   **Key Features:** More control over the agent's reasoning loop, allowing for modifications and cycles, rather than a fixed chain.
    
-   **Best For:** Creating sophisticated agents that require complex, non-linear reasoning and the ability to correct their own mistakes.
    

### 📈 MCP (Model Context Protocol)

-   **Core Idea:** An open-source, universal protocol designed to standardize communication between AI models, agents, and external tools, creating a unified and interoperable AI ecosystem. It acts as a universal API for AI.
    
-   **Key Features:** Standardized context sharing that allows different AI systems to understand and continue each other's work, simplified state management, and tool-agnostic extensibility.
    
-   **Best For:** Building complex, interoperable AI systems where agents from different providers need to collaborate seamlessly. It is ideal for creating a unified "AI-native" backend for applications, breaking down AI silos.

## Contributing

Contributions are welcome! If you have an implementation of another agentic framework or an interesting use case for an existing one, please feel free to open a pull request.

Please try to follow the existing structure:

1.  Create a new directory for your project.
    
2.  Include all necessary code and a `requirements.txt` file.
    
3.  Add a detailed `Readme.md` within your project's directory explaining what it does and how to run it.
    

## License

This repository is licensed under the MIT License. See the `LICENSE` file for more details.