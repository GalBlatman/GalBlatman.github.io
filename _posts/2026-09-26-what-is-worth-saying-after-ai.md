---
title: "What is worth saying after AI?"
description: "A new paper on mathematical discovery made me think differently about an old management question: what separates a paper we can produce from one worth producing?"
tags: [reading]
date: 2026-09-26 09:00:00 -0700
---

I recently read a paper by Niket Patel and colleagues called *Learning to Discover Interesting Mathematics*, and I think management scholars should read it too.[^1]

Nothing in it is about management. It asks what to do now that language models can generate and prove mathematical statements faster than anyone can decide which ones matter.

Their answer starts with a simple idea. A theorem is more interesting when it is relatively easy to state but difficult to prove, given what is already known. They also ask a second question: does having this theorem make later mathematics easier? A useful theorem becomes something later work can simply pick up and use.

The exact measures only work because mathematics gives them things we do not have: formal proofs, verified truth, and a library whose dependencies can be counted. But the problem felt familiar.

In 1971, Murray Davis asked what makes a social-science theory interesting.[^2] His answer was that interesting theories disturb something their audience already believes. If a finding merely confirms the assumption people started with, the response is usually some version of "of course."

What caught me rereading Davis was a passage about computers. He worried that they would make it easy to produce enormous numbers of correlations that were valid but uninteresting. What the human researcher added was a step "between conception and assertion," a filter that screened out propositions that were not worth saying.

He was describing the missing piece fifty-five years early.

Management has spent those years making that filter more demanding. Tihanyi argued that surprising is not enough; the question also has to matter.[^3] Herman Aguinis has turned theoretical contribution into a set of fairly unforgiving questions about what changes, for whom, and why.[^4] The AMJ Research Canvas asks authors to connect the puzzle, audience, research question, theory, design, findings, contribution, and limitations into one coherent project.[^5]

I use guidance like this because it makes vague claims about "contribution" much harder to hide behind. I have also built AI tools that apply some of these checks to manuscripts, which is how I know how good models have become at producing the visible form of a strong paper. [I wrote about one of them here](https://galblatman.com/blog/teaching-claude-to-review-like-an-editor/).

An LLM can suggest a puzzle, find a tension in a literature, generate constructs, propose mechanisms and hypotheses, recommend analyses, draft a contribution, and make the whole thing read smoothly. That is genuinely useful, but it can also produce something that looks much more interesting than the idea underneath it.

Reading Patel et al. gave me three questions I now like asking about management papers.

The first is: how far does the claim move the reader from what they already believed?

This is my closest translation of "hard to prove." A finding does more intellectual work when the destination was not already visible from the starting point. That is close to Davis's idea too: interestingness depends on what the audience thought before the paper arrived.

The second is: how much do I have to teach the reader before they can understand the claim?

This is my version of statement length. New constructs and distinctions are sometimes necessary. But they impose a cost. If a paper needs pages of new vocabulary to deliver a fairly modest claim, the machinery may be doing more work than the idea.

I have seen this in my own writing. Over one summer, the title of my job-market paper moved from *Governance Mode as a Structural Response to Institutional Complexity* to *To Partner or Go Alone*. The paper itself had become more complicated, not less. But the claim had become clearer. I needed fewer words to say what the reader was supposed to learn.

The third question is: what becomes easier for the next researcher because this paper exists?

Patel et al. call this utility. In their setting, a useful theorem shortens later proofs because future mathematicians can use it as a premise. I like the management version of that question: who is going to pick this idea up, and what will they no longer have to establish because this paper already did the work?

That feels more concrete to me than saying a paper "extends" or "enriches" a literature.

The analogy also breaks in useful ways. A mathematical theorem can be checked before anyone asks whether it is interesting. We do not get that luxury. A management result that moves the reader a very long distance may be profound, or it may simply be wrong.

Difficulty is slippery too. My own job-market paper took years of deal-level data to assemble. That made it hard to do. I have learned not to mistake that for the idea being deep.

And some of the best work is expensive to explain because it connects literatures that did not previously speak to one another. New vocabulary can be the price of building a bridge rather than evidence that the argument is inflated. Patel et al. acknowledge a related limit in their own measure: it does not fully capture results that connect previously unrelated objects or unify different areas.[^1]

So I would not turn any of this into a score. I read the paper as a way of sharpening an old question.

AI has made it much cheaper to generate things that have the form of research. There are now more plausible questions to choose from, more possible mechanisms, more ways to frame a finding, and more polished ways to describe a contribution. That makes Davis's filter more important, not less.

That is why I am recommending Patel et al. to people who do not work in mathematics. The paper is ostensibly about teaching machines to choose worthwhile theorems. I read it as a useful prompt for thinking about how we choose worthwhile papers.

Eventually, a model can help you make almost every part of a paper look coherent.

Then you have to walk into a room full of smart people and explain why the idea was worth saying.

### Endnotes

[^1]: Niket Patel, Ahmad Rammal, Amaury Hayat, Remi Munos, and Julia Kempe, "Learning to Discover Interesting Mathematics" (2026). The paper defines interestingness using proof difficulty relative to description length, examines downstream utility, and explicitly notes that its measure does not fully capture results that connect previously unrelated objects or unify areas. [arXiv:2609.28603](https://arxiv.org/abs/2609.28603).

[^2]: Murray S. Davis, "That's Interesting! Towards a Phenomenology of Sociology and a Sociology of Phenomenology," *Philosophy of the Social Sciences* 1 (1971): 309–344. Davis argues that interesting theories challenge assumptions held by their intended audience and describes the human filter between producing a proposition and deciding it is worth asserting. [Article](https://journals.sagepub.com/doi/10.1177/004839317100100211).

[^3]: Laszlo Tihanyi, "From 'That's Interesting' to 'That's Important'," *Academy of Management Journal* 63 (2020): 329–331. [https://doi.org/10.5465/amj.2020.4002](https://doi.org/10.5465/amj.2020.4002).

[^4]: Herman Aguinis, "Theory Contribution Builder." [Theory Contribution Builder](https://www.hermanaguinis.com/theorycontribution.html).

[^5]: Sinziana Dorobantu, Marc Gruber, Davide Ravasi, and Ned Wellman, "The AMJ Management Research Canvas: A Tool for Conducting and Reporting Empirical Research," *Academy of Management Journal* 67 (2024): 1163–1174. [https://doi.org/10.5465/amj.2024.4005](https://doi.org/10.5465/amj.2024.4005).
