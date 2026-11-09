---
title: "From prompt to promptbook: make good prompting reusable"
description: "Part 7 of Secure by Prompt. The 'perfect mega prompt' is the wrong goal. The real gain comes from turning what works into custom instructions, promptbooks and agents your whole team can use."
date: 2026-12-28 09:00:00 +0000
series: secure-by-prompt
part: 7
tags: [ai, prompting, security-copilot, promptbooks, agents]
image_prompt: "library of reusable investigation playbooks displayed as cards on a screen, security operations team in background, modern, DSLR, cinematic lighting"
---

When I first wrote about prompting, the end goal was the "mega prompt": one carefully layered instruction with role, context, format, audience, tone and constraints all in a single paragraph. It works. But I now think it's the wrong goal.

A mega prompt lives in one person's head, or in a note on their laptop. Every analyst writes their own version, quality varies from person to person, and when a good analyst leaves, their prompts leave too.

The industry has started calling the alternative **context engineering**: instead of perfecting individual prompts, you design what the model always knows and the workflows it follows. For a security team, that means making good prompting reusable.

## Three levels of reuse

**1. Standing context: custom instructions and knowledge.** Most assistants now let you set persistent instructions and attach reference material: your terminology, your data classification scheme, your house style for reports. You set it once and every prompt benefits. Most of the context from part 1 belongs here rather than being retyped each time.

**2. Repeatable workflows: promptbooks.** Security Copilot's [promptbooks](https://learn.microsoft.com/copilot/security/build-promptbooks) are sequences of prompts that run in order, each building on the last. You can build one from a session that worked, replace the specifics with inputs such as `<IncidentId>` or `<UserPrincipalName>`, and share it across your organisation.

This is where parts 3 to 6 of this series pay off: the deliverable definition, the examples and the checkpoint structure get captured once and used by everyone.

**3. Delegated work: agents.** The next step is agents that carry out a defined job with less prompting. Microsoft has [announced more than a dozen Security Copilot agents](https://learn.microsoft.com/copilot/security/security-copilot-inclusion) across Defender, Entra, Intune and Purview, covering scenarios such as phishing triage, Conditional Access optimisation and sensitive data discovery. In Microsoft 365 E5 and E7 they come with a monthly usage allowance. They aren't switched on automatically, though; someone has to decide where they fit.

## The product owner's view

This is where my day job comes in. A promptbook or an agent is a product. It has users, a job to do, acceptance criteria and a lifecycle. Treat it that way:

- **Start from a real, repeated task.** The best candidates are things analysts do weekly in a consistent way: phishing triage, user risk summaries, device investigations.
- **Define what good looks like** before you build. What should the output contain, and how will you know it's right?
- **Test against real cases**, including awkward ones, before you share it.
- **Name an owner.** Models, data sources and your environment all change, and a promptbook that worked in March can quietly degrade by September.
- **Watch the cost.** In Security Copilot, promptbooks and agents consume compute units. A badly scoped promptbook that runs on every incident costs real money.

## What doesn't change

Reuse doesn't remove the need for judgement. A shared promptbook spreads your best practice, and it spreads your mistakes just as widely. Review the output critically, especially when a workflow is new. The goal is to free analysts from repeating the same routine work, not to stop them thinking.

## The takeaway

Stop trying to write the perfect prompt. Write a good one, prove it works and then make it something your whole team can use. That's how individual skill becomes a team capability.

*Next: the part most prompting guides leave out, which is prompting safely.*
