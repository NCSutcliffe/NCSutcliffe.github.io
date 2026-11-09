---
title: "From one-liner to promptbook: Secure by Prompt in practice"
description: "The Secure by Prompt finale. One phishing incident, taken from a vague one-line prompt to a tested, reusable promptbook, using every technique in the series."
date: 2027-01-11 09:00:00 +0000
series: secure-by-prompt
part: 9
tags: [ai, prompting, security-copilot, phishing]
image_prompt: "security professional reviewing a finished internal communication after a phishing incident, modern office, thoughtful and focused, DSLR, soft lighting with slight vignette"
---

Over eight posts we've covered context, role and audience, the deliverable, examples, checkpoints, iteration, reuse and safety. Here's how they fit together on one realistic job: **writing the staff communication after a phishing incident.**

## The starting point

> "Write something about our phishing attack."

It's vague, has no audience and no format, and quietly invites the model to make up the details. Let's rebuild it.

## Step 1: Choose the tool and minimise the data *(part 8)*

Before writing anything, decide where the work happens. Incident details belong in an approved tool, so in this case we'll use Security Copilot in the Defender portal, where the incident is already in context. The staff email doesn't need the clicker's identity, so we'll refer to them by role only.

## Step 2: Establish the facts from the evidence *(parts 1 and 5)*

> "From incident `<IncidentId>`, list what we know: delivery channel, lure, number of recipients, number of clicks, any credential use and containment actions taken. Cite the alert or record behind each item. Don't interpret yet."

**Checkpoint:** we review the facts. Suppose they show a LinkedIn message impersonating a recruiter with an "urgent CV request". Five staff were targeted. One executive assistant entered credentials, the account was contained within an hour and there's no sign of further access. We confirm these facts before anything gets written.

## Step 3: Set the role, audience and tone *(part 2)*

> "Take the perspective of our security awareness lead. The audience is all staff, with no technical background assumed. Tone: calm and supportive. Educate without alarming, and don't blame the person who clicked."

## Step 4: Define the deliverable and the boundaries *(part 3)*

> "Format: an internal email under 200 words, with a two-sentence summary, three bullet-point actions and a closing line pointing to the phishing awareness module on the intranet. Don't name any individual or third party. Don't speculate about who was behind the attack."

## Step 5: Show the house style *(part 4)*

> "Here's last year's post-incident email, which staff responded well to. Match its structure and tone, not its content."

## Step 6: Iterate *(part 6)*

The first draft is good, but the second bullet mentions "OAuth token theft". We give specific feedback:

> "Rewrite bullet two without technical terms. Focus on what a recruiter message asking you to sign in might look like."

Then a self-review:

> "Check the draft against the brief. Is anything unsupported by the confirmed facts?"

## The consolidated prompt

Here's everything we learned, written as one clean brief rather than a long conversation:

> "Take the perspective of our security awareness lead. Using only the confirmed facts from incident `<IncidentId>`, write an internal email to all staff, assuming no technical background. Under 200 words: a two-sentence summary, three plain-English bullet-point actions and a closing link to the phishing awareness module. Tone: calm and supportive, focused on the attacker's tactics rather than the person who clicked. Follow the structure and tone of the attached example email. Don't name any individual or third party, and don't speculate about attribution. Then review your draft against these instructions and list anything you were unsure about."

## Step 7: Make it reusable *(part 7)*

This is where the series ends up. Phishing comms will be needed again, so we don't leave this prompt in a chat history. We turn the session into a **Security Copilot promptbook**:

1. **Facts:** establish confirmed facts for `<IncidentId>`, with citations.
2. **Checkpoint:** an analyst confirms the facts.
3. **Draft:** generate the staff email using the brief above, with the house-style example as standing knowledge.
4. **Review:** self-critique against the brief.

We give it an owner, test it on two past incidents and share it with the team. The next phishing incident gets a consistent, reviewed, on-brand communication in minutes, and the analyst's time goes into checking it properly.

## Looking back

The techniques in this series aren't tricks. They're the same habits that make anyone good at delegating work: brief clearly, know your audience, define what done looks like, show examples, check work at the right points, give specific feedback, turn what works into a repeatable process and protect the data along the way.

AI hasn't changed what good security communication and analysis look like. It has changed how much of it a small team can produce, and that makes the standards we apply to it more important. That's the whole idea behind *Secure by Prompt*.

*Thanks for following the series. If you're rolling out Security Copilot or building promptbooks for your team, I'd like to hear what's working for you. Find me on [LinkedIn](https://linkedin.com/in/nathan-sutcliffe).*
