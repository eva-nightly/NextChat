# Module: app/mcp

Manages Model Context Protocol (MCP) server configurations, child processes, and stdio client connections to discover and execute tools for LLM agent capabilities.

## Key files
- `app/mcp/actions.ts`: Next.js server actions managing MCP client lifecycle, authorization verification, server status tracking, configuration persistence, and tool discovery.
- `app/mcp/client.ts`: Wrapper around Model Context Protocol SDK to establish stdio client transports, list tools, and execute tool requests.
- `app/mcp/logger.ts`: Console logger with ANSI color styling customized for MCP client events.
- `app/mcp/types.ts`: TypeScript definitions and Zod schemas for MCP messages, server configurations, client status, and tool responses.
- `app/mcp/utils.ts`: String parsing utilities for detecting and extracting MCP JSON payloads from markdown code blocks.

## Public interface
- getClientsStatus(accessCode: string): Promise<Record<string, ServerStatusResponse>>
- getClientTools(clientId: string, accessCode: string)
- getAvailableClientsCount(accessCode: string)
- getAllTools(accessCode: string)
- initializeMcpSystem(accessCode: string)
- addMcpServer(clientId: string, config: ServerConfig, accessCode: string)
- pauseMcpServer(clientId: string, accessCode: string)
- resumeMcpServer(clientId: string, accessCode: string): Promise<void>
- getMcpChildEnvironment(configEnv?: Record<string, string>): Record<string, string>
- createClient(id: string, config: ServerConfig): Promise<Client>
- removeClient(client: Client): Promise<void>
- listTools(client: Client): Promise<ListToolsResponse>
- executeRequest(client: Client, request: McpRequestMessage): Promise<any>
- MCPClientLogger
- McpRequestMessageSchema
- McpResponseMessageSchema
- McpNotificationsSchema
- isMcpJson(content: string)
- extractMcpJson(content: string)

## Dependencies
- @modelcontextprotocol/sdk
- zod
- spark-md5
- fs/promises
- path

## AI touchpoints [AI]
- `app/mcp/client.ts`
- `app/mcp/actions.ts`
- `app/mcp/utils.ts`

## Open questions
- How does the client side handle server action timeouts or long-running stdio MCP child processes across Next.js serverless or multi-instance deployments since clients are stored in an in-memory Map?
