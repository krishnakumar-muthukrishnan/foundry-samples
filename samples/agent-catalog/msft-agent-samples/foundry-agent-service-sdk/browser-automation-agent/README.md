# 🌐 Browser Automation Agent

This template helps build an agent that enables users to perform real-world browser tasks through natural language prompts. Powered by **Azure AI Agent Service** and **Azure Playwright Service**, it facilitates multi-turn conversations to automate browser-based workflows such as searching, navigating, filling forms, and booking.

**WARNING:** Browser automation comes with significant security risks. Both errors in judgment by the AI and the presence of malicious or confusing instructions on web pages which the AI encounters may cause it to execute commands you do not intend, which could compromise the security of your browser, your computer, and any accounts to which the browser or AI has access, including personal information, financial, or enterprise systems. We recommend that you use this type of agent only in isolated environments with controlled access, such as browsers running within dedicated VMs.

 # 🧠 Scenario Overview

This agent demonstrates a browser automation experience where the user interacts with a website conversationally—like booking a class online. Here's how it works:

1. **User Prompt**: The user asks for available classes.
2. **Session Provisioning**: The request is received by Azure AI Agent Service, which provisions a private browser session using Azure Playwright Service.
3. **Web Interaction**: The browser performs Playwright-driven actions to retrieve and display class options.
4. **Follow-Up Commands**: The user provides further input to complete the booking, all within the same multi-turn thread.

---

## 💼 Use Cases

- **Booking & Reservations**: Automate form-filling and schedule confirmation across booking portals.
- **Product Discovery**: Navigate ecommerce or review sites, search by criteria, and extract summaries.
- **Web Form Interactions**: Log in, submit applications, or upload documents through web UIs.
- **Customer Support Tasks**: Automatically navigate portals to retrieve account status, ticket updates, etc.

---

## 🧩 Tools

This agent leverages **Azure AI Agent Service** and uses:

- **Browser Automation Tool** (via Playwright): Executes browser-based tasks on your behalf, securely and asynchronously.
- **Azure Playwright Service**: Powers the browser session backend with serverless browser capabilities.

The agent is configured through a Python script (`browser_automation.py`) and authenticated using managed identity.

---

## 🧠 Architecture Overview

![Architecture Diagram](assets/architecture-browser-automation.png)

---

## ⚙️ Setup Instructions

### Prerequisites

1. Azure subscription with the following permissions
   - Contributor or Cognitive Services Contributor role (for resource deployment)
   - Azure AI Developer and Cognitive Services user role (for agent creation)
2. Agent setup: deploy the latest agent setup using this ([custom deployment](https://www.aka.ms/basic-agent-deployment)).
   - The above creates:
      - AI Services resource
      - AI Project
      - Model deployment
3. Python 3.8+
4. Azure CLI
   
### Template specific requirements:
- Playwright connection (optional, see below)

### Environment Variables

Set the following environment variables before running the sample:

```bash
PROJECT_CONNECTION_STRING=<your_project_connection_string>
MODEL_DEPLOYMENT_NAME=<your_model_deployment_name>
PLAYWRIGHT_CONNECTION_ID=<optional_serverless_connection_id>


