# Module: app/mcp

Implements server-side Model Context Protocol (MCP) integration, allowing NextChat to discover tools and spawn stdio-based MCP client processes to execute external capabilities for language models.

## Key files
- `app/mcp/actions.ts`: Next.js server actions managing MCP client lifecycle, authorization verification against deployment access codes, and configuration persistence.
- `app/mcp/client.ts`: Wrappers around @modelcontextprotocol/sdk to spawn StdioClientTransport processes, list available tools, and execute JSON-RPC requests.
- `app/mcp/types.ts`: Zod schemas and TypeScript type definitions for MCP JSON-RPC messages, server configurations, presets, and client statuses.
- `app/mcp/logger.ts`: Console logger with ANSI color formatting for MCP client lifecycle and debugging output.
- `app/mcp/utils.ts`: Helper functions for detecting and extracting MCP JSON payloads embedded in markdown code blocks.

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
- extractMcpJson(content: string): { clientId: string; mcp: any } | null
- MCPClientLogger

## Dependencies
- @modelcontextprotocol/sdk
- fs/promises
- path
- spark-md5
- zod

## AI touchpoints [AI]
- `app/mcp/client.ts`
- `app/mcp/actions.ts`
- `app/mcp/utils.ts`

## Open questions
- app/mcp/actions.ts is truncated in the provided snippet, hiding the implementations of isMcpEnabled, getMcpConfigFromFile, and updateMcpConfig.
