# Module: app/config [AI]

Manages configuration across build, client, and server environments, providing build metadata, client-accessible configuration via meta tags, and server-side runtime settings for model provider endpoints, API keys, and access controls.

## Key files
- `app/config/build.ts`: Retrieves build-time metadata such as package version from Tauri configuration, git commit hash/date, build modes, and input templates.
- `app/config/client.ts`: Resolves configuration for the client by reading from the HTML meta tag 'config' in the browser or falling back to build config on the server.
- `app/config/server.ts`: Parses and provides server-side environment variables for AI model providers, API keys with rotation support, authentication access codes, and model constraints.

## Public interface
- getBuildConfig
- BuildConfig
- getClientConfig
- getServerSideConfig

## Dependencies
- spark-md5
- ../../src-tauri/tauri.conf.json
- ../constant
- ../utils/model
- child_process

## AI touchpoints [AI]
- `app/config/server.ts`

## Open questions
- app/config/server.ts is truncated near the end of the getServerSideConfig function, leaving the full list of exported properties incomplete.
