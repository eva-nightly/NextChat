# Module: app/mcp

Provides Model Context Protocol (MCP) server lifecycle management, tool discovery, and execution over stdio transports for integrating external tools with LLM chat interactions.

## Key files
- `app/mcp/actions.ts`: Next.js server actions providing authenticated RPC endpoints to manage MCP server configs, start/stop clients, and retrieve tool definitions.
- `app/mcp/client.ts`: Wrapper around @modelcontextprotocol/sdk to spawn stdio transports, create/close MCP clients, list available tools, and execute tool calls.
- `app/mcp/logger.ts`: Console logger formatted with ANSI colors for MCP client lifecycle and debug events.
- `app/mcp/types.ts`: Type definitions and Zod validation schemas for JSON-RPC MCP request/response messages, server configs, and client states.
- `app/mcp/utils.ts`: Utility functions to detect and extract MCP-specific JSON blocks from chat markdown content.

## Public interface
- getClientsStatus(accessCode: string): Promise<Record<string, ServerStatusResponse>>
- getClientTools(clientId: string, accessCode: string): Promise<ListToolsResponse | null>
- getAvailableClientsCount(accessCode: string): Promise<number>
- getAllTools(accessCode: string): Promise<Array<{ clientId: string; tools: ListToolsResponse | null }>>
- initializeMcpSystem(accessCode: string): Promise<McpConfigData | undefined>
- addMcpServer(clientId: string, config: ServerConfig, accessCode: string): Promise<McpConfigData>
- pauseMcpServer(clientId: string, accessCode: string): Promise<McpConfigData>
- resumeMcpServer(clientId: string, accessCode: string): Promise<void>
- createClient(id: string, config: ServerConfig): Promise<Client>
- removeClient(client: Client): Promise<void>
- listTools(client: Client): Promise<ListToolsResponse>
- executeRequest(client: Client, request: McpRequestMessage): Promise<any>
- getMcpChildEnvironment(configEnv?: Record<string, string>): Record<string, string>
- MCPClientLogger
- isMcpJson(content: string): RegExpMatchArray | null
- extractMcpJson(content: string): { clientId: string; mcp: any } | null
- McpRequestMessageSchema
- McpResponseMessageSchema
- McpNotificationsSchema

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
- app/mcp/actions.ts is truncated near resumeMcpServer; additional server actions or helper functions defined below the cut are not visible.
