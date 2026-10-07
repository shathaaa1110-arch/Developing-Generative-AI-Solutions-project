# Hackathon Multi-Agent System

A three-agent workflow in n8n that finds hackathons open for registration, picks the ones that fit a user's interests, and reviews the result before the user sees it.

---

## About

This is the final project for the **Developing Generative AI Solutions** training program (تطوير حلول الذكاء الاصطناعي التوليدي) delivered by SDAIA Academy.

SDAIA Academy on GitHub: https://github.com/SDAIAAcademy

---

## Team

| Member |
|---|
| [Shatha Alanazi](https://github.com/shathaaa1110-arch) |
| [Haya Aldossari](https://github.com/hayaaldossari) |
| [Yara Algarni](https://github.com/yaraalgarni-dot) |

---

## Project idea

Finding a hackathon worth joining takes time: listings are scattered, many have closed, and most do not match a person's interests or constraints. This system does that work from one chat message.

The user writes what they are looking for, for example:

> I am a beginner interested in AI and health, and I prefer online events.

The system replies with up to five hackathons, each with a fit score, a one-sentence reason, the dates, the location, and the link.

The work is split between three agents so that no single model both writes the answer and judges it. One agent searches, one personalizes, and one reviews. An answer reaches the user only after the reviewer approves it, or it is clearly marked as unverified.

---

## System Architecture

The architecture consists of 3 specialized AI Agents operating under strict governance and quality control loops:

1. **Finder Agent (Tavily Search Tool):** Researches, verifies, and extracts raw hackathon details (Name, Date, Location, URL) without halluncinations.
2. **Personalizer Agent:** Evaluates and scores hackathons against the user profile (Match Score 0–100%) and formats output into clean Markdown.
3. **Supervisor Agent (Governance & Auditing):** Audits Agent 2's output for accuracy and completeness. Implements a Feedback/Retry loop (Approved vs Rejected).

---
   
## Technical Stack & Tools

- **Workflow Orchestration:** n8n
- **LLM Engine:** Groq API (`llama-3.1-70b-versatile` / `qwen/qwen3.8-27b`)
- **Web Search Engine:** Tavily AI Search
- **Response Handling:** Webhook / Dynamic Chat Output

---

## Repository contents

| File | Description |
|---|---|
| `hackathon_multi_agent_workflow.json` | The n8n workflow to import |
| `README.md` | This file |

---

## How to Import and Run

1. Download the `hackathon_multi_agent_workflow.json` file from this repository.
2. Open your **n8n** instance and click **Import from File**.
3. Configure your API Keys for **Groq** and **Tavily** in the credentials section.
4. Execute the workflow via the Chat Trigger.
