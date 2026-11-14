---
layout: default
title: AI Brief Builder
permalink: /tools/ai-brief-builder/
description: A free, one-page-of-text agent that interviews the person asking for an AI agent and writes the brief a leader can sign off. Works in Claude, ChatGPT and Copilot.
---
<section class="section glow" style="padding-top:40px;padding-bottom:0">
<div class="wrap">
<h1>AI Brief Builder</h1>
<p class="lead measure">Before you fund an AI project, ask for the brief. This is the agent that writes it: an hour with the person who asked, fifteen questions, one page you can sign off.</p>
<div class="btn-row">
<a class="btn primary" href="{{ '/assets/downloads/ai-brief-builder.zip' | relative_url }}">Download the brief builder (zip, 9 KB)</a>
<a class="btn" href="{{ '/writing/did-anyone-ask-what-problem-it-solves/' | relative_url }}">Read the article</a>
</div>
</div>
</section>
<section class="section" style="padding-top:24px">
<div class="wrap">
<div class="article-body" style="margin:0" markdown="1">

## How to use it

It is a page of text. No files, connectors or budget.

- **Claude:** upload the folder as a skill, or paste `SKILL.md` into a Project's instructions. Say "Run the AI brief builder. I want an agent that..."
- **ChatGPT:** create a custom GPT and paste `instructions-for-copilot-and-chatgpt.md` into Instructions.
- **Microsoft Copilot:** choose "Create an agent" and paste the same text into its instructions. Share it with whoever brings you AI requests.

Give it to the person who asked for the AI, not to the developers. It asks one question at a time, keeps asking why until the real problem is clear, and writes the brief in a fixed shape. Sometimes the brief says "this does not need an agent." That is it working.

## What the brief contains

The one line it is for. The real problem, which is often not the one in the request. A recommendation: build it, build a narrower version, fix the underlying problem first, or do not build it. What it does, what systems it touches, the rules it must never break, what happens when it is wrong, what would make people hate it, how you will know it works, and job stories your team can build and test from.

The questions come from the [Agent Empathy Canvas]({{ '/writing/we-used-to-design-for-humans/' | relative_url }}), reframed for the person who signs the budget.

## A worked example

This is a made-up example. The request is the kind that lands on teams every week; the brief is what the AI Brief Builder produced from an hour with the person who asked.

## The ask, as it arrived

"We need an AI agent that can answer questions about our supplier contracts. Legal is drowning in the same questions and it slows everything down."

## What the interview found

The first why: "Legal gets forty emails a week asking about contracts." Why? "People need the payment terms, the notice period or the renewal date before they can act." Why can't they look it up? "Those details are inside PDFs. The contract system only holds the file, the supplier name and the dates it was signed." Why not in the system? "Nobody owns that data. It was never anyone's job."

Asked whether they would still want the agent if those three fields were in the system and searchable: "Honestly, that would solve most of it. The rest is the odd complicated clause, and legal should be the one reading that anyway."

## The brief

### AI brief: Contract answers for the business
Owner: Head of Procurement Operations · Date: 14 Nov 2026 · Status: draft for sign-off

#### The one line
Let people find the payment terms, notice period and renewal date of a supplier contract themselves, in under a minute, so legal only sees the questions that need a lawyer.

#### The real problem
Three fields that everyone needs are trapped inside PDFs because nobody owns contract data. The forty emails a week are a symptom of that.

#### Recommendation
Fix the underlying problem first, then build a narrower version. Extract and own the three fields in the contract system (an agent can do the first pass of extraction, a person checks it). Then give people a small agent that answers those three questions with a link to the clause. Do not build a general "ask anything about contracts" agent: it would answer complex clauses with confidence it has not earned, and legal would still have to check.

#### What it does
- Does: finds the contract for a named supplier; returns payment terms, notice period, renewal date, with the clause reference.
- Works out: whether a renewal or notice date falls in the next 90 days and says so.
- Tells: the requester; legal only when a question falls outside the three fields.
- Explains: which clause the answer came from, and when it is not sure.

#### What it touches
- Always reads: the contract system (metadata and the three extracted fields).
- Finds out per case: the clause text for the specific supplier, when asked to show it.
- Hands over: a short answer in the chat with a link to the clause; a logged question in the contract system; for anything else, a drafted email to legal with the question and the contract attached.

#### Rules
- Never: interpret liability, indemnity, termination-for-cause or any clause outside the three fields. Never state a figure without a clause reference.
- Stays with a person: all legal interpretation; any answer about a contract marked confidential.
- Can do on its own: answer the three questions; flag upcoming dates; draft (not send) the email to legal.
- Must stop or ask when: the field is missing or the extraction was never checked; two contracts match the supplier name.

#### When it goes wrong
If it cannot find a checked value it says "not confirmed, ask legal" and drafts the email, rather than guessing. Every answer carries the clause link so the person can check it in ten seconds. Legal sees a weekly list of questions it could not answer.

#### What would make people hate it
Confident wrong answers. Being sent back to legal for things it should know. Having to learn a new tool: it has to live in Teams, where the questions are asked today.

#### Done well looks like
Emails to legal about the three fields drop by at least 70% in three months. Every answer has a clause link. No answer is given on an unchecked field.

#### Job stories for the team
When someone asks for a supplier's payment terms, notice period or renewal date, it needs to find the checked value and the clause and return both, so that the person can act without emailing legal. Rules: never answer on an unchecked field; never interpret other clauses. Done when: 70% fewer of those emails, every answer linked.

When a renewal or notice date is within 90 days, it needs to say so in the answer, so that nobody misses a window. Rules: dates only, no advice on whether to renew. Done when: no missed renewal windows on contracts it has answered on.

When a question is outside the three fields, it needs to draft an email to legal with the question and the contract attached, so that legal gets a complete question first time. Rules: draft, never send. Done when: legal reports fewer back-and-forth clarifications.

#### Open questions
Who will own the three fields going forward? How many legacy contracts need extracting, and who checks the first pass?

#### Why we are asking now
"We were asked what we're doing with AI, and this was the loudest complaint." Noted. The data fix would have been worth doing regardless.


Free to use and adapt. If you improve it, I would like to hear how.

</div>
</div>
</section>
