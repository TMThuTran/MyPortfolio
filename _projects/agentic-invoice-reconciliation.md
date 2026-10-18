---
title: An agent for the invoice exceptions nobody wants to handle
description: A product case for using an AI agent on the hardest part of invoice reconciliation, the exceptions, with evaluation designed in from day one.
order: 1
period: 2026
org: Side project
role: Product owner, from problem framing to evaluation design
status: In progress
tile: green
visual: recon
---

This is my current portfolio project. I'm writing it up while it's in the requirements phase, because the framing decisions are the part of product work that's usually invisible, and they matter most.
<!-- Update this page as the project moves forward: add what you build, what you test, and what changed your mind. -->

## The problem

Reconciliation means checking that an invoice, the purchase order behind it, the goods receipt and the payment all agree. When they do, rules and existing automation handle it well. When they don't, because of a partial delivery, a price change, a credit note, a typo in a reference, or a supplier who merged two invoices, a person has to investigate: open the documents, compare line by line, email the supplier or the buyer, and decide.

I worked on the happy path of this process for years, with OCR at Adyen and robotic process automation before that. The pattern was always the same: automation clears the easy volume, and the exception queue is where the time, the frustration and the risk end up.

## Why an agent, and why now

Rule-based automation breaks when the world doesn't match the rules. An exception investigation is a short chain of judgement calls: which documents matter, what's different, what's the likely reason, and what should happen next. That's the kind of multi-step work current language-model agents can attempt, as long as they can show their working.

## Who it's for

- **Accounts payable specialists**, who work the exception queue every day and need fewer, better-prepared cases.
- **Finance controllers**, who are accountable for what gets booked and need an audit trail they can defend.

## What the first version does

1. Picks up an unmatched invoice and gathers the related documents.
2. Identifies the discrepancy and proposes the most likely explanation, citing the exact lines it relied on.
3. Recommends an action (match, partial match, request a credit note, ask the supplier) and drafts any message needed.
4. Hands everything to a person who approves, edits or rejects it. **Nothing is booked without a human decision.**

Out of scope for now: posting entries automatically, paying invoices, and anything that changes supplier master data.

## How I'll know it works

In finance, a wrong match is worse than no match: it moves money or hides a problem. So the evaluation starts from the cost of being wrong, not from overall accuracy.

- **Guardrail:** the rate of incorrect recommendations that a reviewer approves. This has to be close to zero before anything else matters.
- **Quality:** how often the agent's explanation matches what an experienced specialist concludes, measured on a labelled set of real exception types.
- **Usefulness:** the share of cases a reviewer accepts with no or minor edits, and the time it takes to resolve a case compared with today.
- **Honesty:** how often the agent says it isn't sure when it shouldn't be sure. Sending a case back with "I couldn't determine this" is a valid, measurable outcome.

## Risks I'm designing around

- **Confident but wrong explanations.** Every claim has to point to a source document, and reviewers see the evidence next to the recommendation.
- **Audit and control.** Finance teams need to show who decided what. The agent recommends; a named person approves.
- **Data protection.** Supplier and payment data is sensitive, which shapes where models can run and what they can see.
- **Adoption.** From implementation work I know that a tool people don't trust is a tool people work around. Early users help define what "good enough to trust" means.

## Next steps

- Collect and label a realistic set of exception cases.
- Define the first evaluation set and a baseline: how well do rules alone do?
- Build a thin prototype of the review screen before building the agent, to test what reviewers need to see.
