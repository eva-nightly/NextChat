# Module: app/config [AI]

Manages configuration across build, client, and server environments, including reading Git/Tauri build metadata, injecting client-side runtime config from HTML meta tags, and resolving multi-provider LLM API keys and model parameters from environment variables.

## Key files
- `app/config/build.ts`: Extracts build-time metadata such as package version from Tauri configuration, git commit hash/date, build mode, and default input templates.
- `app/config/client.ts`: Provides client-safe configuration by reading serialized config from document meta tags in the browser or falling back to build config on the server.
- `app/config/server.ts`: Parses server-side environment variables, API keys, access control MD5 hashes, proxy settings, and multi-provider LLM endpoint configurations.

## Public interface
- getBuildConfig(): BuildConfig
- type BuildConfig
- getClientConfig(): BuildConfig | undefined
- getServerSideConfig(): object

## Dependencies
- spark-md5
- child_process
- ../../src-tauri/tauri.conf.json
- ../constant
- ../utils/model

## AI touchpoints [AI]
- `app/config/server.ts`

## Open questions
- app/config/server.ts was truncated at the end of the provided snippet, hiding full property listings and remaining helper logic (e.g. ENABLE_BALANCE_QUERY).
