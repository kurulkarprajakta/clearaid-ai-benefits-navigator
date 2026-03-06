# ClearAid – System Design

## Overview

ClearAid is an AI-guided benefits discovery and application navigation system designed to support underserved users through a low-stress, structured experience.

The system combines a user-facing prototype with a reusable skills-based reasoning layer. The current implementation uses a Lovable UI, a five-skill Markdown skills pack, Codex-based execution/testing, and an MCP filesystem tool demonstration.

## High-Level Architecture

The system has four main layers:

1. **UI Layer**
   - Lovable-based frontend
   - captures need category, location, profile details, language, and user constraints
   - displays results, confidence meters, explainability, and Navigator steps

2. **Skill Layer**
   - eligibility_precheck_router
   - plain_language_explainer
   - document_checklist_builder
   - next_step_advisor
   - application_navigator

3. **Execution / Orchestration Layer**
   - Codex is used to install and invoke skills in realistic runs
   - skills are chained depending on user goal and friction point

4. **Tool Access Layer**
   - MCP filesystem tool in Claude Desktop used to read local skill documentation and confirm successful access

## End-to-End Flow

1. User selects need category
2. User provides location and lightweight contextual details
3. User chooses language preference
4. eligibility_precheck_router generates likely benefit pathways and confidence level
5. next_step_advisor recommends a prioritized starting path
6. document_checklist_builder creates a preparation checklist
7. plain_language_explainer simplifies confusing form questions when needed
8. application_navigator guides the user step-by-step through the application process

## Output Types

ClearAid returns:
- program shortlist
- confidence meter
- “Why am I seeing this?” explanation
- additional data requests
- document checklist
- next-step guidance
- navigator flow with progress tracking
- follow-up plan and call support

## Why this architecture matters

This design makes ClearAid more than a static website. The UI is backed by reusable product logic that can be composed differently based on the user’s needs, urgency, and barriers.

## Key Product Principles

- privacy-first inputs
- no eligibility guarantees
- multilingual accessibility
- trauma-informed guidance
- structured, low-stress support
- explainable recommendations

## Current Limitations

- state/county variation can reduce precision
- exact local resource routing is limited without ZIP/county-specific retrieval
- the current system is a prototype and not yet connected to production APIs

## Next Improvements

- add county/ZIP-aware resource lookup
- integrate backend orchestration
- log skill invocation and reasoning traces
- improve edge-case handling and benchmark coverage
