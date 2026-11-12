# Module: app/mcp

Manages Model Context Protocol (MCP) clients, configurations, and tool integrations, enabling tool discovery and execution via stdio transports with access code authorization.

## Key files
- `app/mcp/actions.ts`: Server Actions for MCP lifecycle management, configuration persistence, client authorization, tool listing, and status reporting.
- `app/mcp/client.ts`: Wraps the Model Context Protocol SDK to initialize stdio client transports, list tools, and execute tool requests.
- `app/mcp/types.ts`: Type definitions and Zod schemas for MCP messages, server configurations, statuses, and tool responses.
- `app/mcp/logger.ts`: ANSI color-formatted console logger for MCP client and server action events.
- `app/mcp/utils.ts`: Regex utility functions to detect and extract MCP tool call JSON blocks from markdown content.

## Public interface
- getClientsStatus(accessCode: string)
- getClientTools(clientId: string, accessCode: string)
- getAvailableClientsCount(accessCode: string)
- getAllTools(accessCode: string)
- initializeMcpSystem(accessCode: string)
- addMcpServer(clientId: string, config: ServerConfig, accessCode: string)
- pauseMcpServer(clientId: string, accessCode: string)
- resumeMcpServer(clientId: string, accessCode: string)
- createClient(id: string, config: ServerConfig)
- removeClient(client: Client)
- listTools(client: Client)
- executeRequest(client: Client, request: McpRequestMessage)
- getMcpChildEnvironment(configEnv?: Record<string, string>)
- isMcpJson(content: string)
- extractMcpJson(content: string)
- MCPClientLogger

## Dependencies
- @modelcontextprotocol/sdk
- zod
- spark-md5
- fs/promises
- path

## AI touchpoints [AI]
- `app/mcp/client.ts`
- `app/mcp/utils.ts`

## Open questions
- Several internal helper functions in app/mcp/actions.ts (such as isMcpEnabled, getMcpConfigFromFile, and updateMcpConfig) are cut off in the truncated source file.
