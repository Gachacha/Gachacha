# Day 20 — Lessons Learned: AI Workflow Guardrails

## Objective
Design guardrails that control AI behaviour inside Project 007 while keeping business rules as the decision authority and the state machine as workflow control.

## Key lessons
- Business rules provide decision authority.
- Guardrails define what the AI is allowed and not allowed to do.
- The state machine records where the client is and controls allowed transitions.
- The AI must not guess, invent exceptions, override approved rules, or treat attempted actions as successful outcomes.
- Unknown external results must remain unknown until verified or reconciled.
- Failures should follow the approved path: STOP → RECORD → RECOVER or ESCALATE.
- Human review is required when information is conflicting, sensitive, unsupported, or outside approved rules.

## Assessment
- Recall: 10/10
- Build: 5/5
- Test: 9/10
- Demonstrate: PASS

## Test correction
When a booking action has been sent but no confirmed response exists, the workflow must not mark the booking as failed. It must keep the result unconfirmed and verify/reconcile the external result.

## Demonstration
User demonstrated understanding that business rules provide authority, guardrails control AI behaviour, the state machine identifies the client's workflow position, and unresolved conditions follow recovery or escalation paths.

## Final principle
AI may act autonomously only when the current state, approved rules, required evidence, and guardrails all permit the action.

## Day 20 final status
- Learn: Complete
- Recall: 10/10
- Build: 5/5
- Test: 9/10
- Deploy: Complete
- Document: Complete
- Demonstrate: PASS
- Close: Complete

## Portfolio value
This work demonstrates the ability to design controlled AI automation in which AI reasoning operates within explicit business authority, behavioural guardrails, workflow states, verification requirements, and human escalation boundaries.
