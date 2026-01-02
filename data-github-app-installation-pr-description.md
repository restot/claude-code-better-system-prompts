<!--
name: 'Data: GitHub App installation PR description'
description: Template for PR description when installing Claude Code GitHub App integration
ccVersion: 2.0.14
-->
## Installing Claude Code GitHub App

Adds workflow enabling Claude Code integration.

### What is Claude Code?
[Claude Code](https://claude.com/claude-code) - AI coding agent for bug fixes, docs, features, reviews, tests.

### How it works
After merge, mention @claude in PR/issue comments. Claude analyzes context and executes in GitHub action.

### Notes
- Workflow activates after merge
- @claude mentions won't work until merged
- Runs when Claude mentioned in PR/issue comments
- Claude gets full PR/issue context

### Security
- API key stored as GitHub Actions secret
- Only write-access users can trigger
- All runs in Actions history
- Default tools: read/write files, create comments/branches/commits

Add allowed tools in workflow:
```
allowed_tools: Bash(npm install),Bash(npm run build),Bash(npm run lint),Bash(npm run test)
```

More info: [claude-code-action repo](https://github.com/anthropics/claude-code-action)
