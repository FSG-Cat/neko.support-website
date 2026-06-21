---
slug: 2026-06-21/eternal-september-and-what-countermeasures-are-needed-to-not-drown
title: Eternal September and what counter measures are needed to not drown
authors: [cat]
tags: [cat, t&s]
---

The Matrix community, as far as I see it, is in quite grave danger because it's September, and if we don't stop this bleeding it's going to be, well, Eternal September.

So in this blog post, I talk about the countermeasures to make sure the Matrix community has a chance at not drowning and killing the viability of the protocol in the process for our purposes.

<!-- truncate -->

## What is Eternal September for Matrix?

Eternal September is popularly in this context referring to the mass influx of new users in a bad way, and it's the way I mean it too. If nobody notices that you're a totally new user in a negative connotation, you're not the problem as far as this post is concerned. It is important to remember that new users are essential to the growth of Matrix, and not a threat. They bring valuable new perspectives and could become key contributors to the protocol's future. We need them to thrive, which means we need to guide their onboarding properly. Improper onboarding turns this potential boon for Matrix into the very curse this blog post is trying to avert.

The original Eternal September event is described by Wikipedia as being an overload event on the custodial moderation front, as far as I see it. And it's what is going to happen to Matrix too. We see it all over the place all these new users who have not a faintest clue how to behave. They go, "new app, what this?" and they don't read descriptions or anything, and don't even know where they landed. Can we really blame them? The application design is not exactly the best at all times in guiding them, and we have no flows designed to force them into an onboarding pipeline. Great for spinning up alts for us established users, but not so good for newcomers.

So yes, I'm not blaming these new users completely; we are failing them, it is fair to say. We can do better, and the saddest part is that these are not new ideas. Gnuxie, my fellow Draupnir maintainer, has for at least a few years been thinking about solutions to this problem and writing about them. While Gnuxie has been writing about them on her blog, I have mostly kept it on Matrix and inside of MSCs. I came to Matrix from Discord, and I had already gotten experience in these matters, having been involved in community operations on that side in the past. I know it's hard to design onboarding. It does not help that users are from a wide variety of backgrounds, and you will rarely be blessed with highly educated users who can be treated like children and not be offended due to their education being in this exact problem. Just like how security experts are happier to deal with extreme security measures if they are genuinely justified according to them, T&S experts are happier to go through flows designed for children even though we are not, because we know it's sadly required if we want them to work for everyone.

## What can we do to protect ourselves?

There are several types of countermeasures that we can use, and there are surely going to be more of them than I will talk about in detail. But at least I'm going to talk about some of them here.

### Membership Screening: MSC4106 or derivative

Membership screening is not a new idea; hell, Cat worked with this stuff on Discord back in 2017 or something back in my Warframe days. While I don't know how old this idea is and these implementation concepts, I know it was known about back in those days, and this is almost a decade ago history.

So how would membership screening work in Matrix? The current working idea is actually to move away from membership based as that will take too much time, and do it via Policy Server enforcement. That's our first hurdle, but after that is passed, how does the screening part work? Well, the screening bot would contact the user and follow an automated script, and then take actions based on its configuration.

Gnuxie has written about ideas for how this can work with participation score and other ideas for scoring people and reputation systems. These ideas can easily be integrated into membership screening to give high reputation users automatic access.

For example, I don't need to have Gnuxie be manually approved for joining the Draupnir Develop room when it was created, because my bot should of course know who she is and why she's allowed to join. But if Alice wants to join well sorry but I don't know Alice, so full screening with either a captcha or manual approval is needed.

### MOTDs and forced reading of welcome messages

This is actually related to membership screening, but more the part that would be more visible to the new users. After all, you may be automatically screened and determined to not be a known threat, but that alone may not grant you access. But this feature can also be implemented by clients without membership screening being enforced.

This change can also help reverse the trend that users have not a clue where they are.

### More custodial moderation interventions and capacity

More custodial moderation is going to be needed by a lot of these communities to deal with these new users, because the ones who are here and want to integrate will need help, and they are so worth it if we want to grow. The problem is how hard it is going to be to filter out all the chaff from the quality users. Especially in an age of machines deluded into "thinking" and rising levels of polarization.

## Closing words

This problem is hard to solve, and it's especially hard for some of us to solve it because we have been banging our heads against the wall for years trying to solve it but got nowhere. The resources didn't exist or were allocated to different areas, and I think it's time for us to at least temporarily re evaluate where resources are going.

We need countermeasures soon or we are screwed if this wave continues. More rooms will abandon being present in the matrix.org room directory, as being there is the same as slowly drowning without these tools in place if your custodial teams are not up for the task.

If this was just another wave of CSAM or spam or whatever janitorial problem, I would not be worried; it's just another Tuesday. Yes, we might burn out some of my colleagues, which is the highest risk, but it's not existential. We as a community have janitorial needs covered for each other. But this is a custodial problem, and we don't have custodial moderation workload sharing agreements with enforcement power the same way we do with janitorial. And these new users sometimes need to just be put in their place by someone with enforcement power.
