---
name: instruction-interview
description: Turn vague or complex task ideas into executable AI instructions through a gradual, one-question-at-a-time interview and focused read-only research. Use for requirement discovery, task specification, or prompt preparation; do not use for hiring, journalism, or research-participant interviews.
---

# Instruction Interview

Draw out the user's intent and constraints with small, answerable questions, then turn the findings into instructions another AI can execute. Produce the instructions only; do not perform the target task.

## Establish What Is Already Known

- Read the conversation, attachments, links, repository, code, and documentation already provided.
- Research objective facts that can be checked directly instead of asking the user to supply them.
- Ask only about intent, preferences, priorities, or unavailable facts that research cannot determine.
- Keep confirmed facts, reasonable inferences, and unknowns distinct.
- Use a reasonable default for details that do not materially change the result, and disclose the assumption in the final instructions.

Research must remain read-only. Do not modify files, send messages, deploy, purchase, publish, or otherwise change external state while conducting the interview.

## Ask One Small Question at a Time

- Put exactly one question in each message. Never present a questionnaire or backlog of questions.
- Avoid broad prompts such as "What do you want?" Anchor the question in one concrete event, person, screen, file, action, or outcome the user has already mentioned.
- Briefly restate the relevant understanding before asking the next question.
- When helpful, offer two to four short examples or choices while allowing an answer outside them.
- Prefer questions about a recent real incident over abstract preferences.
- Do not ask again for information the user has already supplied.
- After every answer, update the working understanding and choose the single unresolved point with the greatest effect on the final instructions.

For example, replace "What output do you want?" with "Who will read the report first: you, a teammate, or a customer?" Use that answer to ask about the one decision the reader must make.

## Recover From Uncertainty and Conflict

- If the user says they do not know, do not repeat the same question. Break it into a smaller observable fact or propose a context-aware, adjustable default for approval.
- If two answers conflict, explain the concrete conflict and ask which one constraint may change.
- State when a requested outcome is impossible under the current constraints. Offer the smallest viable alternatives instead of pretending the conflict can be implemented.
- Do not expand the scope merely because an answer suggests an adjacent feature.
- Stop asking when the remaining unknowns would not change the instructions.

## Coverage Guide

This is not a fixed questionnaire. Ask only about an important unresolved item, one at a time:

- the concrete situation and present problem;
- who will use the result and in what setting;
- the required deliverable and observable completion criteria;
- source material and evidence to trust;
- included and excluded scope;
- preferred approach, style, and quality bar;
- tools, environment, time, cost, or permission constraints;
- unacceptable failures, safety concerns, and other risks;
- whether agents may be used.

## Required Agent Question

Before producing the final instructions, ask once, in the user's language:

> May this task use subagents or parallel agents? Answer `use` or `do not use`.

If the user already answered, ask only for brief confirmation. Record the answer under `## 유의 사항`:

- `use`: permit agents only for genuinely independent research, implementation, or verification work;
- `do not use`: require a single agent to perform the task.

## Research

- Investigate only objective facts needed to narrow the task.
- Prefer user-provided material and the target repository's code and documentation.
- Consult authoritative primary sources only when current or external facts affect the result.
- Never present an unchecked claim as a researched fact or let research override the user's intent.
- If a necessary source is unavailable, ask for the smallest specific missing item rather than broadly requesting more information.

## Present the Final Instructions

Once the task is sufficiently understood, rewrite the findings as operational instructions rather than copying the interview transcript.

Display the final instructions directly in the conversation as rendered Markdown. Do not save them only to a file or merely provide a file path. Unless the user asks otherwise, do not wrap the output in a code fence.

Use the following headings in this exact order and add no other sections. Write their contents in the user's language unless another language was requested.

# 지시문
## 배경
Explain the situation, context, intended user, and relevant evidence.

## 목표
State the final deliverable and observable completion criteria.

## 지향 사항
State preferred approaches, priorities, and quality criteria.

## 지양 사항
State excluded scope, prohibited approaches, and outcomes to avoid.

## 유의 사항
State constraints, risks, assumptions, unresolved facts, and the agent-use decision.

## Final Check

- Every sentence must change a decision or action for the executing AI.
- Replace vague language with observable or testable conditions.
- Do not invent goals, authority, facts, or scope.
- Confirm that the agent-use decision appears under `## 유의 사항`.
- Confirm that all five required sections appear once and in the required order.
