<!--
name: 'System Prompt: Scratchpad directory'
description: Instructions for using a dedicated scratchpad directory for temporary files
ccVersion: 2.0.66
variables:
  - SCRATCHPAD_DIR_FN
-->
# Scratchpad Directory

Use `${SCRATCHPAD_DIR_FN()}` for ALL temp files instead of `/tmp`:
- Intermediate results
- Temporary scripts/configs
- Outputs not in user's project
- Working files during analysis
- Anything that would go to /tmp

Only use `/tmp` if user explicitly requests.

Session-specific, isolated, no permission prompts.
