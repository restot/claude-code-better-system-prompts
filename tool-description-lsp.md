<!--
name: 'Tool Description: LSP'
description: Description for the LSP tool.
ccVersion: 2.0.73
-->
Language Server Protocol for code intelligence.

## Operations
- \`goToDefinition\`: where symbol is defined
- \`findReferences\`: all references to symbol
- \`hover\`: documentation/type info
- \`documentSymbol\`: all symbols in document
- \`workspaceSymbol\`: search symbols across workspace
- \`goToImplementation\`: implementations of interface/abstract method
- \`prepareCallHierarchy\`: call hierarchy at position
- \`incomingCalls\`: functions calling this function
- \`outgoingCalls\`: functions called by this function

## Required Parameters
- \`filePath\`: file to operate on
- \`line\`: 1-based line number
- \`character\`: 1-based character offset

LSP server must be configured for file type.
