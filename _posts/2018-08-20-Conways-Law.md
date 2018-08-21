---
layout: post
title: "Conway's Law"
date: 2018-08-20
---
I have an odd fascination with how organizations run. I obsess over org-charts, and want to know what the role and purpose of each person I'm in a meeting with is. I care probably a bit to much about communication and team structure. This behavior probably isn't healthy, and it probably makes me come off as a jerk. 

As of late I find myself having increasingly more conversations (and sometimes arguments) about team structure with co-workers. Even though I'm a developer at heart, this topic still really fires me up. I decided to write a blog post to talk about how this obsession intersects with software development. I want to talk about Conway's Law.

# Definition
In a 1967 paper Melvin Conway wrote what he summarized as the following: 
> Any organization that designs a system (defined broadly) will produce a design whose structure is a copy of the organization's communication structure.

Conway suggests that the reason for this is that one of the initial tasks a company does when building software of any size is to first identify the teams that work on said software. Those teams are then broken into sub-teams, those teams into sub-sub-teams and so on until a reasonable separation of duty is achieved. 

This is not unlike how software developers break up their code. Although, [experienced developers typically have a process they follow](https://en.wikipedia.org/wiki/SOLID).

Conway then suggests that when these sub-teams design, either the systems they design interact with another sub-team's design or they don't. If they do, then obviously the teams must have communicated in some fashion in order for them to interact. Therefore the teams communication structure mimics that of the software they wrote and vice-versa.

Put bluntly: If two teams are required to produce stuff that must interact with each other, the quality of that interaction directly mirrors the quality of the teams communication. If you have two teams who suck at communicating, guess what? The software they write together will suck too. 

You can read the [whole paper here](http://www.melconway.com/research/committees.html) or a summarization he [posted here](http://www.melconway.com/Home/Conways_Law.html)

# Some Examples
## Dev-Ops
I feel like Dev-Ops really strikes at the heart of Conway's argument here. Traditionally developers and IT have not gotten along well, and I'm not entirely sure why that is. They both _usually_ have the same goals: Deliver a solution that solves the problem, solves it correctly, and does it in an efficient and reliable way. I think things start to break down when it comes to separating who is suppose to deliver what. Or more specifically, they seem to think that they're responsible for different parts of it.

While Dev-Ops original goals were to specifically _"reduce the time between committing a change to a system and the change being placed into normal production"_ the result I feel was a bit more than that. In order to achieve this, teams needed to work closer with their IT counterparts to ensure code is delivered quickly and consistently. Organizations did this by [literally merging their "Dev" and their "Ops" teams together.](https://stories.visualstudio.com/devops/)

In a Dev-Ops world, no longer are developers allowed to throw code over the wall and just let Ops deal with it. No longer are developers left questioning "Did this actually deploy right?" Both are asked to be responsible for what is delivered, how it's delivered and how fast it can get there. Their communication needed to improve, and by doing so, so did the quality.

## Agile Software Development
Let's start by listing the core values listed in the agile manifest:
- Individuals and Interactions over processes and tools
- Working Software over comprehensive documentation
- Customer Collaboration over contract negotiation
- Responding to Change over following a plan

Right there in the values, the very first bullet point you have _"Individuals and Interactions"_. By structuring your entire development process from how you structure your teams to how you work each day around individuals and interactions, according to Conway, you're focusing on your software design.

I've typically seen agile development as a way to organize a team and structure it's interactions. When you take into account Conway's law, what agile development is really about is how you design your software. 

# Wrap-Up
I feel like an important distinction to make here is that Conway's law isn't really about how team's should be structured. It's more about the sociology behind why teams function they do.

Sometimes we look inside a large organization at a dis-functional team, or a failed project and ask _"How on earth did it get this bad?"_ Thinking about Conway's law really helps us find where things broke down. 

_Maybe if the ops team and the dev team had the same managers they would've communicated more._

_Maybe if there was a separate team for handling core functionality each team wouldn't have tried to create their own frameworks._

_Maybe if there was a core team focusing on analytics for the product, they would've produced consistent metrics._
