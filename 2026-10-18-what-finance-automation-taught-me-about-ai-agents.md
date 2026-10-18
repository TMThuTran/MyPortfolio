---
title: What eight years of finance automation taught me about AI agents
description: Bots, OCR and implementations taught me five lessons that apply directly to building with AI agents, starting with where automation really fails.
---

When I tell people I'm moving into AI product management, they sometimes ask whether coming from finance and banking automation is a detour. I think it's the opposite. I've spent eight years watching software take over work that people used to do by hand, and most of what I learned applies directly to AI agents. Here are the five lessons I keep coming back to.

## 1. The happy path is the easy part

Every automation project I've worked on, from RPA bots at a Dutch bank to OCR for supplier invoices at Adyen, cleared the routine volume quickly. The hard part was always the exceptions: the document in an unexpected format, the request that didn't fit the rules, the case nobody had written down. That's where the time and the risk sit.

Agents are being pitched at precisely this kind of messy work. That's exciting, and it's also a warning: the demo will look great on the happy path. The product lives or dies on the exceptions.

## 2. Measure the cost of being wrong, not just accuracy

In finance, a wrong answer is often worse than no answer. A wrong invoice match moves money or hides a problem; a case sent back to a person just costs a few minutes. So "95% accurate" means very little until you know what the other 5% does.

For any agent I work on, the first metric I want is the one that captures the expensive mistakes, and I want it treated as a guardrail, not averaged away in an overall score.

## 3. People need to see why

When OCR extracted an amount, finance colleagues trusted it more once they could see where on the invoice it came from. The same is true of agents, only more so. An agent's recommendation should come with its evidence: which documents, which lines, which reasoning. That's what makes review fast, and it's what an auditor will ask for.

## 4. Adoption is a product problem

At Yokoy I ran implementations for 14 clients, including user acceptance testing and training. The product could be excellent and still fail if people didn't understand it or didn't trust it. Users route around tools they don't trust, quietly, and the dashboard won't tell you.

With AI, trust is even more fragile, because the system won't behave the same way every time. Designing how people review, correct and override an agent is not a finishing touch. It's core product work.

## 5. Rule-based automation breaks loudly; agents fail quietly

When an RPA bot hits a screen it doesn't recognise, it stops and throws an error. Annoying, but visible. A language-model agent that meets something unfamiliar will often produce a plausible answer anyway. That's the most important difference between the automation I grew up with and the automation I'm moving into.

It's why I think evaluation is the centre of AI product management: deciding what good looks like, building test sets from real cases, and monitoring for quiet failures after launch. It's also why I've chosen invoice exceptions for my [portfolio project]({{ '/work/agentic-invoice-reconciliation/' | relative_url }}). I know what the failures look like there, and I know what they cost.

---

I'm writing here as I work through AI product management in practice. If you're building agents for finance or operations, I'd like to compare notes: [get in touch]({{ '/about/' | relative_url }}#get-in-touch).
