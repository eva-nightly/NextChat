# Module: app/config [AI]

Manages configuration loading and environment variables across build-time, client-side, and server-side environments, including provider API keys, model availability rules, access codes, and build metadata.

## Key files
- `app/config/build.ts`: Retrieves build-time metadata such as package version from Tauri configuration, git commit info, build mode, and default input templates.
- `app/config/client.ts`: Extracts client-side build and runtime configuration from HTML document meta tags or falls back to build config on the server.
- `app/config/server.ts`: Parses server-side environment variables for model provider endpoints and API keys, access authentication codes, model overrides, and service integration settings.

## Public interface
- getBuildConfig()
- BuildConfig
- getClientConfig()
- getServerSideConfig()

## Dependencies
- spark-md5
- ../../src-tauri/tauri.conf.json
- ../constant
- ../utils/model

## AI touchpoints [AI]
- `app/config/server.ts`
- `app/config/build.ts`

## Open questions
- In app/config/server.ts, isTencent checks process.env.TENCENT_API_KEY even though the declared environment variable is TENCENT_SECRET_KEY.
