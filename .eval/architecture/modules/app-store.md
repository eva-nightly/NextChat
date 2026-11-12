# Module: app/store [AI]

Manages client-side persisted application state, including LLM chat sessions, access credentials and endpoints across AI providers, prompt templates, masks (system prompt configurations), plugin tool schemas, Stable Diffusion image generation tasks, sync mechanisms, and application updates.

## Key files
- `app/store/chat.ts`: Manages conversation sessions, message history, token counting, summarization model selection, context injection, and MCP tool handling.
- `app/store/access.ts`: Stores API access keys, custom base URLs, and access codes for multiple AI service providers, and synchronizes server configuration via /api/config.
- `app/store/config.ts`: Stores global app configurations, model lists, model inference parameters (temperature, max_tokens, etc.), TTS settings, and realtime configs.
- `app/store/mask.ts`: Stores and provides CRUD operations for conversational masks (preset system prompts and associated model configurations).
- `app/store/plugin.ts`: Manages OpenAPI-based tool plugins and registers client-callable function definitions for LLM tool use.
- `app/store/prompt.ts`: Stores user and builtin prompt templates with fuzzy search capabilities via Fuse.js.
- `app/store/sd.ts`: Manages Stable Diffusion image generation tasks and calls the Stability API.
- `app/store/sync.ts`: Manages cloud state backup and synchronization with WebDAV or Upstash.
- `app/store/update.ts`: Checks remote version updates and tracks LLM usage quotas.
- `app/store/index.ts`: Re-exports all store modules and types.

## Public interface
- useChatStore
- useAccessStore
- useAppConfig
- useMaskStore
- usePluginStore
- usePromptStore
- useSdStore
- useSyncStore
- useUpdateStore
- FunctionToolService
- SearchService
- createMessage
- createEmptyMask
- createEmptyPlugin

## Dependencies
- nanoid
- fuse.js
- openapi-client-axios
- js-yaml
- rt-client
- @/app/utils/indexedDB-storage

## AI touchpoints [AI]
- `app/store/access.ts`
- `app/store/chat.ts`
- `app/store/config.ts`
- `app/store/prompt.ts`
- `app/store/update.ts`
- `app/store/mask.ts`
- `app/store/plugin.ts`
- `app/store/sd.ts`

## Open questions
- The truncated portion of app/store/chat.ts cuts off additional session management and chat dispatch implementation details.
