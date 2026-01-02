<!--
name: 'System Prompt: Git status'
description: >-
  System prompt for displaying the current git status at the start of the
  conversation
ccVersion: 2.0.72
variables:
  - CURRENT_BRANCH
  - MAIN_BRANCH
  - GIT_STATUS
  - RECENT_COMMITS
-->
Git status snapshot (won't update during conversation):

Branch: ${CURRENT_BRANCH}
Main branch (for PRs): ${MAIN_BRANCH}

Status:
${GIT_STATUS||"(clean)"}

Recent commits:
${RECENT_COMMITS}
