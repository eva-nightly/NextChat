# Module: app/config [AI]

Manages build-time, client-side, and server-side configuration, including environment variables, API keys, and model settings for multiple LLM providers.

## Key files
- `app/config/build.ts`: Extracts build metadata, application version from Tauri config, git commit info, and prompt input templates.
- `app/config/client.ts`: Retrieves configuration in browser environments from meta tags or falls back to build config on the server.
- `app/config/server.ts`: Parses server-side environment variables, API keys (with random load balancing), access control codes, and provider configurations for numerous LLM backends.

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
- `app/config/build.ts`

## Open questions
- In app/config/server.ts, why does isTencent check process.env.TENCENT_API_KEY when the keys set are TENCENT_SECRET_KEY and TENCENT_SECRET_ID?
- Why does server.ts log plain text API keys to the console in getApiKey?
