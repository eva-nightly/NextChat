# Module: app/config [AI]

Manages build-time, client-side, and server-side configurations, including environment variable resolution, API key selection/rotation, provider URL configurations, access code verification hashing, and client meta-tag config hydration.

## Key files
- `app/config/build.ts`: Retrieves build metadata including Tauri version, Git commit hash/date, build modes, and default input templates.
- `app/config/client.ts`: Hydrates configuration across environments by reading HTML meta tags in browser contexts or invoking build config on the server.
- `app/config/server.ts`: Reads and processes server-side environment variables, API keys, provider base URLs, access codes (MD5 hashed), and model availability flags.

## Public interface
- getBuildConfig()
- type BuildConfig
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
- _none_
