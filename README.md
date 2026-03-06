# ClearAid – AI Benefits Navigator

Live Demo: https://clearaid.lovable.app

ClearAid is an AI-powered benefits navigator designed to help underserved communities and immigrants discover government benefits they may be eligible for. The product simplifies complex eligibility rules through multilingual support, AI-guided navigation, and step-by-step assistance.

---

## Problem

Millions of eligible individuals miss out on public benefits because eligibility rules are complex, information is fragmented across multiple websites, and application steps are difficult to understand.

Underserved communities and immigrants often face additional barriers such as language limitations and lack of clear guidance.

---

## Solution

ClearAid provides a simple interface where users can explore potential benefits through an AI-guided experience. The system captures key user information, evaluates eligibility criteria, and provides clear recommendations along with step-by-step guidance on how to proceed.

The goal is to make benefits discovery easier, faster, and more accessible.

---

## Key Features

• AI navigation agent that guides users through benefit discovery  
• Multilingual support to improve accessibility  
• Personalized eligibility reasoning based on user inputs  
• Step-by-step guidance explaining documents and next steps  
• Simplified experience for navigating complex government programs

---

## Architecture Diagram

```mermaid
flowchart LR
    A[User / Applicant] --> B[ClearAid Web Interface<br/>Lovable Frontend]

    B --> C[Language Selection Layer<br/>Multilingual Support]
    C --> D[AI Navigation Agent<br/>Conversational guidance]

    D --> E[User Profile Capture<br/>Household, income, location]
    E --> F[Eligibility Reasoning Engine]

    F <--> G[Benefits Knowledge Base<br/>Programs, criteria, documents]

    F --> H[Personalized Benefit Recommendations]
    H --> I[Step-by-Step Guidance Engine]

    I --> J[User Output Interface<br/>Clear recommendations + next steps]

    J --> K[Future Integrations]
    K --> L[Official benefit portals]
    K --> M[Application progress tracking]
