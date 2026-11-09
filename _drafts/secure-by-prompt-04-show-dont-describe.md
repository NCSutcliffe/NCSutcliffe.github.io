---
title: "Show, don't describe: the power of one good example"
description: "Part 4 of Secure by Prompt. A single worked example communicates format, depth and house style better than a paragraph of instructions, as long as you know what it will copy."
date: 2026-12-07 09:00:00 +0000
series: secure-by-prompt
part: 4
tags: [ai, prompting, kql, defender-xdr]
image_prompt: "two side-by-side incident summaries on a screen, one used as a template for the other, SOC environment, technical, macro lens, clean interface overlays"
---

You can spend a paragraph explaining the style of incident summary your team likes: concise, timeline first, impact stated plainly, actions with owners. Or you can paste one you're proud of and say "like this".

The second approach wins almost every time. Models are very good at pattern-matching, and an example carries information that's hard to put into instructions: tone, structure, depth, the level of detail in each section and the things you *didn't* include.

## Examples for written outputs

Most security teams already have good examples lying around: last quarter's best incident report, the awareness email that got good feedback, the risk acceptance that sailed through committee.

> "Here's an incident summary our CISO rated highly. Write a summary of the attached incident in the same structure and level of detail. Match the tone; don't copy the content."

If you have time, give two contrasting examples ("one for a high-severity incident, one for a low") so the model learns what changes with severity and what stays fixed.

## Examples for technical outputs

This is where examples earn their keep. When you're generating hunting queries, detection logic or scripts, an example shows the model your conventions: table choices, naming and how you comment.

Security Copilot's [query assistant in advanced hunting](https://learn.microsoft.com/defender-xdr/advanced-hunting-security-copilot-query-assistant) already turns natural-language questions into KQL against the Defender schema. You'll get more consistent results if you show it the pattern you want:

```kql
// Users who clicked a link in a message Defender classified as phishing, last 7 days
UrlClickEvents
| where Timestamp > ago(7d)
| where ActionType == "ClickAllowed"
| join kind=inner (
    EmailEvents
    | where ThreatTypes has "Phish"
    | project NetworkMessageId, Subject, SenderFromAddress
  ) on NetworkMessageId
| summarize Clicks = count() by AccountUpn, Subject, SenderFromAddress
```

> "Using the same structure and commenting style as this query, write one that finds users who signed in from a new country within 24 hours of clicking a phishing link."

Whatever generates the query, read it before you run it, and check the result counts make sense. A query that looks valid but quietly matches the wrong thing is worse than one that fails, because you'll trust the answer.

## The catch: examples are copied faithfully

Examples are powerful because the model takes them seriously, and that cuts both ways. It will copy what you meant it to copy and also what you didn't: the length, the quirks, sometimes the specific details.

A few habits help:

- **Say what to take from the example.** "Match the structure and tone, not the content" stops it recycling your old incident's facts.
- **Strip anything sensitive first.** An example from a real incident can carry names, hostnames or customer details into new output. More on this in part 8.
- **Use more than one example when you can.** With a single example, the model may treat incidental details as the rule. Two or three varied examples show it which parts actually matter.

## The takeaway

If you can't quite explain what good looks like, show it. Keep a small library of your team's best outputs (summaries, emails, queries) and use them as templates. It's the cheapest quality improvement available, and it makes AI output sound like your team rather than like a generic assistant.

*Next: breaking big tasks into checkpoints, and why the reason for doing it has changed.*
