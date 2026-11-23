# Module: app/store [AI]

Manages persistent client-side application state for NextChat, including chat sessions and history, model provider credentials and endpoints, prompt templates (masks), custom OpenAPI tool plugins, prompt search indexing, Stability AI generation, cloud synchronization (WebDAV/Upstash), and client update/usage tracking.

## Key files
- `app/store/access.ts`: State store for provider API keys, custom base URLs, access codes, and remote server configuration.
- `app/store/chat.ts`: Core state store for chat sessions, messages, token counting, MCP tool integration, and conversation summarization model resolution.
- `app/store/config.ts`: Application configuration store managing LLM parameters (temperature, penalties, history counts), TTS settings, Realtime API settings, and model lists.
- `app/store/mask.ts`: Store managing prompt templates (masks), custom personas, and their associated model configurations.
- `app/store/plugin.ts`: Manages OpenAPI tool plugins and converts them into function definitions and executable handlers for LLM tool calling.
- `app/store/prompt.ts`: Manages user and built-in prompt catalogs with fuzzy search via Fuse.js.
- `app/store/sd.ts`: Store for Stability AI image generation tasks, parameters, and generated outputs.
- `app/store/sync.ts`: Handles importing, exporting, and syncing local state with WebDAV and Upstash storage providers.
- `app/store/update.ts`: Checks for client updates against upstream release tags/commits and tracks OpenAI API usage balances.
- `app/store/index.ts`: Barrel file re-exporting stores.

## Public interface
- useAccessStore
- useChatStore
- createMessage
- BOT_HELLO
- DEFAULT_TOPIC
- useAppConfig
- DEFAULT_CONFIG
- limitNumber
- TTSConfigValidator
- ModalConfigValidator
- useMaskStore
- createEmptyMask
- usePluginStore
- FunctionToolService
- createEmptyPlugin
- usePromptStore
- SearchService
- useSdStore
- useSyncStore
- useUpdateStore

## Dependencies
- nanoid
- fuse.js
- js-yaml
- openapi-client-axios
- rt-client
- @/app/utils/indexedDB-storage
- @/app/utils/chat
- @/app/components/sd/sd-panel
- @/app/client/api
- @/app/constant

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
- `app/store/chat.ts` references `indexedDBStorage` but the file implementation was truncated in the provided snippet.
