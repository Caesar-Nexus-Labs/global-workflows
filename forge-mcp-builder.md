---
name: /forge-mcp-builder
description: Rapid development of Model Context Protocol (MCP) servers.
category: Meta-Automation
status: Stable
methodology: Caesar Nexus Logic
---

# MCP Builder (/forge-mcp-builder)

## Caesar Nexus Execution Logic

### Phase 1: Tool Definition
- **Call**: `/forge-brainstorm`
- **Action**: Define tool names, descriptions, and JSON schema arguments.

### Phase 2: Schema Blueprint
- **Call**: `/forge-plan`
- **Action**: Orchestrate the MCP server architecture (using `@modelcontextprotocol/sdk`).

### Phase 3: Execution (Development)
- **Call**: `/forge-cook`
- **Action**: Implement handler logic and server state management.

### Phase 4: Testing & Validation
- **Call**: `/forge-test`
- **Action**: Invoke tools via MCP Inspector or CLI tests.

### Phase 5: Deployment & Integration
- **Action**: Register the new server in the Antigravity system configuration.

## Iron Laws
- **Standardized Schema**: Argument schemas must follow strictly documented types.
- **Error Handling**: Graceful error responses for all tool invocation failures.
- **Security**: Mandatory input sanitization before executing any system commands.

