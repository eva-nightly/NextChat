# Module: app/mcp

Manages Model Context Protocol (MCP) server configurations, child process STDIO transports, client lifecycles, tool discovery, and execution requests via secure Next.js server actions.

## Key files
- `app/mcp/actions.ts`: Next.js server action handlers enforcing access code authorization, maintaining server status and configuration in local storage, and controlling MCP client lifecycles.
- `app/mcp/client.ts`: Wraps the Model Context Protocol SDK Client and StdioClientTransport to manage client connections, child process environments, tool listings, and request executions.
- `app/mcp/types.ts`: TypeScript types and Zod schemas defining JSON-RPC messages, MCP tool responses, client states, and server configurations.
- `app/mcp/logger.ts`: Provides ANSI-colored logging utilities customized for MCP operations.
- `app/mcp/utils.ts`: Provides helper functions to detect and extract MCP-specific JSON code blocks from message text.

## Public interface
- getClientsStatus(accessCode: string): Promise<Record<string, ServerStatusResponse>>
- getClientTools(clientId: string, accessCode: string)
- getAvailableClientsCount(accessCode: string)
- getAllTools(accessCode: string)
- initializeMcpSystem(accessCode: string)
- addMcpServer(clientId: string, config: ServerConfig, accessCode: string)
- pauseMcpServer(clientId: string, accessCode: string)
- resumeMcpServer(clientId: string, accessCode: string): Promise<void>
- createClient(id: string, config: ServerConfig): Promise<Client>
- removeClient(client: Client)
- listTools(client: Client): Promise<ListToolsResponse>
- executeRequest(client: Client, request: McpRequestMessage)
- isMcpJson(content: string)
- extractMcpJson(content: string)

## Dependencies
- @modelcontextprotocol/sdk/client/index.js
- @modelcontextprotocol/sdk/client/stdio.js
- zod
- spark-md5
- fs/promises
- path

## AI touchpoints [AI]
- `app/mcp/client.ts`
- `app/mcp/utils.ts`

## Open questions
- How does the chat streaming or execution layer wire tool output from executeRequest back into the conversation context?
- Where are isMcpEnabled and updateMcpConfig/getMcpConfigFromFile defined in actions.ts (portions were truncated)?
