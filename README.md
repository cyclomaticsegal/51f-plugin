# 51Folds Marketplace

A small plugin marketplace for 51FoldsQuestionMaker, which turns a rough idea into a submission-ready prediction question: one falsifiable hypothesis statement, two to five mutually exclusive outcomes, and an accompanying context of no more than 300 words, grounded in current web evidence.

## Install: two ways

### Option A: single file (easiest, no GitHub account needed)

Download `dist/51folds-question-maker.plugin`, then in Claude:

1. Open the Cowork tab and click Customize, then Plugins.
2. Click Add and drag in (or select) the file.
3. Done. Type `/51folds your idea`, or just describe a thesis and ask for a hypothesis.

### Option B: marketplace (gets automatic updates)

Inside Claude:

```
/plugin marketplace add YOUR-GITHUB-USERNAME/YOUR-REPO-NAME
/plugin install 51folds-question-maker@51folds-marketplace
/reload-plugins
```

When the plugin changes, bump `version` in `plugins/51folds-question-maker/.claude-plugin/plugin.json`; marketplace users pick it up.

## What it does

- Skill `hypothesis-builder`: the method. Triggers on natural language such as "frame a hypothesis" or pasting a claim and asking for a hypothesis.
- Skill `51folds`: the on-demand trigger. Type `/51folds your idea`.

Every build verifies present-day facts with web search, then returns the triplet, with the context kept at or under 300 words. Default lens is global; house style is concise with no em dashes.

## Repository layout

```
51folds-marketplace/
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
  .gitignore
```

The marketplace installs from `plugins/51folds-question-maker` (the source). The file in `dist/` is only for the manual drag-in route; rebuild it whenever you bump the version, or attach it to a GitHub Release instead.

## Trust and scope

Plugins run with the same access you have, so only install ones sent by someone you trust. This plugin needs no API keys or connectors; it uses the built-in web search. It only helps craft the input you submit to a prediction engine; it contains nothing about, and does not reproduce, the internal workings of any such engine.

## License

MIT. See LICENSE.
