# ADK Made Simple - Agent Examples

This project demonstrates simple agents built using the Google Agent Development Kit (ADK).
Currently, it contains one agent: "Game Dev News Scout".

## Agents

- **Game Dev News Scout**: Simulates fetching recent discussion titles from game development subreddits.

## General Setup

1.  **Clone the repository:**

    ```bash
    git clone <your-repo-url>
    cd adk-made-simple
    ```

2.  **Create and activate a virtual environment (Recommended):**

    ```bash
    python -m venv .venv
    # On Windows
    .\.venv\Scripts\activate
    # On macOS/Linux
    source .venv/bin/activate
    ```

3.  **Install general dependencies:**

    ```bash
    pip install -r requirements.txt
    ```

4.  **Agent-Specific Setup:** Navigate to the specific agent's directory within `agents/` and follow the instructions in its `README.md` (or follow the steps below for the default agent).

## Game Dev News Scout - Setup & Running

1.  **Navigate to Agent Directory:**

    ```bash
    cd agents/news_scout
    ```

2.  **Set up API Key:**

    - Copy the example environment file:
      ```bash
      cp .env.example .env
      ```
    - Edit the `.env` file and add your Google AI API Key. You can obtain one from [Google AI Studio](https://aistudio.google.com/app/apikey).
      ```dotenv
      GOOGLE_API_KEY=YOUR_API_KEY_HERE
      ```
    - _Note:_ You might need to load this into your environment depending on your OS and shell (`source .env` or similar) if `python-dotenv` doesn't automatically pick it up when running `adk`.

3.  **Run the Agent:**

    - Make sure your virtual environment (from the root directory) is activated.
    - From the `agents/news_scout` directory, run the agent using the ADK CLI, specifying the core code package:
      ```bash
      adk run news_scout
      ```
    - Alternatively, from the project root (`adk-made-simple`), you might be able to run:
      ```bash
      adk run agents.news_scout
      ```
      _(Check ADK documentation for preferred discovery method)_

4.  **Interact:** The agent will start, and you can interact with it in the terminal. Try prompts like:
    - `What's the latest news?`
    - `Give me news from unrealengine`

## Project Structure Overview

```
adk-made-simple/
├── agents/
│   └── news_scout/          # Game Dev News Scout Agent
│       ├── news_scout/      # Core Python package
│       │   ├── __init__.py
│       │   └── agent.py
│       ├── .env.example     # Agent-specific env example
│       ├── .gitignore       # Optional: Agent-specific ignores
│       └── README.md        # Optional: Agent-specific README
├── .venv/                   # Virtual environment directory
├── .env                     # Optional: Root env vars (or use agent-specific)
├── .gitignore               # Root gitignore file
├── requirements.txt         # Project dependencies
├── README.md                # This file (Overall Project README)
└── PLAN.md                  # Development plan notes
```
