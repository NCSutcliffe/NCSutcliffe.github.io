---
title: "Break the work into checkpoints you can review"
description: "Part 5 of Secure by Prompt. Today's reasoning models can plan a big task on their own. Break the work up anyway, but for a different reason than before: so you get a review point before mistakes compound."
date: 2026-12-14 09:00:00 +0000
series: secure-by-prompt
part: 5
tags: [ai, prompting, governance]
image_prompt: "project blueprint with review checkpoints marked, cybersecurity architecture workspace, methodical, DSLR, clean vector overlay with document fragments"
---

The standard advice used to be: never ask an AI for something big in one go. Ask for "a comprehensive incident response plan" and you'd get something generic and shallow, because the model had to plan and write at the same time.

That advice has aged in an interesting way. Current reasoning models handle multi-step work much better. Give one a large task and it will often plan the structure, work through it and check its own output before answering. So should we stop breaking tasks up?

I don't think so. The reason for breaking them up has changed, though.

## The new reason: control, not capability

In security work, the danger in a big one-shot output is that **an early wrong assumption runs through everything after it**. If the model misreads your scope in the first section of an AI usage policy, every later section builds on that mistake, and you discover it at the end after reading 3,000 confident words.

Breaking the work into stages gives you **review points**: places where a human confirms the direction before the next layer is built on it. It's the same reason we have design reviews before build, and change approval before deployment.

## What it looks like in practice

Instead of:

> "Write our AI acceptable use policy."

Run it in stages:

1. "Propose the section structure for an AI acceptable use policy for a UK bank. For each section, give one line on its purpose. Don't write the content yet."
2. *You review: add a section on approved tools, remove one that duplicates the data classification policy.*
3. "Draft the 'Approved tools and data handling' section using the agreed structure. Reference our existing data classification levels: Public, Internal, Confidential, Highly Confidential."
4. *You review, then move on to the next section.*

Each step is small enough to check properly, and each correction is cheap.

## Where to put checkpoints

Not every task needs this. I add checkpoints when:

- **Scope is ambiguous.** Get the outline agreed before the content.
- **Facts feed decisions.** In an investigation, confirm what the evidence shows before asking for conclusions or recommendations.
- **Output will be published or actioned.** Policy text, comms, remediation steps and anything that changes a system.
- **The task crosses domains.** Endpoint, identity and data protection findings are better reviewed separately before you combine them.

For a quick summary or a one-off query, a single prompt is fine. The aim is to have a human check at the points where it matters, not to slow everything down.

## The investigation pattern

For incident work, I've found a three-stage pattern holds up well:

1. **Establish facts:** "From the incident data, list what is known, with the source for each item. Don't interpret yet."
2. **Analyse:** "Based only on the confirmed facts above, what are the plausible explanations? Rank them by the strength of the evidence."
3. **Recommend:** "For the most likely explanation, what containment and remediation steps should we take?"

Keeping fact, interpretation and recommendation separate is good investigative practice anyway. With an AI involved, it also stops the model inventing facts to support a conclusion it has already reached.

## The takeaway

Today's models can manage big tasks on their own; that's no longer the issue. The issue is whether you'll notice when they go wrong, so put the checkpoints where a mistake would be expensive.

*Next: iterating like an editor, and treating the first output as a draft.*
