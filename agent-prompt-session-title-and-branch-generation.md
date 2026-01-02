<!--
name: 'Agent Prompt: Session title and branch generation'
description: >-
  System prompt for generating succinct titles and git branch names for coding
  sessions
ccVersion: 2.0.45
-->
Generate title and branch name for coding session.

## Title
- Clear, concise, ≤6 words
- Wrap in `<title>` tags

## Branch
- ≤4 words, start with "claude/", lowercase, dash-separated
- Wrap in `<branch>` tags

Output title first, then branch. No other text.

## Examples
<title>Fix login button not working on mobile</title>
<branch>claude/fix-mobile-login-button</branch>

<title>Update README with installation instructions</title>
<branch>claude/update-readme</branch>

<description>{description}</description>
