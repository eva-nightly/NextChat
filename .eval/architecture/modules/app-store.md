# Module: app/store [AI]

Manages client-side persisted state for NextChat, including chat sessions, model provider credentials, application configurations, prompt templates, masks, plugins/tools, Stability AI image generation, sync, and version/usage tracking.

## Key files
- `app/store/access.ts`: State store for multi-provider API keys, base URLs, access codes, and remote server configuration fetching.
- `app/store/chat.ts`: State store for conversation sessions, chat messages, token calculations, prompt templating, model summarization routing, and MCP tool prompt injection.
- `app/store/config.ts`: Global application configuration store holding model parameters (temperature, max_tokens), TTS and Realtime API settings, and model lists.
- `app/store/mask.ts`: Store for managing custom and builtin prompt personas (masks) with specific model configs and system contexts.
- `app/store/plugin.ts`: Store for loading OpenAPI-based tool definitions and formatting them into LLM function tools.
- `app/store/prompt.ts`: Store and fuzzy search service for custom and builtin prompt templates.
- `app/store/sd.ts`: Store for running Stability AI image generation tasks and tracking drawing job history.
- `app/store/sync.ts`: Store for backing up and synchronizing local chat and application state via WebDAV, Upstash, or JSON export.
- `app/store/update.ts`: Store for checking application updates and polling LLM API subscription usage.
- `app/store/index.ts`: Re-exports access, chat, config, mask, plugin, prompt, sd, sync, and update stores.

## Public interface
- useAccessStore
- useChatStore
- createMessage
- useAppConfig
- DEFAULT_CONFIG
- ModalConfigValidator
- TTSConfigValidator
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
- fuse.js
- js-yaml
- nanoid
- openapi-client-axios
- rt-client
- app/client/api
- app/client/controller
- app/components/sd/sd-panel
- app/components/ui-lib
- app/config/client
- app/constant
- app/locales
- app/masks
- app/mcp/actions
- app/mcp/utils
- app/typing
- app/utils
- app/utils/chat
- app/utils/clone
- app/utils/cloud
- app/utils/format
- app/utils/indexedDB-storage
- app/utils/model
- app/utils/store
- app/utils/sync
- app/utils/token

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
- _none_
