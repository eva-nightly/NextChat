# Module: app/mcp

Manages Model Context Protocol (MCP) server lifecycle, configuration, stdio client transport connections, tool discovery, and execution within NextChat.

## Key files
- `app/mcp/actions.ts`: Server Actions for authenticating requests, managing MCP server state (add, pause, resume, initialize), retrieving available tools, and querying server statuses.
- `app/mcp/client.ts`: Wraps the Model Context Protocol SDK to establish stdio client transports, list tools, and execute client requests.
- `app/mcp/logger.ts`: Console logger helper formatted with ANSI color codes for terminal and Tauri environment output.
- `app/mcp/types.ts`: TypeScript interfaces and Zod schemas for MCP messages, server configurations, client runtime status, and preset server definitions.
- `app/mcp/utils.ts`: Parsing utilities to detect and extract MCP-formatted JSON blocks embedded in chat message strings.

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
- `app/mcp/actions.ts`
- `app/mcp/utils.ts`

## Open questions
- app/mcp/actions.ts references functions not fully defined within the visible file snippet (such as isMcpEnabled, getMcpConfigFromFile, and updateMcpConfig).
