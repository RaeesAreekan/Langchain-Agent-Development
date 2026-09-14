# AI Agents Learning Repo

This repository tracks the AI agents I build while learning.

## Agents

- **Personal Assistant** (`personal_assistant.py`): A personal assistant that can schedule calendar events and send emails with human approval.
    - Here, the subAgents work synchronously , one after another
- **Customer Support State Machine** (`customer_support_with_handoff.py`): A step-based support agent that collects warranty and issue details before providing a solution or escalating to a human.
    - The workflow moves through three steps: warranty verification, issue classification, and resolution.
    - It uses shared state to carry information between steps. Software issues receive troubleshooting guidance, while in-warranty hardware issues receive repair instructions.
    - Hardware issues that are out of warranty are handed off to human support for paid repair options.

More agents and experiments will be added as I continue learning.
