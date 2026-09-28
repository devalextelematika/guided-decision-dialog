---
name: guided-decision-dialog
description: "Run a sequential clarification interview when the user asks to define business rules, product behavior, architecture, or implementation choices through questions, answer options, and recommendations. Ask exactly one consequential decision question per turn. Do not use for ordinary factual questions, completed specifications, or tasks where no user choice is needed."
---

# Guided Decision Dialog

Clarify unresolved business or implementation decisions without overwhelming the user or silently choosing product behavior for them.

## Interaction Contract

1. Identify the next unresolved decision that can materially change behavior, scope, risk, cost, UX, compatibility, or maintainability.
2. Ask exactly one such question in the current response. Do not bundle independent decisions or preview a questionnaire.
3. Offer two to four concise, numbered, mutually exclusive options. For each option, state its practical consequence or main trade-off in one short sentence.
4. Mark exactly one option as the recommendation and justify it briefly from the known requirements, evidence, and scope. Do not disguise a preference as a confirmed user decision.
5. Invite the user to reply with the option number or their own alternative, then stop. Do not proceed to another decision or begin implementation while waiting for the answer.
6. After the user answers, acknowledge the decision in one concise sentence. If another consequential decision remains, ask only that next question using the same format.
7. When no consequential decisions remain, summarize the confirmed decisions compactly and state the next available step. Do not implement, edit, submit, or perform another mutation unless the user has authorized it.

## Question Design

- Resolve business rules before implementation details when the technical choice depends on the business decision.
- Ask only questions whose answers matter. Do not ask the user to choose facts that repository inspection, documentation, or safe read-only research can establish.
- Use realistic options rather than artificial alternatives. Keep labels short and make differences easy to compare.
- Prefer a decision-oriented question such as `How should the system behave when ...?` over an open-ended request such as `What do you want?`.
- Match the user's language and level of technical detail.
- Do not include `Other` as a numbered option; always allow a custom answer after the numbered choices.
- If the user has already selected an option, do not ask the same question again unless new evidence materially changes the decision.

## Response Shape

Use a compact form similar to this, adapting labels and detail to the task:

```text
Question: How should the system behave when ...?

1. Option A — practical consequence or trade-off.
2. Option B — practical consequence or trade-off.
3. Option C — practical consequence or trade-off.

Recommendation: 2 — brief evidence-based reason.

Reply with the number or your own variant.
```

Do not add a long preamble, unrelated analysis, a second question, or an implementation plan to the same response unless the user explicitly asks for it.

## Scope and Authorization

This dialog format does not expand the task's permissions. Preserve any analysis-only, read-only, no-edit, approval, security, cost, or external-side-effect boundary already set by the user or project. A selected answer confirms that decision only; it does not authorize unrelated work or implementation unless that authorization is explicit in context.
