# AI Agents Learning Repo

This repository tracks the AI agents I build while learning.

## Agents

- **Personal Assistant** (`personal_assistant.py`): A personal assistant that can schedule calendar events and send emails with human approval.
    - Here, the subAgents work synchronously , one after another
- **Customer Support State Machine** (`customer_support_with_handoff.py`): A step-based support agent that collects warranty and issue details before providing a solution or escalating to a human.
    - The workflow moves through three steps: warranty verification, issue classification, and resolution.
    - It uses shared state to carry information between steps. Software issues receive troubleshooting guidance, while in-warranty hardware issues receive repair instructions.
    - Hardware issues that are out of warranty are handed off to human support for paid repair options.
- **Multi-Source Knowledge Base with Routing** (`Multi-Source-Knowledge-base-with-routing.py`): A LangGraph workflow that routes a question to the knowledge sources most relevant to it.
    - A router model classifies the question into targeted sub-questions for GitHub, Notion, and/or Slack.
    - LangGraph uses conditional routing and `Send` to fan out the selected sub-questions to source-specific agents, allowing relevant searches to run in parallel.
    - Each source agent uses its own tools: GitHub searches code, issues, and pull requests; Notion searches documentation; and Slack searches team discussions and threads.
    - A synthesis step combines the returned results into one concise answer and can call out discrepancies between sources.
    - This approach is useful when information is distributed across multiple systems, but it can be token-intensive because it invokes a router, one or more subagents, and a synthesis model. Keep the source selection focused and avoid running every agent for every question.

More agents and experiments will be added as I continue learning.
