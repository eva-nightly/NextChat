# Module: app/config [AI]

Manages configuration parsing and retrieval for build-time metadata, client-side runtime settings via document meta tags, and server-side environment variables across supported AI providers and proxy configurations.

## Key files
- `app/config/build.ts`: Retrieves build metadata including app version from Tauri config, git commit info, build mode, and default input templates.
- `app/config/client.ts`: Supplies configuration to client and server contexts by reading HTML meta tags on the client or delegating to build configuration on the server.
- `app/config/server.ts`: Parses server-side environment variables, authentication codes, allowed endpoints, and provider-specific credentials/URLs (OpenAI, Azure, Google, Anthropic, DeepSeek, etc.).

## Public interface
- getBuildConfig(): BuildConfig
- getClientConfig(): BuildConfig | undefined
- getServerSideConfig(): object
- type BuildConfig

## Dependencies
- spark-md5
- ../../src-tauri/tauri.conf.json
- ../constant
- ../utils/model
- child_process

## AI touchpoints [AI]
- `app/config/server.ts`

## Open questions
- app/config/server.ts is truncated near the end of the file (around line 214), so some configuration return properties at the tail end of getServerSideConfig may be cut off.
