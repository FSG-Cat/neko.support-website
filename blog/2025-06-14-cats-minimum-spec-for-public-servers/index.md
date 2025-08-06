---
slug: 2025-06-14/cats-minimum-spec-for-public-servers
title: Cats Minimum Specification for Public Servers
authors: [cat]
tags: [cat, t&s, matrix, sys_admin]
---

Hosting a public matrix homeserver in 2025 is a lot more complicated than just enabling some form of registration in your homeserver software of choice.

Without the right combination of homeserver software and external tooling in place it’s currently not realistic to provide a good safe user experience out in the open federation if you’re under attack.

This post will go into my recommendations for how to solve this concern. As in what tooling and what software are your options and a tiny bit about getting access to them.

<!-- truncate -->

## What to not use and why?

Currently as of today if you’re not using Synapse, I am sorry but you are screwed. If you’re using Continuwuity then your lucky as I have seen Nex work on trying to fix the shortcomings that block it from being considered acceptable.

Also, if you are using Synapse that is hosted by Element Matrix Services your also hamboned. It is simply not configured for this use case.

So why is your only option today, Synapse? Its because [synapse-http-antispam](https://github.com/maunium/synapse-http-antispam) exists and has no comparable options. The synapse-http-antispam module is simply so good that there are no credible alternatives currently. And well this is Synapse only.

And well what about Mjolnir. Considering my role within the Draupnir project I’m not going to go into detail on this. It would be rude and not professional. So, lets summarise it as Mjolnir’s Module is questionable in when it wants to work at least when I used it and Mjolnir its self doesn’t yet have invite filtering or suspend on policy. The module is also just likely to ripped out and replaced with http antispam.

## What to use?

The minimum viable sbom for a matrix homeserver stack that meets Cats T&S Requirements today and you actually would want to use. So, no dbeaver required to even operate the thing bullshit is the following list.

* Synapse
* [synapse-http-antispam](https://github.com/maunium/synapse-http-antispam)
* Draupnir or Meowlnir
* [Synapse Admin etke.cc fork](https://github.com/etkecc/synapse-admin)
* ./well-known/matrix/support

Yes, the list is actually that short. You only rly need for the absolute minimum viable to not be a total shitshow of a matrix homeserver a good moderation bot and the module plus a good admin interface.

## How to use this?

This won’t be too detailed of a guide on this its more of a what to do with these tools high level overview.

### Synapse

So, in synapse ofc enable captchas and email verification. I know I know I hate captchas as much as everyone else. If you want to go very secure go and do reg enabled and requires registration token.

The magic in registration tokens is that you can either manually issue them or use whatever anti bot measure you want to protect a page that generates them via the admin API with extremely short validity times and single use. Point is they allow you full control and you don’t need some Auth provider setup for OAuth or MAS.

Ofc enable admin API access for your moderation bot and so you can use the admin API frontend of your choosing. How to do this is up to the reader.

### synapse-http-antispam

You simply just hook up antispam to your bot and enable the callbacks that are asked for by your bot and well your ready to go on this side.

### Draupnir or Meowlnir

Make your bot follow a policy list of your liking preferably CME and enable the bot’s version of suspend on policy. Then also enable invite filtering and room takedowns.

The details of how all this is achieved are well in your bot documentation I would hope. I know Draupnir docs have all this covered as we care extensively about this topic over in The Draupnir Project.

Also Report Hijacking is a good idea to probably have enabled so you can get easy access to reports from users. Alternatively leave this task to your admin API frontend.

### Synapse Admin

So, what purpose does Synapse admin serve in all this mess. Easy visual management of a lot of aspects of your homeserver including the disabling of rate limits, Reading of reports, User management, Reg token management and more.

Essentially, it’s your Swiss army knife meant to help you with your admin needs. Not much more needs to be said.

### ./well-known/matrix/support

This is where information like admin contact information and homeserver moderation contact information can be found. Pretty essential and admin communities will use this to validate if you belong in the room at all.

## Summary

The bare basics of how to run a public matrix homeserver in a somewhat decent manner aren’t that complicated it turns out. And what’s most funny is that mdad provides all of this in a nice package ready to go.

Now if you want to take this the extra mile there’s always a lot more things you can do and should do. For example, if your very adventurous and like to live a bit dangerously you can host D4A and help out making it more stable. D4A is not perfectly stable and is currently only run by people with a relationship with The Draupnir Project to my knowledge. And only 2 total deployments exist that I know of. And I host one of them.
