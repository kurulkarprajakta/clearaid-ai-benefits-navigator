---
name: document_checklist_builder
description: Generate a calm, personalized document checklist for a selected benefit type with alternatives when documents are missing.
---
Skill 4
name

document_checklist_builder

purpose

Create a personalized, low-stress checklist of documents and information a user should gather for a specific benefit application, based on their selected program type and basic context—so they can apply faster and avoid common delays.
This appears as a “What to prepare” panel/card after the user selects a benefit option.

inputs

selected_program_type: Medicaid/CHIP | SNAP | WIC | TANF | housing_assistance | childcare_subsidy | education_aid | utilities_assistance | other

location: state (required), optional county/city/ZIP

user_context (optional): household size, dependents, employment status, income band, student status, senior/disability flags

user_constraints (optional): missing_ID, no_fixed_address, no_paystubs, limited_internet, limited_english

language: en | es | hi | zh (default en)

checklist_length: short | standard (default standard)

outputs

core_checklist: 6–12 items that are commonly requested for that program type

nice_to_have: 3–6 optional items that can help (if available)

alternatives_if_missing: “If you don’t have X, try Y” suggestions (non-prescriptive, varies by state)

organization_tips: how to store/submit (photos, folder naming, note of dates)

redaction_note: what to redact before sharing (SSN, full DOB, account numbers)

translation: the checklist in the requested language

reassurance_line: supportive message that it’s okay if some items are missing

step-by-step behavior

Confirm what we’re preparing for

“You selected ___ in ___ (state). Here’s a simple prep list.”

Load a program-specific template

Use a base template per program type (e.g., SNAP vs Medicaid vs Housing).

Keep language as “commonly requested” and “may vary by state/county.”

Personalize the checklist using user context

If household size > 1 → include household composition items.

If employed → include income proof options.

If self-employed/variable income → include “any income records you have” (broad).

If child/pregnancy flags → include child-related/pregnancy-related proofs (non-sensitive, optional).

Add barrier-aware alternatives

If missing_ID: suggest acceptable alternatives “often include school ID, employer ID, or other documents” (without claiming universal acceptance).

If no_fixed_address: suggest “letter from shelter/host, mail pickup options” (varies).

If no_paystubs: suggest “bank deposit history, employer letter” (varies).

Keep it calm and doable

Offer “start with just the top 3 items” when anxiety/urgency is high (inferred by constraints or user wording).

Add submission/organization tips

Photos/scans, readable filenames, keep dates consistent, retain receipts/confirmation numbers.

Privacy & redaction

Remind the user to redact sensitive numbers before sharing documents with anyone other than official portals.

Translate output

Output the same structure in the requested language, keeping official program names recognizable.

constraints and guardrails

No guarantees: Do not claim these documents are required everywhere. Always label as “commonly requested” and “may vary.”

No collection of sensitive data: Do not ask for SSN, full DOB, immigration doc numbers, or bank account numbers.

No legal advice: Provide general information only; direct users to official guidance for definitive requirements.

Respect user dignity: Avoid shaming language for missing documents.

Avoid inventing state-specific lists: If the user asks “exactly what WA/TX requires,” advise checking the official state portal checklist or speaking to the agency.

failure modes

Program ambiguity: “Housing assistance” can mean multiple programs; checklist may be too generic without narrowing.

Local variations: County offices may request different proofs; user may need to confirm with their agency.

User constraints unknown: Without knowing barriers, the checklist may not include the most helpful alternatives.

Overwhelm risk: Too many items can stress users; use checklist_length=short when needed.

example usage

Input

selected_program_type: SNAP

location: “California”

user_context: “2 adults, 1 child; recently unemployed; income band very_low”

user_constraints: “no_paystubs”

language: en

checklist_length: standard

Output (English)
Core checklist (commonly requested)

Proof of identity (ID if available)

Proof of address (lease, utility bill, or a letter showing where you live — varies)

Household members list (names + relationship)

Income information (any recent pay info, unemployment info if applicable, or an estimate if not available)

Expense basics (rent/mortgage amount, utilities estimate)

Child-related details (child’s info; school/childcare costs if relevant)

Nice to have

Bank deposit summary showing recent income (if comfortable sharing with the official agency)

Employer separation letter or last day of work note

Any notices you’ve received from the agency

If you don’t have pay stubs

You can often use: a simple employer letter, bank deposit history, or a written statement—rules vary, so ask the caseworker what they accept.

Organization tips

Take clear photos in good light, name files like ID_front, Lease, Utility_Jan, and keep a note of submission dates.

Privacy note

Redact SSN/full account numbers if sharing outside official portals.

Reassurance

“It’s okay if you don’t have everything today. Start the application with what you have—many programs let you provide missing items later.”

Output (Spanish / Hindi / Mandarin brief samples)

Spanish: “Lista básica (común): identificación, comprobante de domicilio, miembros del hogar…”

Hindi: “आम तौर पर मांगे जाने वाले: पहचान पत्र, पते का प्रमाण, घर के सदस्यों की सूची…”

Mandarin: “常见材料：身份证明、住址证明、家庭成员信息、收入与支出概况…”
