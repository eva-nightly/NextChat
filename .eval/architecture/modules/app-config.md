# Module: app/config [AI]

Manages configuration loading and environment parsing across build-time, client-side, and server-side runtimes, handling provider API keys, endpoint URLs, model access settings, and version metadata.

## Key files
- `app/config/build.ts`: Extracts build-time metadata including Tauri package version, git commit hash and timestamp, build mode, and default input template.
- `app/config/client.ts`: Retrieves client-accessible build configuration from the HTML meta tag on the browser or directly via build config in server environments.
- `app/config/server.ts`: Parses and structures server-side environment variables, managing LLM provider API credentials, base URLs, access code validation hashes, and feature flags.

## Public interface
- getBuildConfig()
- type BuildConfig
- getClientConfig()
- getServerSideConfig()

## Dependencies
- spark-md5
- child_process
- ../../src-tauri/tauri.conf.json
- ../constant
- ../utils/model

## AI touchpoints [AI]
- `app/config/server.ts`

## Open questions
- app/config/server.ts was truncated in the provided source, leaving trailing properties like hideBalanceQuery incomplete.
