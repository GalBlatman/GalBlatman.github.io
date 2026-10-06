---
title: "A prompt for judging a research idea"
description: "I built a workbench to criticize research ideas, tested it against one good prompt, and kept the prompt."
tags: [tools]
date: 2026-10-06 09:00:00 -0700
---

I made a prompt file that gives a research idea a tough pre-submission read. It separates "missing" from "wrong," tells you what is worth protecting, names the main problem, and gives you the next piece of work most likely to change the verdict. [Get it here](https://github.com/GalBlatman/Research-Development-Workbench/blob/main/docs/tools/Baseline_Plus_Research_Review_Prompt_v1.md). One Markdown file, nothing to install.

Here is how it came to exist.

My [last post](/blog/what-is-worth-saying-after-ai/) argued that once generating results is cheap, the hard part is telling which ones are worth anything. That left the obvious question: how do I tell? I had a folder of editorials on what makes a paper interesting, what counts as a contribution, how to design a study, how to review one. I had my own habits from writing and reviewing papers. I also knew my reactions are biased in ways I cannot see from the inside. So I tried to build something that would judge an idea without my thumb on the scale.

My first instinct was to build a workbench: an app you plug a research idea into, and it helps you criticize and develop it. It starts by asking what kind of contribution you are making, because a descriptive paper should not be graded like a theory paper. For papers that explain something, it runs ten checks, from whether the puzzle matters and whether the explanation explains anything, to what would tell your account apart from the obvious alternatives, whether the measures measure what they say, and whether the setting gives you enough to test it with. It also holds a few lines that models like to blur: missing evidence is not bad evidence, a claim nobody checked is not a false one, and sometimes the right answer is that there is not enough here to judge yet.

Then I tested it. I took 50 recent quantitative papers from AMJ, ASQ, Management Science, Organization Science, and SMJ, broke each into its parts, and made damaged versions: a mechanism removed, a rival explanation swapped for a weak one, measures weakened, claims stretched past the evidence. I showed the workbench these versions without telling it what I had changed, scoring it on whether it noticed the changes I made, left unrelated judgments alone, and withheld judgment when the evidence was missing. Then I ran the same development and validation cases, on the same model, `gpt-6-sol`, through one good prompt. Not a weak one on purpose. The best simple version I could write.

The app didn't win. On the validation papers it was a little better at refusing to make unsupported calls, but not by enough to distinguish it clearly from the prompt. It also cost about twice as much, took almost twice as long, and failed to return a usable answer more often. The full test, both systems, and the results are [in the repo](https://github.com/GalBlatman/Research-Development-Workbench/blob/main/docs/tasks/STEP-14-validation-report.md), so anyone who suspects I handicapped the baseline can read it.

So I turned the exercise into a prompt. It is cheaper and faster, anyone can paste it into a chat, and building the larger version had already told me which parts were actually doing the work: a good rubric, permission to say "I cannot tell," a fixed output format, and a few hard stops for things we already know are invalid. The prompt keeps those and drops everything else.

One caveat: the evaluation tested the rules that went into this prompt, not this exact Markdown file. The file is new. I am going to use it on my own ideas and see where it breaks. If it gives you a good read, or does something dumb, tell me.
