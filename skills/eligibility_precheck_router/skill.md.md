Skill 3
name

eligibility_precheck_router

purpose

Quickly narrow down the most relevant benefit programs and pathways for a user based on their situation, and identify the minimum follow-up questions needed to reduce uncertainty—without making an official eligibility decision.

inputs

need_category: healthcare | food | housing | childcare | education | utilities | cash_assistance | mixed

location: state (required), optional city/ZIP/county

household: household size, dependents (optional)

income_band (optional): none/unknown | very_low | low | moderate | above_moderate
(bands are intentionally broad to avoid false precision)

life_situation_flags (optional): pregnant/postpartum, child_under_5, senior, disability, student, veteran, recently_unemployed, homeless_or_at_risk

documentation_barriers (optional): missing_ID, no_fixed_address, no_paystubs, limited_internet, limited_english

language: en | es | hi | zh (default en)

risk_tolerance: conservative | balanced (default balanced)
(conservative = show fewer programs but higher relevance)

outputs

program_shortlist: 3–8 candidate programs/types with “why this might fit”

follow_up_questions: 3–7 targeted questions that change routing

confidence_meter: low | medium | high + 1–2 reasons (based on missing inputs)

recommended_path: online | phone | in_person + why (based on barriers/urgency)

handoff_notes: what to do next (links/categories, not hardcoded URLs), and who can help (211, local agencies, nonprofits)

disclaimer: not an official eligibility decision

step-by-step behavior

Restate the need + location

“You’re looking for help with ___ in ___ (state).”

Build a program universe

Use the need category to pull common program types (examples):

Healthcare: Medicaid/CHIP, marketplace subsidies, community clinics

Food: SNAP, WIC (if pregnant/child under 5), school meal programs

Housing: emergency shelter/rapid rehousing, local housing authority waitlists, utility support

Childcare: state childcare subsidy, Head Start/ECEAP-type programs

Utilities: LIHEAP-type energy assistance, local utility discount programs

Cash assistance: TANF-type programs, local emergency funds

Apply broad screening rules (not final eligibility)

Use high-level heuristics:

household size + income band,

presence of children/pregnancy/senior/disability,

urgency (today/this week inferred from “at risk” flags),

barriers (missing documents / limited internet / language).

Rank and present the shortlist

Provide each candidate with:

“Why this is on the list”

“What you’ll usually need” (very brief)

“Where to start” (category: state portal / county office / 211 / clinic)

Generate minimal follow-up questions

Ask only questions that would change recommendations, e.g.:

“Do you have children under 18 in the home?”

“Is anyone pregnant or postpartum?”

“Do you have any income right now (rough range is fine)?”

“Do you have stable housing this month?”

“Do you prefer online, phone, or in-person?”

Compute a confidence meter

High: location + need + at least 2 of (household, income band, key flags)

Medium: missing one major input (income band or household)

Low: only need + state provided, or conflicting info

Explain confidence in plain words (“I’m missing income band, so I’m listing broader options.”)

Recommend the best path (channel)

If limited internet or complex barriers → recommend phone/in-person support options.

If urgent (homeless tonight/food today) → prioritize emergency resources and human assistance.

Translate the summary

Provide the shortlist + follow-up questions in the requested language.

constraints and guardrails

No official eligibility statements: Never say “you qualify,” “you will get,” or give exact benefit amounts.

Avoid false precision: Use ranges/bands and “commonly” language.

Do not request sensitive identifiers: No SSN, full DOB, immigration document numbers, bank details.

No invented local info: If city/ZIP isn’t provided, don’t name specific organizations—use categories and search phrases.

Bias toward user safety: If the user indicates immediate danger, abuse, or medical emergency, advise emergency services and appropriate hotlines/resources.

failure modes

State/county differences: Some programs are administered differently by county; routing may be incomplete without county/city.

Income complexity: Self-employment, variable income, or mixed households can change which path is best.

User uncertainty: If the user doesn’t know household/income, recommendations may stay broad.

Overloaded output: If the shortlist is too long, reduce using risk_tolerance=conservative.

example usage

Input

need_category: healthcare

location: “Texas”

household: “2 adults, 1 child”

income_band: low

life_situation_flags: child_under_5

documentation_barriers: limited_english

language: en

Output (English)
Program shortlist

Medicaid/CHIP (state healthcare coverage) — likely relevant because you have a child and your income is in a lower band.

Community health clinics (sliding fee / low-cost care) — helpful if you need care quickly while an application is processing.

Marketplace plan + subsidies — a backup option if you don’t fit Medicaid/CHIP rules.

Follow-up questions (to narrow)

“Is the child under 19?”

“Do you have any current income this month (rough range is fine)?”

“Do you want help online, phone, or in-person?”

“Do you need language support (Spanish/Hindi/Mandarin) when calling?”

Confidence meter: Medium — I have need + state + household + income band, but exact program routing can vary by state/county.

Recommended path: Phone/in-person — because limited English can make online forms harder; ask for an interpreter.

Disclaimer: This is guidance only. Final eligibility and enrollment decisions happen in official state systems.

Output (Spanish, brief sample)

“Lista de opciones: Medicaid/CHIP, clínicas comunitarias, y plan del Marketplace… Preguntas clave: edad del niño, rango de ingreso, y si necesitas intérprete…”

Output (Hindi, brief sample)

“संभावित विकल्प: Medicaid/CHIP, कम-शुल्क कम्युनिटी क्लिनिक, Marketplace सब्सिडी… कुछ सवाल: बच्चे की उम्र, आय का मोटा रेंज, और क्या आपको दुभाषिया चाहिए…”

Output (Mandarin, brief sample)

“可能的选择：Medicaid/CHIP、社区诊所、以及 Marketplace 补贴计划… 需要确认：孩子年龄、收入大致范围、以及是否需要口译支持…”
