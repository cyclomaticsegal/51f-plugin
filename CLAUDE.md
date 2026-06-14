# CLAUDE.md

> **Note:** This repo is also being discussed in a Claude Cowork workspace called **"Brain: 51Folds-Hypo-Builder"**. Context, decisions, and design discussion may live there as well as in the code — check it for background that isn't captured in this repo.

## What this is

A small plugin marketplace for **51FoldsQuestionMaker**, which turns a rough idea into a submission-ready prediction question: one falsifiable hypothesis statement, two to five mutually exclusive outcomes, and a context of no more than 300 words, grounded in current web evidence.

## Purpose

Most predictions die as vague statements. "Prices will rise," "the policy will fail," "rates are to blame" sound like forecasts, but you cannot test them, score them, or learn from them later. They hide their definitions, smuggle in their own conclusions, and leave no way to tell, months on, whether you were right. 51FoldsQuestionMaker fixes that at the source: it turns a rough idea into a prediction you can actually be held to.

Hand it a hunch, a headline, a screenshot, or a half-formed thesis. It returns three things: a single falsifiable question, a small set of mutually exclusive outcomes, and a tight context of no more than 300 words that defines the key terms, draws the boundaries, names the mechanism in play, and lists the specific signals that would confirm or refute the claim. The result is a clean, submission-ready prediction rather than an opinion.

Two things make it more than a formatter. First, it checks current evidence before it writes, so the question is anchored to what is true today rather than to a stale assumption. Second, it is honest about the odds: if the latest data cuts against your thesis, it says so and frames your idea as the underdog instead of quietly confirming what you hoped to hear. When you hand it a loaded, single-cause claim, it reframes it as a fair test rather than rubber-stamping it.

The payoff is speed and discipline at once. You get the rigour of a well-formed forecast, clear definitions, a time frame, named drivers, and explicit falsifiers, in the time it takes to describe the idea, and you get it the same way every time. The output drops straight into your forecasting workflow, so your effort goes into thinking, not formatting.

## Repository layout

```
51f-plugin/
  .claude-plugin/marketplace.json   catalog the marketplace install reads
  plugins/
    51folds-question-maker/         the plugin source (installed from here)
      .claude-plugin/plugin.json
      skills/hypothesis-builder/SKILL.md
      skills/hypothesis-builder/references/context-recipe.md
      skills/51folds/SKILL.md
      README.md
      LICENSE
  dist/
    51folds-question-maker.plugin   prebuilt file for the drag-in route
  LICENSE
  README.md
```

## Skills

- `hypothesis-builder` — the method. Triggers on natural language such as "frame a hypothesis" or pasting a claim and asking for a hypothesis.
- `51folds` — the on-demand trigger. Type `/51folds your idea`.

Every build verifies present-day facts with web search, then returns the triplet, with the context kept at or under 300 words. Default lens is global; house style is concise with no em dashes.

## Releasing

When the plugin changes, bump `version` in `plugins/51folds-question-maker/.claude-plugin/plugin.json`; marketplace users pick it up.
