# Module: app/store [AI]

Provides persistent client-side state management for NextChat, covering chat sessions, prompt templates (masks), API access credentials across multiple LLM providers, OpenAPI tool plugins, application configuration, Stable Diffusion image generation, synchronization (WebDAV/Upstash), and client versioning.

## Key files
- `app/store/access.ts`: State store for API keys, custom endpoints, model provider credentials, and access control settings.
- `app/store/chat.ts`: State store for conversation sessions, message history, token estimation, summarization models, and MCP tool templates.
- `app/store/config.ts`: Application configuration store covering UI settings, active LLM model parameters (temperature, top_p, context compression), TTS, and realtime voice settings.
- `app/store/mask.ts`: Store for prompt templates (masks) including context prompts and model configuration overrides.
- `app/store/plugin.ts`: Manages OpenAPI client-based plugins, parsing OpenAPI specs into LLM function tool schemas and handling tool executions.
- `app/store/prompt.ts`: Prompt repository with fuzzy search indexing (Fuse.js) for user and built-in prompts.
- `app/store/sd.ts`: Store and API dispatch logic for Stable Diffusion image generation tasks.
- `app/store/sync.ts`: Backup and synchronization store handling WebDAV, Upstash cloud sync, and JSON import/export.
- `app/store/update.ts`: Store tracking client version updates, remote release commit checking, and token usage statistics.
- `app/store/index.ts`: Barrel export consolidating access, chat, config, mask, plugin, prompt, sd, sync, and update stores.

## Public interface
- useAccessStore
- useChatStore
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
- DEFAULT_CONFIG
- ModalConfigValidator
- TTSConfigValidator

## Dependencies
- nanoid
- openapi-client-axios
- js-yaml
- fuse.js
- rt-client
- ../constant
- ../client/api
- ../client/controller
- ../components/ui-lib
- ../locales
- ../utils/format
- ../utils/store
- ../utils/token
- ../utils/model
- ../utils/clone
- ../mcp/actions
- ../mcp/utils
- ../typing
- ../config/client
- ../masks
- ../utils
- ../utils/chat
- ../components/sd/sd-panel
- ../utils/sync
- ../utils/cloud

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
