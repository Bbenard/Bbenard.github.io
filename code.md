
---
layout: post
title: code Simplicty!
---

Resolving code complexity usually requires detailed work at the level of the individual contributor.

If a manager just says “simplify the code!” and leaves it at that, usually nothing happens, because (a) they’re not being specific enough, (b) they don’t necessarily have the knowledge required about each individual piece of code in order to be that specific, and (c) part of understanding the problem is actually going through the process of solving it, and the manager isn’t the person writing the solution.

The higher a manager’s level in the company, the more true this is. When a CTO, Vice President, or Engineering Director gives an instruction like “improve code quality” but doesn’t get much more specific than that, what tends to happen is that a lot of motion occurs in the company but the codebase doesn’t significantly improve.

It’s very tempting, if you’re a software engineering manager, to propose broad, sweeping solutions to problems that affect large areas. The problem with that approach to code complexity is that the problem is usually composed of many different small projects that require detailed work from individual programmers. So, if you try to handle everything with the same broad solution, that solution won’t fit most of the situations that need to be handled. Your attempt at a broad solution will actually backfire, with software engineers feeling like they did a lot of work but didn’t actually produce a maintainable, simple codebase. (This is a common pattern in software management, and it contributes to the mistaken belief that code complexity is inevitable and nothing can be done about it.)

So what can you do as a manager, if you have a complex codebase and want to resolve it? Well, the trick is to get the data from the individual contributors and then work with them to help them resolve the issues. The sequence goes roughly like this:

Ask each member of your team to write down a list of what frustrates them about the code. The symptoms of code complexity are things like emotional reactions to code, confusions about code, feeling like a piece will break if you touch it, difficulties optimizing, etc. So you want the answers to questions like, “Is there a part of the system that makes you nervous when you modify it?” or “Is there some part of the codebase that frustrates you to work with?”
Each individual software engineer should write their own list. I wouldn’t recommend implementing some system for collecting the lists—just have people write down the issues for themselves in whatever way is easiest for them. Give them a few days to write this list; they might think of other things over time.

The list doesn’t just have to be about your own codebase, but can be about any code that the developer has to work with or use.

You’re looking for symptoms at this point, not causes. Developers can be as general or as specific as they want, for this list.

Call a meeting with your team and have each person bring their list and a computer that they can use to access the codebase. The ideal size for a team meeting like this is about six or seven people, so you might want to break things down into sub-teams.
In this meeting you want to go over the lists and get the name of a specific directory, file, class, method, or block of code to associate with each symptom. Even if somebody says something like, “The whole codebase has no unit tests,” then you might say, “Tell me about a specific time that that affected you,” and use the response to that to narrow down what files it’s most important to write unit tests for right away. You also want to be sure that you’re really getting a description of the problem, which might be something more like “It’s difficult to refactor the codebase because I don’t know if I’m breaking other people’s modules.” Then unit tests might be the solution, but you first want to narrow down specifically where the problem lies, as much as possible. (It’s true that almost all code should be unit tested, but if you don’t have any unit tests, you’ll need to start off with some doable task on the subject.)

In general, the idea here is that only code can actually be fixed, so you have to know what piece of code is the problem. It might be true that there’s a broad problem, but that problem can be broken down into specific problems with specific pieces of code that are affected, one by one.

Using the information from the meeting, file a bug describing the problem (not the solution, just the problem!) for each directory, file, class, etc. that was named. A bug could be as simple as “FrobberFactory is hard to understand.”
If a solution was suggested during the meeting, you can note that in the bug, but the bug itself should primarily be about the problem.

Now it’s time to prioritize. The first thing to do is to look at which issues affect the largest number of developers the most severely. Those are high priority issues. Usually this part of prioritization is done by somebody who has a broad view over developers in the team or company. Often, this is a manager.
That said, sometimes issues have an order that they should be resolved in that is not directly related to their severity. For example, Issue X has to be resolved before Issue Y can be resolved, or resolving Issue A would make resolving Issue B easier. This means that Issue A and Issue X should be fixed first even if they’re not as severe as the issues that they block. Often, there’s a chain of issues like this and the trick is to find the issue at the bottom of the stack. Handling this part of prioritization incorrectly is one of the most common and major mistakes in software design. It may seem like a minor detail, but in fact it is critical to the success of efforts to resolve complexity. The essence of good software design in all situations is taking the right actions in the right sequence. Forcing developers to tackle issues out of sequence (without regard for which problems underlie which other problems) will cause code complexity.

This part of prioritization is a technical task that is usually best done by the technical lead of the team. Sometimes this is a manager, but other times it’s a senior software engineer.

Sometimes you don’t really know which issue to tackle first until you’re doing development on one piece of code and you discover that it would be easier to fix a different piece of code first. With that said, if you can determine the ordering up front, it’s good to do so. But if you find that you’d have to get into actually figuring out solutions in order to determine the ordering, just skip it for now.

Whether you do it up front or during development, it’s important that individual programmers do realize when there is an underlying task to tackle before the one they have been assigned. They must be empowered to switch from their current task to the one that actually blocks them. There is a limit to this (for example, rewriting the whole system into another language just to fix one file is not a good use of time) but generally, “finding the issue at the bottom of the stack” is one of the most important tasks a developer has when doing these sorts of cleanups.

Now you assign each bug to an individual contributor. This is a pretty standard managerial process, and while it definitely involves some detailed work and communication, I would imagine that most software engineering managers are already familiar with how to do it.
One tricky piece here is that some of the bugs might be about code that isn’t maintained by your team. In that case you’ll have to work appropriately through the organization to get the appropriate team to take responsibility for the issue. It helps to have buy-in from a manager that you have in common with the other team, higher up the chain, here.

In some organizations, if the other team’s problem is not too complex or detailed, it might also be possible for your team to just make the changes themselves. This is a judgment call that you can make based on what you think is best for overall productivity.

Now that you have all of these bugs filed, you have to figure out when to address them. Generally, the right thing to do is to make sure that developers regularly fix some of the code quality issues that you filed along with their feature work.
If your team makes plans for a period of time like a quarter or six weeks, you should include some of the code cleanups in every plan. The best way to do this is to have developers first do cleanups that would make their specific feature work easier, and then have them do that feature work. Usually this doesn’t even slow down their feature work overall. (That is, if this is done correctly, developers can usually accomplish the same amount of feature work in a quarter that they could even if they weren’t also doing code cleanups, providing evidence that the code cleanups are already improving productivity.)

Don’t stop normal feature development entirely to just work on code quality. Instead, make sure that enough code quality work is being done continuously that the codebase’s quality is always improving overall rather than getting worse over time.

If you do those things, that should get you well on the road to an actually-improving codebase. There’s actually quite a bit to know about this process in general—perhaps enough for another entire book. However, the above plus some common sense and experience should be enough to make major improvements in the quality of your codebase, and perhaps even improve your life as a software engineer or manager, too
