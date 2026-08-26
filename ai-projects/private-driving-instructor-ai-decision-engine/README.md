# Project 006 — AI Decision Engine

## Purpose
Turn structured customer data into controlled business actions using approved rules, rule priority, verification gates, and human escalation.

## Architecture

Customer message → structured data → validation → priority checks → approved decision rules → action → human escalation where required.

## Core principles

- AI applies approved business rules; it does not invent business policy.
- Missing required information blocks decisions that depend on it.
- Unverified information must be verified before dependent decisions.
- Sensitive exceptions can override normal package rules.
- Customer preference and AI recommendation are separate data points.
- If no approved rule matches, route to human review.

## Projects connected

- Project 003 — Customer information and qualification
- Project 004 — Complete AI workflow
- Project 005 — Structured customer data
- Project 006 — Decision engine

## Status
Recall: 10/10
Build: 10/10
Test: 10/10
Deploy: complete
