# Module: app/store [AI]

Manages client-side persistent state for NextChat, including AI model and provider configurations, access credentials, chat sessions and message histories, system prompts (masks), plugin/tool calling, cloud synchronization, and update/usage metrics.

## Key files
- `app/store/access.ts`: Manages API keys, custom endpoints, access control codes, and provider settings across supported LLM backends.
- `app/store/chat.ts`: Manages chat sessions, message state, conversation summarization, and prompt/MCP tool template interpolation.
- `app/store/config.ts`: Manages global application settings, model parameter defaults (temperature, top_p, max_tokens), available LLM lists, TTS, and realtime voice configuration.
- `app/store/mask.ts`: Manages system prompts (masks), preset contextual personas, and mask-specific model overrides.
- `app/store/plugin.ts`: Converts OpenAPI specifications into tool and function-calling schemas usable by LLMs.
- `app/store/prompt.ts`: Stores user and builtin prompt templates, providing fuzzy search via Fuse.js.
- `app/store/sd.ts`: Coordinates Stability AI image generation tasks, models, parameters, and results.
- `app/store/sync.ts`: Handles synchronization and export/import of local app state across WebDAV and Upstash storage.
- `app/store/update.ts`: Tracks application versioning and fetches OpenAI API usage and quota data.
- `app/store/index.ts`: Re-exports all store modules for unified consumption.

## Public interface
- useAccessStore
- useChatStore
- createMessage
- useAppConfig
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
- app/store/chat.ts was truncated; are there additional actions or cleanup routines implemented in the rest of useChatStore?
