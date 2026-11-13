---
title: "The pauses were part of the method"
description: "AI made my research faster, and the speed created problems of its own. Notes on what went wrong, what I changed, and the skills I built for Claude and ChatGPT."
tags: [tools]
date: 2026-11-12 17:00:00 -0800
---

I've been using AI for different parts of my research for a while now. It makes my life much easier, especially when it comes to collecting data, writing code, and checking analyses. But I've also learned that making research faster creates some problems of its own.

I recently started three research projects, all with different coauthors. I came into each with a research question and an initial theoretical argument. My job was to work out what evidence I needed, which comparisons could distinguish my explanation from the alternatives, and whether the available data could support the study.

I used AI to help with the work. Coding agents helped collect and organize records, write scripts, and run checks. Language models helped me examine research designs and challenge my interpretations. I decided what to investigate, what the evidence could tell me, and what to do next.

The work moved much faster than I was used to. But I kept running into problems that had little to do with whether the AI could write good code or follow instructions.

This post is about those problems, and how I ended up turning what I learned into reusable skills for Claude and ChatGPT.

## How I used it

I tried to keep three parts of the work separate.

First was collecting and organizing evidence. I'd define what I needed, then use a coding agent to find records, apply coding rules, and produce tables. The instructions described the data and the task, not the result I hoped to find.

Second was designing and checking the work. I'd decide what comparison could answer my question, then use AI to help develop the instructions, identify possible problems, and check what came back.

Third was getting another reading of the evidence. I often had two different models examine the same material independently before comparing their responses. They sometimes caught mistakes I'd missed. They also disagreed, or confidently made the same mistake.

That last part was useful to learn. Two models agreeing isn't the same thing as having independent evidence.

## Where it went wrong

The biggest problem was that AI made it very easy to keep going.

Research used to have more pauses built into it. If collecting data took weeks, I had time to reconsider the design before the next analysis. Now I can ask for another collection, another model, or another check in the same afternoon.

That sounds wonderful until you realize you've spent the afternoon doing something you shouldn't have started.

**Rigorous answers to the wrong question.** In one project, I got quite far into the data work before establishing that the records could support the comparison I wanted. The source captured the amount of activity I was interested in, but not consistently the attribute that made that activity relevant to my argument.

We could count plenty of observations. What we couldn't establish was whether enough independent organizations differed in the way the theory required.

The analyses were technically sound, but they couldn't answer my question. I should have checked that before investing so much work. Now I check what needs to vary, which records establish that variation, and how many independent units actually carry it. Six hundred rows could represent just two independent decisions.

**Following the next interesting result.** Each exploratory analysis suggested something else worth checking. I kept approving the next comparison because it seemed reasonable given what I'd just seen.

Every step made sense. Every step was narrower.

Eventually, I realized I was answering a different question from the one I'd started with. I hadn't decided to change the question. I'd just kept following the next lead.

**Using the wrong standard.** Exploration can help me understand what the data contain, develop measures, and work out whether a proposed comparison is possible. It cannot independently confirm a hypothesis that I developed from those same observations.

The reverse matters too. I sometimes asked models to review early exploratory work, and they applied standards intended for confirmatory tests. They wanted holdouts and sample thresholds before I'd established what was even available to study.

I've become more careful about saying what stage I'm in and what the evidence can support. When a hypothesis is informed by exploratory results, testing it requires genuinely independent evidence or an appropriately limited claim. Simply running another model on data I've already examined doesn't solve that problem. Nor does writing a dated plan in my own files constitute public preregistration.

**Letting repairs take over.** I'd find a problem in the data, ask an agent to investigate, and discover more things to fix. I kept approving those repairs without always asking which conclusions they could change.

In one project, the cleanup expanded into a large exercise even though relatively few consequential results changed. The repairs weren't necessarily wrong. I just needed to know what they were restoring before spending more time on them.

**Reviewing by adding.** Give a model an argument and ask it to criticize it, and it will usually find something to improve. I've noticed the same thing when I ask it to review instructions or assess another model's suggestions.

I was accepting too many additions simply because they sounded reasonable. Now I want a reason for every proposed change, including an explanation of what would be lost by making it.

**Confusing a measure with the idea.** I've also had models interpret a null result for one measure as evidence that the underlying concept didn't matter. I sometimes let that interpretation go further than it should have.

One measure out of a family is still one measure. A result might challenge the theory, the measure, or the way the study was designed. Deciding which is part of the research.

These are familiar methodological problems. Gelman and Loken's work on the garden of forking paths and Simmons, Nelson, and Simonsohn's work on researcher degrees of freedom explain why apparently reasonable analytical choices can create misleading evidence. AI hasn't invented those problems. It has made it possible for me to encounter them much faster.

## How I'm trying to make it work

At first, I tried improving the prompts. Be rigorous. Keep the big picture in mind. Consider alternative explanations. Don't get distracted.

The models would acknowledge all of that and then carry on much as before.

What helped was turning those requests into steps that had to be completed before moving forward.

Before substantial data collection, I now establish what variation the study needs and whether the available records can show it. I keep my research question at the top of the working instructions, along with the conditions under which I'd reconsider it. And I label each round of work *explore*, *build*, or *test*, so I don't quietly change the rules halfway through.

I've also become stricter about checking what comes back. Important coding decisions need a path to the original record. Unknown values stay unknown rather than becoming zeros. Counts and denominators get checked against the underlying files, not just an AI-generated summary.

When something needs fixing, I want to know which results depend on it and what the correction could change.

And when I ask for an interpretation, I want an actual judgment. Which explanation fits better? What doesn't fit? What would change the assessment? I don't need a list of six equally plausible possibilities if the evidence already favors one.

I still use two models to challenge my thinking, but I have them work independently before seeing each other's conclusions. Then I go through their disagreements rather than treating agreement as a vote.

I've also started keeping a short restart note for each project. It records the question, the current argument, what I've ruled out and why, and the next piece of work. Otherwise, coming back after a week means reconstructing decisions I've already made.

Most of these are things a careful researcher would do anyway. But when I can move through several rounds of analysis in an afternoon, I find it helps to make the checks explicit.

## Where things stand

Over time, these instructions became reusable skills for Claude and ChatGPT.

The Claude version separates study design, running and auditing the work, and interpreting results into three skills. The ChatGPT version covers the same jobs in one skill with supporting reference files.

- Claude: [study design](/assets/evidence-first/Evidence_first_study_design-v20.zip), [run and audit](/assets/evidence-first/Evidence_first_run_and_audit-v2.zip), [read and decide](/assets/evidence-first/Evidence_first_read_and_decide-v2.zip). Start with study design; it points to the other two.
- ChatGPT: [one package](/assets/evidence-first/evidence_first_study_design_v1_4_0.zip).

They're built around how I work, which is also their limitation. All three projects are still underway. I haven't systematically tested whether these instructions improve research quality, and they may be too closely tailored to the problems I've encountered. The packaged ChatGPT version hasn't had a live behavioral evaluation yet.

I'm sharing them because I suspect other researchers using AI will recognize some of these problems, and I'd be interested to hear what they've found works better.

I still decide what to study, develop the argument, choose the design, inspect the evidence, and defend the conclusions. AI has made parts of that work much faster.

What I didn't expect was how much effort I'd have to put into deciding when *not* to use that speed.

---

### References

Gelman, A., & Loken, E. (2013). *The garden of forking paths: Why multiple comparisons can be a problem, even when there is no "fishing expedition" or "p-hacking" and the research hypothesis was posited ahead of time.* Working paper, Columbia University. [Link](https://sites.stat.columbia.edu/gelman/research/unpublished/forking.pdf)

Simmons, J. P., Nelson, L. D., & Simonsohn, U. (2011). False-positive psychology: Undisclosed flexibility in data collection and analysis allows presenting anything as significant. *Psychological Science, 22*(11), 1359–1366. [https://doi.org/10.1177/0956797611417632](https://doi.org/10.1177/0956797611417632)