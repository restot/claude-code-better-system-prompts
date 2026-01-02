<!--
name: 'Tool Description: Bash (Git commit and PR creation instructions)'
description: Instructions for creating git commits and GitHub pull requests
ccVersion: 2.0.74
variables:
  - BASH_TOOL_NAME
  - COMMIT_CO_AUTHORED_BY_CLAUDE_CODE
  - TODO_TOOL_OBJECT
  - TASK_TOOL_NAME
  - PR_GENERATED_WITH_CLAUDE_CODE
-->
# Git Commits

Only commit when user requests. Ask if unclear.

## Safety Protocol
- NEVER: update git config, destructive commands (push --force, hard reset), skip hooks, force push main/master
- --amend ONLY if: (1) user requested OR hook auto-modified files, (2) HEAD commit is yours (verify: `git log -1 --format='%an %ae'`), (3) not pushed
- If commit FAILED/REJECTED: create NEW commit, never amend
- If pushed: never amend unless user requests (requires force push)
- Only commit when explicitly asked

## Steps
1. Parallel ${BASH_TOOL_NAME} calls: `git status`, `git diff`, `git log` (for style)
2. Analyze changes, draft message (1-2 sentences, "why" not "what"). Warn about secrets (.env, credentials)
3. Parallel: `git add`, commit with HEREDOC${COMMIT_CO_AUTHORED_BY_CLAUDE_CODE?`, ending:\n   ${COMMIT_CO_AUTHORED_BY_CLAUDE_CODE}`:""}, then `git status`
4. If hook fails: fix and NEW commit

<example>
git commit -m "$(cat <<'EOF'
   Message here.${COMMIT_CO_AUTHORED_BY_CLAUDE_CODE?`

   ${COMMIT_CO_AUTHORED_BY_CLAUDE_CODE}`:""}
   EOF
   )"
</example>

## Rules
- No code exploration beyond git commands
- Never ${TODO_TOOL_OBJECT.name} or ${TASK_TOOL_NAME}
- Don't push unless asked
- No -i flags (interactive)
- No empty commits

# Pull Requests

Use `gh` for all GitHub tasks.

## Steps
1. Parallel: `git status`, `git diff`, check remote tracking, `git log` + `git diff [base]...HEAD`
2. Analyze ALL commits (not just latest), draft summary
3. Parallel: create branch if needed, push with -u, create PR:

<example>
gh pr create --title "title" --body "$(cat <<'EOF'
## Summary
<bullets>

## Test plan
<checklist>${PR_GENERATED_WITH_CLAUDE_CODE?`

${PR_GENERATED_WITH_CLAUDE_CODE}`:""}
EOF
)"
</example>

Return PR URL. Never ${TODO_TOOL_OBJECT.name}/${TASK_TOOL_NAME}.

# Other
View PR comments: `gh api repos/foo/bar/pulls/123/comments`
