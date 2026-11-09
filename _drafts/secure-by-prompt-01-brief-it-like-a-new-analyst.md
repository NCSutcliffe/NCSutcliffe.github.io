---
title: "Brief it like a new analyst: context is the whole job"
description: "Part 1 of Secure by Prompt. Most weak AI output in security comes from weak briefs, not weak models. Here's how to set context and ground the answer in your own evidence."
date: 2026-11-16 09:00:00 +0000
series: secure-by-prompt
part: 1
tags: [ai, prompting, security-copilot]
image_prompt: "security analyst briefing an AI assistant at a desk with incident notes and a laptop, modern operations room, realistic, DSLR, high contrast with slight vignette"
---

*Secure by Prompt is a nine-part series on getting dependable work out of AI in security teams. With Security Copilot now included in Microsoft 365 E5, a lot of security teams have just been handed a capable assistant and very little guidance on how to work with it. This series is my attempt at that guidance: what works, what's changed, and where the risks are.*

---

When a security team tells me "the AI output was useless", I ask to see the prompt. Nine times out of ten it's a single line: *summarise this*, *write a policy for phishing*, *what should we do about this alert?*

The model wasn't the problem. The brief was.

## The junior analyst test

Picture your newest SOC analyst on their second day. You wouldn't hand them a 40-page threat report and say "summarise this". You'd tell them what it is, who it's for, what matters and what to ignore:

> "This is the monthly threat report for UK financial services. I need the three ransomware trends most relevant to us. Skip the geopolitical section; the CISO already has a separate briefing on that."

That's the level of briefing an AI assistant needs as well. It has broad general knowledge but none of yours. It doesn't know your sector, your estate, your risk appetite or what happened last week. Anything you don't tell it, it fills in with the most generic plausible answer. In security, generic and plausible is a dangerous combination.

## What good context covers

A useful brief answers four questions before you ask for anything:

- **What is this?** The type of material and where it came from: "a Defender XDR incident", "last quarter's DLP alert export", "our draft AI usage policy".
- **What's the situation?** The facts that make this case different: "credential phishing via LinkedIn messages up sharply this quarter", "the affected device is a shared kiosk".
- **What does good look like?** The decision or action the output will feed into.
- **What's out of scope?** What to leave out, and why.

Compare these two:

> Weak: "Write a policy section on phishing."

> Strong: "We've seen a rise in credential phishing arriving through LinkedIn messages rather than email, which our email controls don't cover. Draft a staff-facing awareness section that addresses this channel specifically. It will sit in our existing acceptable use policy, so don't repeat general phishing advice."

The second prompt is longer, but it's the only one of the two that produces something you'd actually use.

## Grounding beats instruction

This is the biggest shift since I first drafted this series. Good prompting used to mean describing the situation in more and more detail. Now the better move is usually to **give the model the evidence itself** and tell it to stay within it.

Security Copilot does this natively. When you work inside the Defender portal, the incident, alerts and entities are already in context. In the standalone experience you can upload files as a knowledge base. In general-purpose assistants you can attach the report rather than paraphrasing it.

Then add one instruction that does more for accuracy than any amount of clever phrasing:

> "Base your answer only on the attached incident data. If something isn't in the data, say so rather than inferring it. Cite the alert or log entry behind each finding."

That turns a confident-sounding paragraph into something you can verify. If a finding has no citation, you know where to look harder.

## The takeaway

Before you type the question, spend thirty seconds on the brief. What is it, what's the situation, what's it for, what's out of scope. Then point the model at the evidence and make it show its sources.

The assistant is only as good as the briefing it gets, and writing that briefing is your job.

*Next in the series: role, audience and tone, and why "act as an expert" is the weakest part of most prompts.*
