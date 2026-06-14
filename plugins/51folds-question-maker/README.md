# 51FoldsQuestionMaker

Turns a rough idea into a submission-ready prediction question. Every build returns the same triplet:

1. A hypothesis statement: one precise, falsifiable question.
2. Outcome categories: two to five mutually exclusive, collectively exhaustive results.
3. An accompanying context of no more than 300 words.

You submit that triplet to your prediction engine manually. The plugin grounds every build in current web evidence and will flag when the latest data cuts against the thesis.

## Components

- Skill: `hypothesis-builder`. Triggers on natural language such as "frame a hypothesis", "turn this into a prediction", or pasting a claim and asking for a hypothesis. Carries the full method: the standard for the question, the eight-move context recipe, and the current-awareness workflow. Detailed recipe and a worked example live in its `references/` folder.
- Skill `51folds`: the explicit, on-demand trigger. Fires when you type `/51folds` or ask to build a 51Folds question, and runs the full workflow.

## Setup

No configuration required. Web grounding uses the built-in web search; no API keys or connectors needed.

## Usage

- Type `/51folds` followed by your idea, for example: `/51folds the central bank will pause rate hikes at its next meeting`.
- Or just describe the idea in plain language and ask for a hypothesis.

The plugin verifies present-day facts, drafts the question, proposes the outcomes, writes the sub-300-word context, and keeps it under the word ceiling.

## House style

Global lens by default. Concise and direct. No em dashes. No inevitability language.

## Scope and confidentiality

This plugin only helps craft the input you submit. It does not describe, infer, or reproduce the internal workings of any prediction engine. It produces just the hypothesis statement, the outcomes, and the context.

Not enabled in this build: pressure-test mode, draft critique and merge, and save-to-file. Any of these can be added later.

## Version

0.1.0
