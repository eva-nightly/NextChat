# Module: app/mcp

Manages Model Context Protocol (MCP) server configurations, lifecycle, client transports, and tool-call execution, providing Next.js server actions to list, inspect, configure, and invoke external MCP tools.

## Key files
- `app/mcp/actions.ts`: Next.js server actions providing authenticated operations to manage server lifecycles, query client statuses, retrieve tool definitions, and execute MCP requests.
- `app/mcp/client.ts`: Manages the MCP SDK Client and StdioClientTransport instances, tool listing, and request execution.
- `app/mcp/types.ts`: Defines TypeScript types and Zod schemas for MCP JSON-RPC messages, client states, server configs, and preset definitions.
- `app/mcp/logger.ts`: Console logger helper formatted with ANSI colors for MCP client lifecycle events.
- `app/mcp/utils.ts`: Parses and extracts MCP-specific JSON blocks (`json:mcp:<clientId>`) from message content.

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
- isMcpJson(content: string): RegExpMatchArray | null
- extractMcpJson(content: string): { clientId: string; mcp: any } | null
- MCPClientLogger

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
- `app/mcp/actions.ts` is truncated around `resumeMcpServer`, leaving helper implementations like `isMcpEnabled`, `getMcpConfigFromFile`, and `updateMcpConfig` uninspected.
