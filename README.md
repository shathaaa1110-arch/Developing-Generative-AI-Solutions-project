# Hackathon Multi-Agent System

A three-agent workflow in n8n that finds hackathons open for registration, picks the ones that fit a user's interests, and reviews the result before the user sees it.

## About

This is the final project for the **Developing Generative AI Solutions** training program (تطوير حلول الذكاء الاصطناعي التوليدي) delivered by SDAIA Academy.

SDAIA Academy on GitHub: https://github.com/SDAIAAcademy

**Team:** 

## Team

| Member | GitHub | Role |
|---|---|---|
| Shatha Alanazi | [@your-username](https://github.com/shathaaa1110-arch) 
| Haya Aldossari | [@their-username](https://github.com/hayaaldossari) 
| Yara Algarni | [@their-username](https://github.com/yaraalgarni-dot) 
## Project idea

Finding a hackathon worth joining takes time: listings are scattered, many have closed, and most do not match a person's interests or constraints. This system does that work from one chat message.

The user writes what they are looking for, for example:

> I am a beginner interested in AI and health, and I prefer online events.

The system replies with up to five hackathons, each with a fit score, a one-sentence reason, the dates, the location, and the link.

The work is split between three agents so that no single model both writes the answer and judges it. One agent searches, one personalizes, and one reviews. An answer reaches the user only after the reviewer approves it, or it is clearly marked as unverified.

## Repository contents

| File | Description |
|---|---|
| `hackathon_multi_agent_workflow.json` | The n8n workflow to import |
| `README.md` | This file |
