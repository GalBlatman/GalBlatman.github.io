---
title: "Manufacturing naivety"
description: "A tool I built found a confound in my paper that three expert reviewers had missed. I have been thinking about why."
tags: [reading]
date: 2026-08-20 09:00:00 -0700
---

I ran one of my own manuscripts through the review skill mostly to see whether it would embarrass itself.

It did, a little. It padded a strengths section I had explicitly told it not to pad, got overconfident about citations, and tried to outsource one of the checks back to me.

Then it got to the paper’s first hypothesis.

The paper used year-over-year capital-expenditure growth as a measure of how fast a firm was expanding. The outcome was a gap between two versions of Scope 2 emissions: the location-based number, which reflects the carbon intensity of grid electricity, minus the market-based number, which gives firms credit for renewable-energy certificates and power-purchase agreements.

The skill asked what growth alone would do to those two numbers.

The gap is an absolute quantity, and both components scale with how much electricity a firm buys. A firm that grows, draws more power, and covers the same share of it with certificates as it did last year produces a wider gap while behaving identically. Growth moves the outcome by arithmetic, before any of the paper’s theory gets a turn.

So the gap could widen without the thing I thought I was measuring having moved at all.

My first reaction was that it had misunderstood the variable.

I checked the construction.

It hadn’t.

Three reviewers at a top journal had read that paper. So had my coauthor. So had I, more times than I want to count.

None of us had said it.

## The essay is mostly about stairs

I kept thinking about this because it reminded me of an essay I have liked for years, John Salvatier’s [Reality Has a Surprising Amount of Detail](https://johnsalvatier.org/blog/2017/reality-has-a-surprising-amount-of-detail).

The essay is mostly about stairs.

Salvatier tries to build some. From across the room, a staircase is simple: wood, brackets, screws, angles. Then he gets close. Lumber warps. Screws pull brackets out of position. Walls are not quite square. The staircase keeps decomposing into smaller details, some of which decide whether the thing works at all.

This is familiar to anyone who has tried to make almost anything.

The stranger part comes later. Before you know an important detail exists, Salvatier argues, it is invisible. Learn it well enough and it becomes transparent. You stop noticing yourself accounting for it.

That sounded uncomfortably close to what had just happened to my variable.

I knew exactly how the variable was constructed. I could have explained it if somebody asked.

Nobody asked.

Including me.

## A paper gets simpler as you learn it

At the beginning of a research project, everything is annoyingly literal.

What exactly is in this dataset? Why does this row exist? What does this field record? Why did the data provider classify these two things differently? What has to happen for the mechanism to work? What happens if that assumption fails?

Then you learn the project.

A column becomes institutional pressure. A coding decision becomes the measure. A specification becomes the standard specification. Six inferential steps get compressed into a phrase because you have walked them so many times that walking them again would be absurd.

This is not sloppiness. It is what expertise is for.

Nobody could do research if every familiar assumption had to be reconstructed from scratch each morning. Compression is what lets us think about harder things.

Occasionally, though, the thing you compressed contains the problem.

By the time I ran this paper through the skill, I no longer saw two emissions calculations and an accounting rule. I saw the compliance-performance gap. I knew perfectly well what went into it. That was almost the problem. The name had become easier to see than the machinery underneath it.

I have one case. I do not know why any particular reviewer missed anything.

What I do know is that I had given the skill a peculiar instruction: do not take the paper’s labels for granted.

If the manuscript called something a measure of X, inspect what went into the measure before accepting X. If it claimed A caused B through C, unpack the intermediate steps. If a result supported the theory, ask what else could produce the same result.

The skill was not actually naive.

But I had made naivety procedural.

## Shared expertise has a weird downside

There is an uncomfortable possibility here.

The people best qualified to review a paper usually know the same things the author knows. That is the point. They know which literatures matter, which methods are normal, which assumptions are reasonable, which distinctions have already been fought over, and which ones no longer need three pages of explanation.

But shared expertise may also produce shared transparency.

Sometimes expertise gives you another pair of eyes. Sometimes it gives you another pair that has learned to look through the same thing.

I do not know how common this is. But it is common enough in my own work that I now want a different kind of read alongside the expert one.

I want a reader who can temporarily forget what I mean.

## Manufacturing naivety

“Look for hidden assumptions” is useless advice. If I could see the assumption, it would not be hidden.

Taking things away works better.

First I take away the construct name. If a variable is supposed to measure environmental performance, institutional pressure, organizational commitment, whatever, I try to forbid myself from using those words. What is actually in the column? Who produced it? What had to happen in the world for this observation to become a 7 instead of a 6?

This is tedious. That is partly why it works.

Then I take away the mechanism shorthand.

If X changes Y through A, B, and C, I write the steps out again. Not the nice theoretical version. The embarrassingly literal one. Who observes what? What changes hands? What has to happen first? Which step is in the data, and which one have I simply become accustomed to believing?

And I ask for the stupid explanation.

Not the elegant rival theory. Academics are already very good at elegant rival theories. I mean the boring mechanical thing: a denominator moved. A coding rule changed. Selection put different observations on the two sides. The treatment appears somewhere inside the outcome.

These explanations feel beneath the theoretical conversation right up until they end it.

The last one is easier with another person. I hand the paper to someone with as little project history as possible and ask what it says. What am I claiming? Why should it happen? What does the evidence actually establish?

Then I try not to help.

Sometimes they simply misunderstand the paper. Sometimes the misunderstanding tells me something. Either way, for a few minutes I get access to a version of the project that has not yet become obvious.

None of this needs AI. A coauthor from another area works. A doctoral student works. A seminar audience works. A sufficiently stubborn friend works.

What a machine adds is procedural stubbornness. I can tell it not to accept the name of a construct, and it will unpack something I have explained a hundred times without getting bored or being polite to me.

That is what I now think the review skill is for.

Not a referee. Not an oracle. A reader I can instruct, temporarily, not to know what I mean.

The paper it caught is now headed back out.

Expertise helps us see more.

Sometimes good research requires giving a little of it back.
