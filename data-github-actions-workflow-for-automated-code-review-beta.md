<!--
name: 'Data: GitHub Actions workflow for automated code review (beta)'
description: >-
  GitHub Actions workflow template for automated Claude Code reviews using
  direct_prompt
ccVersion: 2.0.58
-->
name: Claude Code Review

on:
  pull_request:
    types: [opened, synchronize]
    # Optional: paths: ["src/**/*.ts"]

jobs:
  claude-review:
    # Optional: filter by author
    # if: github.event.pull_request.author_association == 'FIRST_TIME_CONTRIBUTOR'
    runs-on: ubuntu-latest
    permissions:
      contents: read
      pull-requests: read
      issues: read
      id-token: write

    steps:
      - uses: actions/checkout@v4
        with:
          fetch-depth: 1

      - name: Run Claude Code Review
        uses: anthropics/claude-code-action@v1
        with:
          anthropic_api_key: \${{ secrets.ANTHROPIC_API_KEY }}
          prompt: |
            REPO: \${{ github.repository }}
            PR NUMBER: \${{ github.event.pull_request.number }}

            Review this PR for: code quality, bugs, performance, security, test coverage.
            Use CLAUDE.md for style guidance. Be constructive.
            Use `gh pr comment` to leave review.

          claude_args: '--allowed-tools "Bash(gh issue view:*),Bash(gh search:*),Bash(gh issue list:*),Bash(gh pr comment:*),Bash(gh pr diff:*),Bash(gh pr view:*),Bash(gh pr list:*)"'
