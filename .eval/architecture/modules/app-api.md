# Module: app/api [AI]

Server-side API layer providing proxying, authentication, rate/model access filtering, and configuration for multiple AI model providers (OpenAI, Anthropic, Google, Azure, DeepSeek, xAI, ByteDance, Alibaba, Baidu, Moonshot, SiliconFlow, 302.AI, iFlyTek, Stability, Tencent) as well as data sync proxies (WebDAV, Upstash) and KV artifact storage.

## Key files
- `app/api/[provider]/[...path]/route.ts`: Edge route dispatcher mapping dynamic provider paths to their corresponding provider handler functions.
- `app/api/auth.ts`: Validates user access codes/API keys and conditionally injects server-configured system API keys per provider.
- `app/api/common.ts`: Shared request handler for OpenAI and Azure requests, managing Cloudflare AI gateway routing, custom model validation, and header hygiene.
- `app/api/config/route.ts`: Exposes non-sensitive server configuration to the client UI (danger config flags, default models, custom model settings).
- `app/api/artifacts/route.ts`: Stores and retrieves code artifacts in Cloudflare KV storage.
- `app/api/webdav/[...path]/route.ts`: SSRF-protected WebDAV proxy for backing up chat data to allowed storage servers.
- `app/api/upstash/[action]/[...key]/route.ts`: Restricted proxy for Upstash Redis KV operations (get/set).
- `app/api/openai.ts`: OpenAI proxy handler enforcing route permissions and filtering model listings when GPT-4 is disabled.
- `app/api/anthropic.ts`: Anthropic proxy handler with allowed path filtering and Cloudflare AI gateway support.
- `app/api/google.ts`: Google Gemini proxy handler managing server and client API key authorization and SSE streams.
- `app/api/tencent/route.ts`: Tencent Hunyuan handler computing required signature headers via getHeader.
- `app/api/baidu.ts`: Baidu Ernie proxy handler acquiring access tokens and routing requests.
- `app/api/proxy.ts`: Generic fallback proxy routing arbitrary base URLs from x-base-url header.

## Public interface
- POST /api/[provider]/[...path]
- GET /api/[provider]/[...path]
- GET /api/config
- POST /api/config
- GET /api/artifacts
- POST /api/artifacts
- GET /api/tencent
- POST /api/tencent
- GET /api/upstash/[action]/[...key]
- POST /api/upstash/[action]/[...key]
- OPTIONS /api/upstash/[action]/[...key]
- GET /api/webdav/[...path]
- PUT /api/webdav/[...path]
- OPTIONS /api/webdav/[...path]
- auth(req: NextRequest, modelProvider: ModelProvider)

## Dependencies
- spark-md5
- next/server
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
- `app/api/[provider]/[...path]/route.ts`: The stack description stated server code runtime is 'node', but route handlers in this directory explicitly export `export const runtime = 'edge'` (e.g. [provider]/[...path]/route.ts, artifacts/route.ts, config/route.ts, google.ts, tencent/route.ts, upstash/[action]/[...key]/route.ts, webdav/[...path]/route.ts).

## Open questions
- Why does app/api/tencent/route.ts live as a standalone route handler instead of being routed through app/api/[provider]/[...path]/route.ts like other providers?
- Should proxy.ts allow DALL-E requests when apiKey is not set or restrict them with more structured error formats matching other handlers?
