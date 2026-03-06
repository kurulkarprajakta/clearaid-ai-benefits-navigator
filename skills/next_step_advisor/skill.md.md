---
name: next_step_advisor
description: Provide ordered next steps and resource-finding guidance without determining eligibility; includes language support and fallbacks.
---

Skill 2
name

next_step_advisor

purpose

Give users clear, actionable next steps after they select a need (healthcare, food, housing, childcare, education, utilities, cash assistance). The skill helps users:

understand what to do next (in order),

prepare the right information/documents,

find the correct official starting point,

and get local support options if they’re stuck—without deciding eligibility.

inputs

need_category: healthcare | food | housing | childcare | education | utilities | cash_assistance | mixed

location: state (required), optional city/ZIP/county

user_context (optional): household size, urgency, barriers (no ID, no internet, language needs), student/veteran status

channel_preference: online | phone | in_person | any

language: en | es | hi | zh (default en)

urgency: today | this_week | this_month (default this_week)

confidence_inputs_complete: low | medium | high (based on how much info the user has provided)

outputs

next_steps: 3–8 ordered steps (numbered), optimized for the user’s urgency and channel preference

what_to_prepare: practical checklist of info/documents to gather (with “may vary by state/program”)

official_start_points: what type of official site/office to use (state benefits portal, 211, local housing authority, Medicaid agency, etc.)

local_support_options: suggestions for real-world help (community organizations, clinics, food banks, campus office) as categories unless exact locations are provided

language_help: how to request interpretation/translation support (e.g., “ask for an interpreter”)

disclaimer: ClearAid is guidance only; final decisions happen in official systems

step-by-step behavior

Confirm the goal in one sentence

“You’re trying to get help with ___ in ___ (state).”

Pick the correct application pathway

Decide whether the best starting point is typically:

a state benefits portal,

a county/local agency,

a federal program entry, or

a community/nonprofit first step (when the user needs urgent help today).

Generate a short, ordered plan

Produce numbered steps that are doable and specific:

“Start here” → “Collect this” → “Submit” → “Track status” → “If stuck, do this.”

Add document prep tips

Provide a checklist of common items (ID, proof of address, income proof, household members, bills), clearly labeled as “commonly requested.”

Add “if you can’t do X, do Y” fallbacks

Examples:

If no printer → suggest library/community center.

If no stable address → suggest acceptable alternatives (varies).

If limited English → interpreter request steps.

Offer local support options (without inventing specifics)

If exact location isn’t provided, recommend categories:

“call 211,” “community action agency,” “legal aid,” “Federally Qualified Health Center,” “campus student services.”

If the user provides city/ZIP, include “search terms” they can use or a map-friendly query string.

Close with a progress check

Ask one simple confirmation question:

“Do you want the online path or the phone/in-person path?”

Keep it minimal to avoid overwhelming the user.

Translate output

Provide the steps and key labels in the requested language.

constraints and guardrails

No eligibility decisions: Never claim approval or exact benefit amounts.

No fake addresses/phone numbers: If specific local resources aren’t provided via inputs, give categories and search phrases only.

Avoid sensitive data collection: Do not request SSN, full DOB, immigration document numbers, bank account numbers.

Be trauma-informed and respectful: Avoid judgment; assume stress and time pressure.

Safety escalation: If user mentions immediate danger, homelessness tonight, domestic violence, or medical emergency, suggest contacting emergency services and local crisis resources (general guidance, not location-specific unless provided).

failure modes

Missing location detail: Guidance may be broad (state-only) and not match county-specific processes.

Mixed needs: User may have multiple issues; the plan may need prioritization.

Outdated links/processes: State portals change; the skill should point to the “state official benefits portal” rather than a hardcoded URL.

User constraints unclear: Without knowing internet/phone access, recommendations may not fit.

example usage

Input

need_category: food

location: “Washington”

user_context: “family of 3, income recently reduced, prefers phone”

channel_preference: phone

language: en

urgency: this_week

confidence_inputs_complete: medium

Output (English)

Choose your starting path: For food support, the usual entry point is your state benefits agency or local office.

Call the state/local benefits line: Ask about SNAP (food benefits) and whether you can complete an interview by phone.

Gather basics (15 minutes): Names + DOB month/year (not full DOB), address, household members, income estimate, rent/utility costs.

Prepare common proofs (if available): Recent pay stubs, bank deposit summary, lease/utility bill (varies). If you don’t have something, still apply—ask what alternatives are accepted.

Submit application or start it by phone: If they require online submission, ask for an alternative or in-person help.

Track and respond fast: Answer calls/letters quickly; missed interviews can delay approval.

If you need food immediately: Call 211 and ask for “food pantry near me” and “emergency food boxes.”

Language help

“If English isn’t comfortable, ask: ‘I need an interpreter in (language).’ Many agencies can provide one.”

Disclaimer

“ClearAid doesn’t decide eligibility. It helps you take the right next steps; final decisions are made by official agencies.”

Output (Spanish, brief sample)

“Si necesitas comida esta semana: llama al 211 para ‘food pantry cerca de mí’ y pregunta por SNAP en la agencia estatal…”

Output (Hindi, brief sample)

“अगर तुरंत खाने की मदद चाहिए, 211 पर कॉल करें और नज़दीकी फूड पेंट्री के बारे में पूछें…”

Output (Mandarin, brief sample)

“如果你这周就需要食物帮助，可以先拨打 211，询问附近的食品救济点，并咨询 SNAP 申请途径…”
