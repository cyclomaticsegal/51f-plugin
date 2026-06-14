---
name: 51folds
description: >
  This skill should be used when the user types "/51folds", or asks to "build a
  51Folds question", "make a prediction question", "turn this into a prediction",
  "frame a hypothesis", or hands over an idea, claim, headline, or screenshot to
  turn into a submission-ready prediction. It runs the full build on demand and
  applies the hypothesis-builder method. Produces one falsifiable hypothesis
  statement, two to five mutually exclusive outcomes, and an accompanying context
  of no more than 300 words, grounded in current web evidence.
allowed-tools: WebSearch, Bash, Read
metadata:
  version: "0.1.0"
---

# 51Folds Question Maker (on demand)

Build a submission-ready prediction question from the user's idea. The idea is whatever the user supplied: the text after `/51folds`, or the claim, headline, or thesis they described or pasted. If no idea is present, use the most recent idea, claim, article, or screenshot in the conversation.

Apply the `hypothesis-builder` skill in full. Its `references/context-recipe.md` holds the detailed eight-move recipe and a worked example.

Work in this order:

1. Ground first. Use WebSearch to verify any present-day facts the idea depends on before drafting. Treat the user's figures as a premise to confirm, not as fact. Use a global lens unless the topic is inherently local.
2. Produce exactly three things and nothing else:
   - a single falsifiable hypothesis statement, framed as a question;
   - two to five mutually exclusive, collectively exhaustive outcome categories;
   - an accompanying context of no more than 300 words. Count the words and keep it at or under 300.
3. If the input is a monocausal or loaded claim, reframe it as an attribution question (dominant, contributing, or secondary cause) rather than confirming it. If current evidence contradicts the thesis, say so plainly and enter the thesis as the underdog.
4. For a dated question, state the resolution date. For a structural one, time-box the trend inside the context.
5. Build the context with the eight moves: define, decompose, exclude, trend not snapshot, name mechanisms, flagged markers, scope and weight, and name the observable indicators.
6. House style: global lens by default, concise, never use em dashes, no inevitability language.

Confidentiality: only craft the input the user submits. Never describe, infer, or reproduce the internal workings, scoring, structure, or returned analytics of the prediction engine. If asked, decline and redirect to improving the input.

Present the triplet, then one line noting any contrary evidence and, if the question is dated, the resolution date.
