# Module: app/api [AI]

Provides Next.js edge route handlers and proxy dispatchers for authenticating, filtering, and relaying requests to multiple AI model providers, as well as handling artifact storage, client configuration exposure, and WebDAV/Upstash sync proxies.

## Key files
- `app/api/[provider]/[...path]/route.ts`: Edge dynamic route handler that multiplexes incoming API calls to specific model provider handlers or the generic proxy handler.
- `app/api/auth.ts`: Authentication and authorization middleware logic verifying user access codes, user API keys, and injecting server-configured API keys per model provider.
- `app/api/common.ts`: Shared request handler for OpenAI and Azure OpenAI endpoints, handling base URLs, Azure deployment mapping, Cloudflare AI Gateway routing, and model restriction checks.
- `app/api/config/route.ts`: Public edge route serving non-sensitive server configurations (e.g., model access flags, custom models) to the client UI.
- `app/api/artifacts/route.ts`: Edge route for storing and retrieving artifact data in Cloudflare KV store.
- `app/api/webdav/[...path]/route.ts`: SSRF-protected proxy route handler for client WebDAV backup synchronization.
- `app/api/upstash/[action]/[...key]/route.ts`: Proxy route handler restricted to Upstash REST endpoints for state synchronization.
- `app/api/tencent/route.ts`: Edge route handler for Tencent Hunyuan model requests using Tencent signing logic.

## Public interface
- GET /api/[provider]/[...path]
- POST /api/[provider]/[...path]
- GET /api/config
- POST /api/config
- GET /api/artifacts
- POST /api/artifacts
- GET /api/tencent
- POST /api/tencent
- GET /api/webdav/[...path]
- PUT /api/webdav/[...path]
- GET /api/upstash/[action]/[...key]
- POST /api/upstash/[action]/[...key]
- auth(req: NextRequest, modelProvider: ModelProvider)
- requestOpenai(req: NextRequest)

## Dependencies
- next/server
- spark-md5
- @/app/config/server
- @/app/constant
- @/app/utils/format
- @/app/utils/model
- @/app/utils/cloudflare
- @/app/utils/baidu
- @/app/utils/tencent
- @/app/client/platforms/openai

## AI touchpoints [AI]
- `app/api/302ai.ts`
- `app/api/[provider]/[...path]/route.ts`
- `app/api/alibaba.ts`
- `app/api/anthropic.ts`
- `app/api/auth.ts`
- `app/api/baidu.ts`
- `app/api/bytedance.ts`
- `app/api/common.ts`
- `app/api/deepseek.ts`
- `app/api/glm.ts`
- `app/api/google.ts`
- `app/api/iflytek.ts`
- `app/api/moonshot.ts`
- `app/api/openai.ts`
- `app/api/proxy.ts`
- `app/api/siliconflow.ts`
- `app/api/stability.ts`
- `app/api/tencent/route.ts`
- `app/api/xai.ts`
- `app/api/azure.ts`

## Where the code disagrees with the stack profile
- `app/api/[provider]/[...path]/route.ts`: The stack definition specifies runtime: node for the Next.js server code, but the route handlers explicitly configure export const runtime = 'edge'.

## Open questions
- _none_
