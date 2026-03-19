---
name: /forge-mcp-management
description: Lifecycle and security management of MCP tools.
category: Engineering
status: Stable
methodology: Caesar Nexus Logic
---

# MCP Management Workflow (/forge-mcp-management)

## 1. Description
Manages the lifecycle, security, and integration of Model Context Protocol (MCP) servers.

## 2. Caesar Nexus Execution Loop

### Phase 1: Discovery & Compatibility
1. **Tool Scouting**: Invoke **[/forge-scout](./forge-scout.md)** (mcp mode) to find tool gaps in the current swarm.
2. **Capability Audit**: Pulse **[/forge-research](./forge-research.md)** to find the most optimized MCP implementation for the task.

### Phase 2: Configuration & Security
1. **Secret Storage**: Invoke **[/ops-secrets](./ops-secrets.md)** for API keys and credentials used by the MCP server.
2. **Registry Mapping**: Update `mcp_config.json` and ensure zero-abstraction routing in `routes.rs`.

### Phase 3: Integration & Testing
1. **API Validation**: Trigger **[/forge-test](./forge-test.md)** with a specialized "MCP Roundtrip" test case.
2. **Connectivity Pulse**: Invoke **[/ops-status](./ops-status.md)** to verify server health.

### Phase 4: Master Ingestion
1. **Handoff**: Link the new tool to the **[/nexus-audit](./nexus-audit.md)** system for continuous governance.
2. **Trigger**: `trigger-task-logger` records the new tool integration.

## 3. Iron Laws
- **Zero Latency**: MCP tool implementations must not block the main execution thread. Use async/await.
- **Least Privilege**: Each MCP server must have the absolute minimum file/network permissions required.
- **English Standard**: All MCP tool documentation and error messages must be in English.
