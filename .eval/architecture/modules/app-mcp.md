# Module: app/mcp

Manages Model Context Protocol (MCP) server configurations, lifecycle operations (create, pause, resume, delete), client tool execution via stdio transports, and parsing of MCP-formatted code blocks.

## Key files
- `app/mcp/actions.ts`: Next.js Server Actions providing authorized endpoints to query, initialize, add, pause, and resume MCP servers and tools.
- `app/mcp/client.ts`: MCP SDK client wrapper providing functions to instantiate stdio transports, connect, list tools, and execute tool requests.
- `app/mcp/types.ts`: TypeScript types and Zod schemas for MCP requests, responses, notifications, server statuses, and configurations.
- `app/mcp/logger.ts`: ANSI-colored terminal logger utility for MCP operations.
- `app/mcp/utils.ts`: Utility functions for detecting and extracting MCP markdown code block payloads.

## Public interface
- getClientsStatus(accessCode: string): Promise<Record<string, ServerStatusResponse>>
- getClientTools(clientId: string, accessCode: string): Promise<ListToolsResponse | null>
- getAvailableClientsCount(accessCode: string): Promise<number>
- getAllTools(accessCode: string): Promise<Array<{ clientId: string, tools: ListToolsResponse | null }>>
- initializeMcpSystem(accessCode: string): Promise<McpConfigData | undefined>
- addMcpServer(clientId: string, config: ServerConfig, accessCode: string): Promise<McpConfigData>
- pauseMcpServer(clientId: string, accessCode: string): Promise<McpConfigData>
- resumeMcpServer(clientId: string, accessCode: string): Promise<void>
- createClient(id: string, config: ServerConfig): Promise<Client>
- removeClient(client: Client): Promise<void>
- listTools(client: Client): Promise<ListToolsResponse>
- executeRequest(client: Client, request: McpRequestMessage): Promise<any>
- getMcpChildEnvironment(configEnv?: Record<string, string>): Record<string, string>
- isMcpJson(content: string): RegExpMatchArray | null
- extractMcpJson(content: string): { clientId: string, mcp: any } | null
- MCPClientLogger

## Dependencies
- @modelcontextprotocol/sdk/client/index.js
- @modelcontextprotocol/sdk/client/stdio.js
- fs/promises
- path
- spark-md5
- zod

## AI touchpoints [AI]
- `app/mcp/client.ts`
- `app/mcp/utils.ts`

## Open questions
- app/mcp/actions.ts is truncated near the end of resumeMcpServer and references missing unexported or cut-off helpers like isMcpEnabled, getMcpConfigFromFile, and updateMcpConfig.
