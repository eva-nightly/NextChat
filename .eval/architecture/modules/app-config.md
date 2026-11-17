# Module: app/config [AI]

Manages configuration across build, client, and server environments, including build metadata extraction, multi-provider LLM credentials, access code hashing, and model availability settings.

## Key files
- `app/config/build.ts`: Extracts build-time metadata such as version from tauri.conf.json, git commit information, build mode, and default input templates.
- `app/config/client.ts`: Retrieves configuration in client and SSR contexts, extracting values from document meta tags or build config.
- `app/config/server.ts`: Loads and parses server-side environment variables, API keys for various LLM providers, model restriction settings, access codes, and endpoints.

## Public interface
- getBuildConfig
- type BuildConfig
- getClientConfig
- getServerSideConfig

## Dependencies
- ../../src-tauri/tauri.conf.json
- ../constant
- ../utils/model
- spark-md5
- child_process

## AI touchpoints [AI]
- `app/config/server.ts`

## Open questions
- app/config/server.ts was truncated at the end of the provided snippet, hiding any additional configuration properties returned by getServerSideConfig.
