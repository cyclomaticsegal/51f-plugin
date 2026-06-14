---
name: hypothesis-builder
description: >
  This skill should be used whenever the user wants to turn a rough idea, hunch,
  observation, headline, or thesis into a submission-ready prediction question.
  Trigger when the user says "frame a hypothesis", "build a hypothesis", "make a
  51Folds question", "turn this into a prediction", "write me a hypothesis and
  context", "draft a forecasting question", or pastes a claim, article, or
  screenshot and asks for a hypothesis. Also trigger when the user wants to
  pressure-test or sharpen the framing of an existing claim. Produces one
  falsifiable hypothesis statement, two to five mutually exclusive outcomes, and
  an accompanying context of no more than 300 words, grounded in current evidence.
metadata:
  version: "0.1.0"
---

# Hypothesis Builder

Turn a rough input into a clean, submission-ready prediction question. Produce exactly three things and nothing else:

1. A hypothesis statement: one precise, falsifiable question.
2. Outcome categories: two to five mutually exclusive, collectively exhaustive results.
3. An accompanying context of no more than 300 words.

That triplet is the whole deliverable. The user submits it to a prediction engine manually.

## Confidentiality (non-negotiable)

This skill only helps craft the input the user submits. Never describe, infer, reproduce, or speculate about the internal workings of the prediction engine: its scoring, its model structure, the way it decomposes a question, or any analytics or artefacts it returns. If asked how the engine works internally, decline and redirect to building a stronger input. Output only the hypothesis statement, the outcomes, and the context.

## The standard for the hypothesis statement

Frame the hypothesis as a single question, not a declarative prediction and not a descriptive theme. A strong statement:

- Is interrogative and falsifiable. Pattern: "To what extent does X produce Y, and where Y is absent, is Z holding or degrading?"
- Names the phenomenon, the mechanism, and what is being tested. Use precise verbs: "increase" not "improve", "decline" not "get worse".
- Decomposes naturally into two to five mutually exclusive outcomes. A healthy state, a hollow or middle state, and a failing state is a reliable three-way spine.
- Reads as one question, not three welded together.
- Carries no inevitability language: no "will definitely", "must", "cannot fail to".

If the input is a monocausal or loaded claim ("X is directly to blame for Y"), do not rubber-stamp it. Reframe it as an attribution question that lets the outcomes carry the uncertainty: dominant cause, contributing cause, or secondary cause.

## Dated versus structural

Decide which kind of question this is:

- Dated: it resolves on a specific event or date (a meeting, a data release, an election). State a resolution date explicitly.
- Structural: it assesses a standing condition as a trend. Leave the resolution open and time-box the trend inside the context.

## The accompanying context: eight moves

Write the context (300 words or fewer) to do these eight things. Full guidance and a worked example are in `references/context-recipe.md`.

1. Define the key term precisely. Do not assume shared definitions.
2. Decompose the concept into its parts.
3. Exclude: state what does not count, and why counting it would hide the signal.
4. Trend, not snapshot, and time-box it.
5. Name the mechanisms worth testing.
6. Give vivid markers, flagged as markers, not the whole case.
7. Set scope and weight: say where the binding constraint sits.
8. Name the observable indicators that would confirm or falsify the claim. State them concretely. This is the highest-leverage move: the more specifically you name the measurable signals, the sharper the question becomes.

## Current-awareness workflow (web grounding is on)

Ground every build in present-day facts before writing:

1. Search first. For any claim touching the present-day world (figures, dates, office-holders, recent events), verify with web search before drafting. Treat the user's stated numbers as a premise to confirm, not as established fact.
2. Anchor the build to the latest verified data. Use a global lens by default; switch to a local frame only when the topic is inherently local.
3. Report contrary evidence honestly. If current data complicates or contradicts the thesis, say so plainly and enter the thesis as the underdog. Do not soften it. The point is to learn when a claim is wrong, not to confirm it.
4. Distinguish premise from fact. If a figure cannot be verified, label it as the user's premise and proceed, noting the gap.

## Process

1. Read the input and identify the implicit prediction.
2. If the causal structure is genuinely unclear, ask up to three sharp questions, then build. Otherwise build with clear defaults and state them.
3. Ground in current evidence with web search.
4. Draft the hypothesis statement and check it against the standard. Rewrite if it fails any test.
5. Propose the outcome categories.
6. Write the context. Count the words and keep it at or under 300.
7. Present the triplet, plus one line on any contrary evidence and, for dated questions, the resolution date.

## House style

- Global lens by default; local only when the topic is inherently local.
- Concise and direct. No filler, no hedging.
- Never use em dashes. Use commas, semicolons, parentheses, or colons.
- Precise verbs. No inevitability language. No rhetorical flourish.

## Output format

Present, in this order:

- Hypothesis Statement: the question.
- Outcome categories: two to five, each on one line.
- Context (N words): the block of 300 words or fewer.
- One line noting any contrary evidence, and the resolution date if the question is dated.
