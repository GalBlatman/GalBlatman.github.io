---
title: "Teaching Claude to review like an editor"
date: 2026-08-18 18:00:00 -0700
description: "A pre-submission diagnostic should not behave like a peer review: the author is the one asking. I built one as a Claude skill and tested it against an editorial record it had never seen."
tags: [tools]
---

<link href="https://fonts.googleapis.com/css2?family=Newsreader:opsz,wght@6..72,400;6..72,500;6..72,600&family=IBM+Plex+Mono:wght@400;500&display=swap" rel="stylesheet">

<style>
.essay{--red:#B42B3C;--red-deep:#5c2730;--red-wash:#F6E7E9;--mono:'IBM Plex Mono',ui-monospace,monospace}
article .post-head h1{font-family:'Newsreader',Georgia,serif;font-size:clamp(2rem,5vw,2.7rem);line-height:1.12;margin:0 0 .55rem;font-weight:600;letter-spacing:-.01em}
.essay .deck{font-size:1.06rem;margin:0 0 1.6rem}
.essay .eyebrow{font-family:var(--mono);font-size:.7rem;letter-spacing:.14em;text-transform:uppercase;color:var(--red);margin:0 0 .5rem}
.essay .specimen{border-left:3px solid var(--red);background:var(--red-wash);padding:.9rem 1.1rem;margin:1.8rem 0;border-radius:0 3px 3px 0}
.essay .specimen .label{font-family:var(--mono);font-size:.68rem;letter-spacing:.12em;text-transform:uppercase;color:var(--red-deep);display:block;margin-bottom:.5rem}
.essay .specimen q{font-style:italic;display:block;margin-bottom:.5rem}
.essay .specimen .strike{text-decoration:line-through;text-decoration-color:var(--red);text-decoration-thickness:2px}
.essay .specimen .annot{font-family:var(--mono);font-size:.76rem;color:var(--red-deep)}
.essay .margin-note{font-family:var(--mono);font-size:.74rem;color:var(--red-deep);letter-spacing:.02em;margin:-.35rem 0 1rem}
.essay .results{display:grid;gap:1.2rem;margin:1.6rem 0}
@media(min-width:700px){.essay .results{grid-template-columns:1fr 1fr;gap:1.5rem}}
.essay .results section{border-top:2px solid var(--line);padding-top:.8rem}
.essay .results section.failed{border-top-color:var(--red)}
.essay .results h4{font-family:var(--mono);font-size:.72rem;letter-spacing:.12em;text-transform:uppercase;margin:0 0 .6rem;font-weight:500}
.essay .results section.failed h4{color:var(--red)}
.essay .results ul{margin:0;padding-left:1.1rem}
.essay .results li{margin-bottom:.6rem;font-size:.96rem;line-height:1.55}
.essay .facts{border-top:1px solid var(--line);border-bottom:1px solid var(--line);padding:1rem 0;margin:1.5rem 0;font-family:var(--mono);font-size:.78rem;line-height:1.9;color:var(--muted)}
.essay .getit{border:1px solid var(--line);border-left:3px solid var(--red);padding:1.2rem 1.3rem;margin:2.2rem 0;border-radius:0 4px 4px 0}
.essay .getit h3{margin:0 0 .5rem;font-size:1.1rem}
.essay ol.patterns{padding-left:1.2rem}
.essay ol.patterns li{margin-bottom:.75rem}
.essay ol.patterns b{font-weight:600}
.essay .refs{font-size:.94rem;padding-left:1.4rem;text-indent:-1.4rem;margin:0 0 .5rem}
</style>

<div class="essay" markdown="1">

<p class="deck">A pre-submission diagnostic looks like a peer review but has to invert its norms, because the audience is inverted: when the author is the one asking, exhaustiveness is a form of respect. I built that inversion into a Claude skill using my field's editorial philosophy, real decision letters from top journals in my field, and one instructive bad review, then tested it against an editorial record it had never seen. The corpus, the judgment calls, and the test design are mine. Here is what worked and where it broke.</p>

<div class="specimen">
<span class="label">Specimen: from an AI-generated peer review</span>
<q><span class="strike">I want to be clear that I am not recommending rejection because the idea is uninteresting;</span> I am recommending Reject &amp; Resubmit because the current execution falls short of the bar.</q>
<span class="annot">// delete: a hedge, not an argument</span>
</div>

## The problem: fluent reviews that don't work like reviews

<p class="margin-note">the specimen taught more than the exemplars did</p>

I had an unusual artifact sitting in a folder: an AI-generated peer review of one of my own submitted manuscripts. It looked like a review, with numbered major concerns, minor issues, questions for the authors, and a recommendation. And it exhibited a pathology set anyone who has asked a chatbot to review a paper will recognize. It said the same thing in three places. It hedged performatively, as above. It cited literature into existence with the confidence of a scholar who has read everything, including papers that may not exist. It padded its praise so the ratio would look fair. Individually these are small. Together they are why AI feedback on manuscripts reads like a review but does not function as one.

I am a postdoctoral researcher in management on the academic job market, and pre-submission feedback is the scarcest resource I have. Co-authors are busy, friendly reviews take weeks, and the reviews that matter arrive only after an editor has already made half the decision. I wanted a diagnostic I could run on my own drafts: something that flags everything wrong, explains why, suggests a fix, and holds the standard of the journals I target. So I built one as a Claude skill.

## A prompt is a bad place to keep a corpus

<p class="margin-note">version-controlled expertise, not prompt archaeology</p>

I had prompts. Everyone has prompts. A prompt can hold a great deal, including pasted reference material, so the problem is not capacity. The problem is maintenance. Prompts drift: you paste different versions on different days, you forget which file had the good clause, and quality varies with your clipboard hygiene. And what makes feedback good in a specific field is not an instruction like "be rigorous." It is calibration against what good and bad actually look like there, and that calibration lives in documents that need to be versioned, not in adjectives that need to be remembered.

A Claude skill is a small folder: one instruction file the model always reads when the skill triggers, plus reference files it consults at defined moments, packaged once and installed at the account level. After that, uploading a draft and asking for fresh eyes pulls the whole apparatus in automatically. The gain is persistent, version-controlled packaging of instructions plus calibration material. Infrastructure instead of improvisation.

## The raw material: philosophy, exemplars, and one very useful bad review

<p class="margin-note">four ingredients; the mix matters more than any one</p>

- **Editorial philosophy.** Three *Academy of Management Review* editor's essays: Ragins (2015), the field's flagship statement on developmental reviewing; Ballinger and Johnson (2015) on the four Rs of respect, reasons, recommendations, and recognition; and Lepak (2009). The field's own account of its standards, written by the people who enforced them.
- **Positive exemplars.** Real decision letters from top journals in my field. Direct, hierarchically numbered, reasoning before verdict, specific to the page and paragraph.
- **A negative exemplar.** The AI-generated review, which became the single most useful document in the pile.
- **My own protocols.** A twelve-section review prompt I had been iterating on, and a Reviewer 2 persona with a one-to-five harshness dial that I ultimately rejected.

## The design decision everything follows from: a diagnostic is not a review

<p class="margin-note">the audience inversion: when the author is the reader, exhaustiveness is the respect</p>

The editors' essays tell reviewers to prioritize five to eight concerns and not to kick dead horses, because the author did not ask for the review and a hundred-item list is demoralizing. Correct advice, for a reviewer writing to an author. But I am the author, and I did ask. When the author is the reader, exhaustiveness is not cruelty. It is the entire point, because the author will triage.

So the skill inverts the reviewing norm on three axes: flag everything, across theory, empirics, prose, numbers, citations, and tables; be direct without social cushioning; and never repeat, because each issue gets exactly one home, handled with the discipline flag, explain, suggest, move on. That last rule is not mine. AOM's own reviewer guidance says to avoid repeating the same critique in multiple places and to consolidate related points, which is the field telling you that repetition is a defect rather than thoroughness.

I kept the philosophy and dropped the manners. Respect, reasons, and recommendations survive intact. Recognition survives in lean form: name what to protect in revision, never pad praise. There is no harshness dial, because the editors are explicit that the Reviewer 2 posture is bad reviewing rather than rigorous reviewing, and my own letters confirm it: the toughest ones are firm and warm at once, and their toughness comes from the specificity of the reasoning rather than the temperature of the prose. I kept "be real" as the stance and stopped expecting it to do any work. The procedural rules below do that.

## The autopsy: eight named anti-patterns became the spec

<p class="margin-note">"don't sound like an AI" is not executable; "never write 'It is worth noting that'" is</p>

The most productive step in the build was treating the AI-generated review as a specimen and cataloguing its failure modes as named anti-patterns, each with a verbatim example and a corrected version. Eight made it in:

<ol class="patterns">
<li><b>Performative throat-clearing.</b> The specimen at the top. A social move, not an analytical one.</li>
<li><b>Saying the same thing in three places.</b> One measurement issue appeared as a major concern, again as a question for the authors, and again in a note to the editor. Length without information.</li>
<li><b>Formatting as a substitute for argument.</b> Bold-italic headers announcing importance the content doesn't earn.</li>
<li><b>Theatrical hedge constructions.</b> "It is worth noting that", "To be fair", "I would be remiss not to". The sentence after the hedge is the actual point; write that.</li>
<li><b>Citing-into-existence.</b> Fluent, confident, specific references that may not exist. The encoded rule: point to streams of literature and tell the user to verify; never fabricate specifics.</li>
<li><b>Padding the strengths section</b> so the praise-to-criticism ratio looks balanced.</li>
<li><b>Rhetorical questions as evasion.</b> "Can you provide any evidence that...?" when the honest sentence is "the paper provides no evidence for X."</li>
<li><b>Theatrical section headers.</b> Urgency in the label doing work the content should do.</li>
</ol>

Naming these with examples matters because "don't sound like an AI" is not an instruction a model can execute. "Never write 'It is worth noting that'" is.

## Architecture: one file always read, two consulted on demand

<p class="margin-note">progressive disclosure: protocol up front, calibration on call</p>

The skill is three files. `SKILL.md`, about 270 lines, is always loaded: the stance, the input handling, and a twelve-section protocol. `references/tone_and_register.md` holds the voice calibration and the eight anti-patterns, consulted before writing. `references/exhaustive_checklist.md` holds the scanning catalog for the section-by-section sweep: numerical consistency across tables and text, construct drift, hedge language, citation hygiene, per-section and per-method checks, and an opt-in reference style audit keyed to journal conventions, because house styles differ and change, and the model should not guess.

Three moves in the protocol earn their keep more than the rest. First, actual versus claimed contribution, including a required sentence stating what a hostile reader would say the paper is really about. That one sentence is worth the exercise. Second, hypothesis diagnosticity: classify every result as non-diagnostic, suggestive, discriminating, or highly probative. Many papers' first hypotheses are non-diagnostic, and it is better to hear that from your own tool than from Reviewer 3. Third, cut, rewrite, keep: the review ends with a revision memo, not a mood.

The skill also knows that real drafts are messy. It reads tracked changes with deletions intact, unpacks Word comments from the document XML, and treats bracketed notes as signal rather than noise: a "[TODO: explain why this differs from X]" sitting next to the paper's core construct is not a reminder, it is an unresolved theoretical problem, and the review says so.

## Test against an external editorial record, not vibes

<p class="margin-note">n = 1, but out-of-sample</p>

Most people evaluate AI tools by whether the output sounds smart. I had something better: one of my own manuscripts for which I held the full editorial packet, meaning the decision letter and all three reviewer reports from a top management journal. That packet was produced by independent readers before the skill existed, which makes it an out-of-sample benchmark rather than an answer key. The distinction matters, and my own result shows why: the most important thing the skill found is something no reviewer flagged. Against an answer key that would score as an error.

I ran the installed skill in a fresh chat, so the conversation that built it could not contaminate the execution.

<div class="results">
<section>
<h4>What it caught</h4>
<ul>
<li>The paper's central confound. Without the specifics: the treatment mechanically altered how the outcome was measured, whether or not the underlying construct moved, so the identification strategy could not separate substantive change from measurement change, and the headline effect was consistent with either. None of the three reviewer reports named this.</li>
<li>A rival mechanism for the most interesting finding, articulated more cleanly than the review packet did, including the observation that one of the paper's own robustness checks was evidence for the rival account.</li>
<li>A full diagnosticity classification of every hypothesis, which reviewers rarely do explicitly.</li>
<li>The register held: no hedging, no repetition across sections, reasoning before verdict throughout.</li>
</ul>
</section>
<section class="failed">
<h4>Where it failed</h4>
<ul>
<li>It padded the strengths section, which is exactly the anti-pattern it had been told to avoid.</li>
<li>It punted on the citation consistency check, telling me to run a programmatic check instead of performing it.</li>
<li>It mis-bucketed two revision priorities between must-fix and nice-to-have.</li>
<li>It named specific citations without flagging uncertainty, despite the citing-into-existence warning. That warning lived in a reference file; it leaked anyway.</li>
</ul>
</section>
</div>

One limitation worth naming rather than burying: the catches are checkable against the editorial packet, but the failure list is my own audit of my own tool, produced in the session that built it. An interested party graded the homework. That is the weakest joint in the evaluation, and the fix is other people running it on their own drafts.

## Every failure traced back to a loose instruction

<p class="margin-note">templates create demand; slots get filled</p>

The useful discipline was tracing each failure to the sentence that permitted it. The punted reference check: I had written "always do a bidirectional consistency check," and the model read "always do" as "always mention." Version two replaces it with numbered do-it-now steps and forbids the punt phrasing. The padded strengths: I had given a four-item template, and templates create demand, so the model filled the slots. Version two reframes the items as prompts to scan, states that the number is not fixed, and encodes the rule that competence is the floor rather than an asset: if a candidate strength is merely competently executed, exclude it.

The confabulated citations resist a prompt-level fix. The warning was already written down and the behavior survived it. Two lessons. Instructions in the always-loaded file bind harder than instructions in consulted reference files, so the highest-stakes rules belong in the main file. And some behaviors survive prompting entirely, which makes the mitigation procedural on my side: I verify every named citation before acting on one. A tool that is right about the confound and shaky on the bibliography is still enormously useful, as long as you know which is which.

Which leaves two lessons the exercise reinforced. Procedural instructions beat attitudinal ones. And negative exemplars are underrated, because failure is more legible than excellence: the bad review taught the skill more than either editors' essay did.

## What ships is the generic version

<p class="margin-note">calibration is personal; the shipped file is deliberately weaker</p>

The version I use is calibrated on my own material: my manuscripts, my decision letters, anti-patterns drawn from a review of my own paper, checklist examples keyed to the constructs and designs I actually work with. That specificity is most of what makes it good.

None of it ships. Before releasing the skill I genericized all three layers. The decision letters became descriptions of their moves rather than quoted passages. The anti-pattern examples lost the manuscript they came from. The checklist examples lost the constructs that made them concrete. Two different reasons, worth separating: the letters are other people's writing, produced under an expectation of confidentiality, while the manuscript examples are mine but belong to papers still under review, and I would rather not circulate their internals.

So the download is a scaffold, not a finished instrument, and the honest recommendation is to re-personalize it. Upload the three skill files to Claude along with whatever editorial material you have, whether decision letters from your own submissions, reviewer reports, or a rejection whose phrasing you still remember, and ask it to recalibrate the skill from them. What comes back is tuned to your field's register and your own recurring failure modes rather than mine. That is the version worth having. If you ever share yours, run the same genericization pass first, for the same two reasons.

<div class="getit">
<h3>Get the skill</h3>
<p>It is designed for management and adjacent social-science manuscripts, calibrated to the review standards of journals such as AMJ, ASQ, AMR, SMJ, and Organization Science. Installation instructions are in the README inside the download.</p>
<p class="facts">3 files · 12-section protocol · 8 named anti-patterns<br>
tracked-changes and Word-comment aware · opt-in journal-style reference audit<br>
always-on citation consistency check · no harshness dial</p>
<p><a href="/assets/academic-manuscript-review.zip" download>Download academic-manuscript-review.zip</a></p>
</div>

If it catches something your co-authors missed, or produces one of the failure modes it was designed against, I want to hear about it. The paper-authoring counterpart is the next build.

<h2>References</h2>

<p class="refs">Ballinger, G. A., &amp; Johnson, R. E. 2015. Editors' comments: Your first AMR review. <i>Academy of Management Review</i>, 40: 315-322.</p>

<p class="refs">Lepak, D. 2009. Editor's comments: What is good reviewing? <i>Academy of Management Review</i>, 34: 375-381.</p>

<p class="refs">Ragins, B. R. 2015. Editor's comments: Developing our authors. <i>Academy of Management Review</i>, 40: 1-8.</p>

</div>
