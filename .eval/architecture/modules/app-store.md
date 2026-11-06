# Module: app/store [AI]

Manages client-side persisted state stores across application features including chat sessions, model access keys, general app and model configurations, prompt templates (masks/prompts), external OpenAPI/function plugins, Stable Diffusion tasks, synchronization (WebDAV/Upstash), and client versioning.

## Key files
- `app/store/access.ts`: Persists and validates provider API credentials, base URLs, access codes, and server configuration overrides.
- `app/store/chat.ts`: Manages conversation sessions, message history, token counts, tool execution states, and session summarization.
- `app/store/config.ts`: Maintains global client preferences, model configuration parameters (temperature, max tokens, etc.), and TTS/Realtime settings.
- `app/store/mask.ts`: Stores and manages customizable prompt templates (masks), their bound model configs, and builtin mask lists.
- `app/store/plugin.ts`: Handles dynamic OpenAPI tool plugins, generating function call definitions and invocations for chat agents.
- `app/store/prompt.ts`: Provides fuzzy search and persistence for user-defined and built-in text prompts via Fuse.js.
- `app/store/sd.ts`: Manages Stable Diffusion image generation task history, status, and direct API dispatch.
- `app/store/sync.ts`: Coordinates state backup, import/export, and remote synchronization across WebDAV and Upstash.
- `app/store/update.ts`: Monitors upstream repository updates and checks OpenAI usage quotas.
- `app/store/index.ts`: Module barrel export file re-exporting all primary stores.

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

## Dependencies
- nanoid
- fuse.js
- openapi-client-axios
- js-yaml
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
