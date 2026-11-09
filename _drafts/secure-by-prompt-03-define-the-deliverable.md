---
title: "Define the deliverable: format, length and boundaries"
description: "Part 3 of Secure by Prompt. If you don't specify the shape of the answer and the lines it mustn't cross, you'll spend longer fixing the output than it took to generate."
date: 2026-11-30 09:00:00 +0000
series: secure-by-prompt
part: 3
tags: [ai, prompting, governance]
image_prompt: "structured risk table on a large monitor in a dark operations room, modern, macro lens, subtle blue highlights"
---

Security teams don't have time to mine a wall of prose for the three things they needed. Yet most prompts leave the most important part of the request out: what the finished thing should look like, and what it mustn't contain.

I think of this as writing the acceptance criteria for the output, the same way a good product owner writes them for a user story.

## Specify the shape

Say what format you need and how long it should be:

> "Return a table of the top five insider risk scenarios for a retail bank, with columns for scenario, likelihood, impact and primary control."

> "Turn this policy into a ten-item checklist an Intune administrator can work through before a rollout."

> "200 words maximum, as an email with a one-line summary, three bullet actions and a closing line."

Length matters more than people expect. Models default to thorough, and thorough usually means long. A word limit makes the model prioritise, which is often the part of the job you actually wanted done.

If the output is heading into another tool, such as a ticket, a report template or a spreadsheet, describe that destination. "Format as a Markdown table I can paste into our Confluence risk register" saves a round of reformatting.

## Set the boundaries

The other half of the specification is what to leave out. In security work this is often more important than what to include, because the cost of a wrong inclusion is real: a vendor named in a breach note, an employee identified in all-staff comms, speculation stated as fact in a regulator update.

Make the boundaries explicit:

> "Don't name the affected employee or the third-party supplier."

> "Cover endpoint controls only. Identity and network are handled in separate sections."

> "Don't speculate on attribution. If the evidence doesn't establish it, say it's under investigation."

> "Use our approved terminology: 'security monitoring', not 'surveillance'."

Two tips make boundaries work better:

1. **Give the reason.** "Don't name the supplier; we're still in contractual discussions" works better than a bare rule. The model applies the principle to cases you didn't list.
2. **Phrase it positively where you can.** "Write in plain English" tends to land better than a long list of banned jargon.

## A worked example

> Weak: "Summarise this audit report."

> Strong: "Summarise this internal audit report on endpoint patching for the CIO. Format: a three-sentence overview, then a table of findings with columns for finding, risk rating, owner and due date. Maximum 250 words outside the table. Don't include the auditor's methodology section, and don't soften the risk ratings. Report them exactly as the audit states them."

The second version produces a summary someone can act on.

## The takeaway

Before you send a prompt, ask yourself what the finished thing looks like and what it mustn't contain. If you can't answer both, the model will answer them for you, and it will usually choose verbose and unconstrained.

*Next: showing rather than describing, and why one good example beats a paragraph of instructions.*
