# Module: app/store [AI]

Manages client-side persisted application state using custom Zustand-like persist stores for user access credentials, chat sessions and message history, global app/model configuration, masks (prompt templates), OpenAPI plugins/tool integrations, prompt libraries, Stability AI image generation tasks, remote WebDAV/Upstash state synchronization, and application update/usage checking.

## Key files
- `app/store/access.ts`: Persists and validates provider API keys, custom base URLs, access codes, and fetches server-side runtime configuration.
- `app/store/chat.ts`: Manages chat sessions, message histories, token statistics, prompt templating, and MCP tool context formatting.
- `app/store/config.ts`: Stores global application settings including default LLM parameters, TTS options, realtime voice configs, and available model listings.
- `app/store/mask.ts`: Handles prompt template (mask) creation, deletion, search, and merging with builtin masks.
- `app/store/plugin.ts`: Manages OpenAPI schema plugins and converts them into callable function tools via FunctionToolService.
- `app/store/prompt.ts`: Stores custom prompts, loads builtin localized prompt libraries, and provides Fuzzy search indexing via Fuse.js.
- `app/store/sd.ts`: Manages Stability AI text-to-image generation tasks, request parameters, and image blob processing.
- `app/store/sync.ts`: Provides manual and automated state synchronization across devices using WebDAV or Upstash backends, plus JSON backup import/export.
- `app/store/update.ts`: Checks GitHub commits/tags for application updates and queries OpenAI account usage statistics.
- `app/store/index.ts`: Module barrel file re-exporting access, chat, config, mask, plugin, and update stores.

## Public interface
- useAccessStore
- useChatStore
- createMessage
- BOT_HELLO
- DEFAULT_TOPIC
- useAppConfig
- SubmitKey
- Theme
- DEFAULT_CONFIG
- limitNumber
- TTSConfigValidator
- ModalConfigValidator
- useMaskStore
- createEmptyMask
- DEFAULT_MASK_AVATAR
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
- openapi-client-axios
- js-yaml
- fuse.js
- rt-client
- ../constant
- ../client/api
- ../config/client
- ../utils/store
- ../utils/clone
- ../utils/model
- ../utils/token
- ../utils/format
- ../locales
- ../mcp/actions
- ../mcp/utils
- ../utils/sync
- ../utils/cloud
- ../masks
- ../components/ui-lib
- ../components/sd/sd-panel

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
- The chat.ts file was truncated in the provided snippet; internal methods for sending messages, summarizing history, and handling streaming responses inside useChatStore could not be fully inspected.
