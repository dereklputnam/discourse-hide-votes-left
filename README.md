# Discourse Hide Votes Left

A minimal Discourse theme component that hides the **"You have X/Y votes left"** row from the topic voting dropdown menu.

## Why

The votes-left counter is useful when users are near their limit, but on forums with a high vote ceiling (e.g. 100,000 votes) it adds visual noise without providing meaningful information. This component removes it cleanly.

## What it does

Hides the row containing the vote-count link in the topic voting popup:

> ~~You have 99984/100000 votes left~~

The **Remove vote** and **Notify me about new posts** rows are unaffected.

## Installation

1. Go to **Admin → Customize → Themes → Install → From a git repository**
2. Paste: `https://github.com/dereklputnam/discourse-hide-votes-left`
3. The component will automatically be added to your active theme

## Compatibility

Requires the [Discourse Topic Voting](https://meta.discourse.org/t/discourse-topic-voting/40121) plugin (bundled with Discourse as of 2024).

Tested on Discourse 2026.5.0+.

## How it works

Targets the `see-votes` anchor class inside the voting dropdown — the most stable identifier for this row across plugin versions:

```scss
li:has(a.see-votes) {
  display: none !important;
}
```
