# Module: app/store [AI]

Manages persistent and reactive client-side application state for NextChat, including chat sessions, model configurations, provider credentials and access control, prompt presets (masks), OpenAPI plugins, Stability AI image tasks, and cloud synchronization.

## Key files
- `app/store/access.ts`: Stores provider base URLs, API keys, access control tokens, and synchronizes server-side configuration.
- `app/store/chat.ts`: Manages chat sessions, messages, token counting, template variable interpolation, summarization model assignment, and MCP tool prompts.
- `app/store/config.ts`: Maintains global application settings, model parameter defaults (temperature, top_p, token limits), model catalogs, and TTS/realtime settings.
- `app/store/mask.ts`: Stores user and builtin prompt preset masks, configuring custom model parameters and context messages.
- `app/store/plugin.ts`: Parses OpenAPI plugin definitions and transforms them into callable tool functions and schemas for LLM tool calling.
- `app/store/prompt.ts`: Stores user prompts, loads builtin prompts, and provides fuzzy search capabilities via Fuse.js.
- `app/store/sd.ts`: Handles Stability AI generation tasks, parameters, image uploads, and status tracking.
- `app/store/sync.ts`: Coordinates state import/export and remote cloud synchronization via WebDAV and Upstash.
- `app/store/update.ts`: Tracks application version status, updates check via GitHub commits/tags, and queries LLM account usage.
- `app/store/index.ts`: Barrel exports for all state management stores.

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
- ModalConfigValidator
- TTSConfigValidator
- limitNumber

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
- _none_
