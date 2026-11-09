---
title: "Role, audience and tone: who's writing, and who's reading"
description: "Part 2 of Secure by Prompt. 'Act as an expert' is the most overrated line in prompting. Naming the reader and the register is what actually changes the output."
date: 2026-11-23 09:00:00 +0000
series: secure-by-prompt
part: 2
tags: [ai, prompting, communication]
image_prompt: "security lead presenting a one-page briefing to a board risk committee, glass boardroom, professional, mirrorless camera, soft background blur"
---

Nearly every prompting guide tells you to start with a persona: *"You are a senior cybersecurity expert…"* I used to recommend it too. I've changed my mind about why it matters.

## What the research says about personas

A [2024 study](https://arxiv.org/abs/2311.10054v2) tested personas across a large set of factual questions and found that adding a role to the system prompt didn't improve accuracy compared with no persona at all. The model doesn't know more because you've called it an expert. Telling it it's a CISSP doesn't give it a CISSP's knowledge.

What a role *does* change is framing: what the model treats as relevant, how deep it goes and which vocabulary it reaches for. That's useful, but it's the smallest of three levers. The other two are the reader and the register, and they do more.

## Lever 1: the role, used for framing

Use a role when you need the output to have a particular perspective or priorities:

> "Review this Conditional Access design as a risk manager would: focus on business impact and residual risk, not configuration detail."

That's more useful than "you are a risk manager" because it says what the role changes about the answer.

## Lever 2: the audience, the lever people forget

Security content written for everyone ends up working for no one. The same DLP incident needs to read completely differently for a board risk committee, a service desk and the data protection officer.

Name the reader, and say what they need from it:

> "Write this for the Board Risk Committee. They need to know the business impact, whether customer data was involved and what decision, if any, they need to make. They don't need the technical chain of events."

> "Rewrite this for the service desk. They need to recognise the symptoms on a user's call and know exactly when to escalate."

In my experience, naming the audience fixes more bad output than any other single change. It sets the vocabulary, the depth and the focus at once.

## Lever 3: tone, the lever that protects trust

In security communication, tone is part of the control. A post-incident email that sounds alarming creates panic and floods the service desk. One that sounds casual reads as if the team isn't taking it seriously. A regulator notification that sounds defensive invites scrutiny.

Be explicit about it:

- "Calm and supportive. Educate without alarming, and don't blame the user who clicked."
- "Formal and precise, suitable for a regulatory notification. No speculation."
- "Direct and action-first. This is a SOC escalation note, not a narrative."

## Putting the three together

> Weak: "You are a cybersecurity expert. Explain this phishing incident."

> Strong: "Take the perspective of our security awareness lead. Explain this phishing incident to all staff, assuming no technical background. Keep the tone calm and supportive, and focus on what they should do differently, not on what went wrong."

The first prompt only gives the model a job title. The second tells it who the message is for and what it has to achieve.

## The takeaway

Keep the role if it sharpens the perspective, but don't expect it to make the answer more accurate. Spend your effort on the reader and the register. Those decide whether the output gets used or gets rewritten.

*Next: defining the deliverable, covering format, length and the boundaries you need it to respect.*
