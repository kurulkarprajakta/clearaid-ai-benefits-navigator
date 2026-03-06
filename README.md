# ClearAid – AI-Guided Benefits Discovery & Application Navigation

![ClearAid Logo](assets/logo.png)

## Project Snapshot

**ClearAid** is an AI-powered benefits navigator designed to help underserved communities, immigrants, and first-time applicants discover relevant support programs and move through applications with less confusion.

**Live Demo:** https://clearaid.lovable.app  
**Project Type:** AI Product / Social Impact / Portfolio Prototype  
**Focus Areas:** accessibility, multilingual support, agentic guidance, eligibility precheck, application navigation

## Problem

Many eligible people never receive government or community benefits because discovery and application processes are confusing, bureaucratic, and intimidating. This challenge is especially severe for immigrants, first-time applicants, and users with limited English proficiency.

## Solution

ClearAid helps users:
- understand what help exists
- narrow down likely benefit pathways
- interpret confusing application questions
- prepare documents
- move forward with a step-by-step application plan in their preferred language

## Core Capabilities

- Multilingual support
- AI-guided benefit discovery
- Confidence-based program recommendations
- Explainability through “Why am I seeing this?”
- Step-by-step Navigator flow
- Document checklist generation
- Follow-up planning and call scripts
- Skills-based agentic orchestration


## System Architecture

ClearAid combines:
- a **Lovable UI prototype** for user interaction
- a **skills-based reasoning layer** for routing, explanation, checklist generation, and navigation
- **Codex-based orchestration/testing**
- an **MCP filesystem tool** for local skill documentation access

See [system_design.md](system_design.md) for the full architecture.

## AI Skill Architecture

ClearAid uses five reusable skills:

- **eligibility_precheck_router** – narrows likely benefit pathways and asks only the most important follow-up questions
- **plain_language_explainer** – simplifies confusing form language with examples and reassurance
- **document_checklist_builder** – creates a personalized checklist and alternatives if documents are missing
- **next_step_advisor** – recommends ordered, realistic next steps based on urgency and constraints
- **application_navigator** – guides users step-by-step through the process with progress gating

See [ai_skills_overview.md](ai_skills_overview.md) and the `/skills` folder.

## Example Product Journey

A user in Washington selects a need category, shares a small amount of profile information, chooses a preferred language, and receives:
- likely benefit options
- confidence indicators
- explainability notes
- document preparation help
- a structured application plan
- follow-up guidance

## Real Runs and Evidence

This repo includes evidence from:
- prototype screenshots
- Codex skill orchestration runs
- MCP filesystem proof for local skill reading

See [benchmark_summary.md](benchmark_summary.md) for run summaries and comparison notes.

## My Role

- Product ideation and problem definition
- User flow design
- Prototype direction in Lovable
- Skills pack design and documentation
- AI workflow orchestration testing
- Evaluation, benchmarking, and report writing

## Tech / Build Stack

- Lovable
- Markdown-based reusable skills
- Codex
- MCP filesystem tool
- Product design / conversational UX

## Repo Contents

- `README.md` – project overview
- `system_design.md` – system architecture and orchestration
- `product_overview.md` – vision, users, and value proposition
- `feature_list.md` – current and planned features
- `ai_skills_overview.md` – skill-based design
- `benchmark_summary.md` – run evidence and benchmark summary
- `skills/` – five reusable AI skills
- `assets/` – screenshots, logos, and execution evidence

## Future Enhancements

- ZIP/county-specific resource routing
- stronger location-aware retrieval
- backend skill invocation APIs
- better structured logging and evaluation
- richer multilingual assistance and edge-case handling

## Author

Prajakta Kurulkar  
MS Information Systems – University of Washington  
AI Products | Product Management | FinTech | Social Impact
