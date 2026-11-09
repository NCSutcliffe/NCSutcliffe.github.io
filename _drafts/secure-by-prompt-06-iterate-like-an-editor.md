---
title: "Iterate like an editor, not a search engine"
description: "Part 6 of Secure by Prompt. The first response is a draft. The people who get the most from AI give specific, editorial feedback and know when to start again."
date: 2026-12-21 09:00:00 +0000
series: secure-by-prompt
part: 6
tags: [ai, prompting]
image_prompt: "analyst marking up a draft document on screen with comments and revisions, secure operations centre, instructional, wide-angle lens"
---

Most people treat an AI assistant like a search engine: type a query, take the result, move on. When the result is poor, they conclude the tool is poor.

The people I see getting real value treat the first response as a first draft from a capable colleague who's new to the team. Then they edit it.

## Good feedback is specific

"Make it better" gives the model nothing to work with. Editorial feedback does:

> "The second bullet is too technical for this audience. Rewrite it without mentioning tokens or OAuth."

> "You've listed six risks. Keep the three that apply to remote workers and drop the rest."

> "This reads as though the user was careless. Reframe it so the attacker is the focus."

> "Cut this to under 100 words without losing the call to action."

Each round should change one or two things. If you change everything at once, you can't tell which instruction made the difference.

## A typical refinement loop

Here's what a typical loop looks like for an unmanaged-device risk summary:

1. "List the main risks from unmanaged personal devices accessing corporate data in a financial services firm."
2. "Focus on remote and hybrid workers. Add a real-world example for each."
3. "Map each risk to the control that addresses it in our stack: Intune app protection, Conditional Access or Defender for Cloud Apps session controls."
4. "Now summarise as five bullets suitable for the risk section of a policy paper."

By step four the output is specific and usable, and every step was quick.

## Know when to start again

Iteration has a limit. After a long back-and-forth, the conversation fills up with abandoned directions and superseded instructions, and quality starts to drift. The model may hold on to something you told it to drop five turns ago.

When that happens, don't fight it. Take what you've learned about what you actually want and **write a fresh prompt that includes all of it from the start**. The second attempt is usually better than the twentieth revision, and the new prompt is worth saving, because that's how reusable prompts get written (part 7).

## Ask it to review itself

One technique that has become much more effective with current models is asking for a critique before the rewrite:

> "Before revising, review your draft against the brief. What's missing, what's unsupported by the evidence and what would the Board Risk Committee push back on?"

The model is often better at spotting weaknesses in a draft than at avoiding them in the first place. Use that, but make the final call on quality yourself.

## The takeaway

Prompt, review, give specific feedback and repeat, but know when to stop and start again with a better brief. That's how editors work, and an editor is the role you should be playing.

*Next: turning a good prompt into something your whole team can reuse.*
