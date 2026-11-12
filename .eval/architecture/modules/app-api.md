# Module: app/api [AI]

Provides Next.js edge route handlers and proxy controllers to authenticate, filter, and forward LLM requests to various AI model providers (OpenAI, Anthropic, Google, Azure, DeepSeek, ByteDance, Baidu, Alibaba, etc.) and handle auxiliary operations like artifacts KV storage, Upstash proxying, WebDAV synchronization, and server configuration delivery.

## Key files
- `app/api/[provider]/[...path]/route.ts`: Dynamic catch-all Edge route handler dispatching incoming requests to provider-specific proxy handlers based on the provider path parameter.
- `app/api/auth.ts`: Validates client access codes and injects system-configured API keys into request headers if user API keys are missing or hidden.
- `app/api/common.ts`: Common OpenAI and Azure proxy requester that applies timeouts, handles Cloudflare AI Gateway routing, enforces custom model filtering, and sanitizes response headers.
- `app/api/openai.ts`: OpenAI proxy handler enforcing path permissions, authenticating requests, forwarding API calls, and filtering GPT-4/o1/o3 models from the model listing if disabled.
- `app/api/anthropic.ts`: Anthropic Claude proxy handler validating chat paths, configuring Anthropic headers, and forwarding requests via fetch.
- `app/api/google.ts`: Google Gemini proxy handler managing API key resolution and SSE query parameters.
- `app/api/config/route.ts`: Edge route handler returning safe public server-side configuration settings to the client.
- `app/api/artifacts/route.ts`: Cloudflare KV storage handler for saving and fetching artifact code snippets by hash.
- `app/api/webdav/[...path]/route.ts`: WebDAV proxy handler for synchronizing backup JSON files with allowed WebDAV endpoints.
- `app/api/upstash/[action]/[...key]/route.ts`: Proxy handler for Upstash Redis get and set actions restricted to .upstash.io endpoints.

## Public interface
- GET /api/[provider]/[...path]
- POST /api/[provider]/[...path]
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
- auth(req: NextRequest, modelProvider: ModelProvider): { error: boolean; msg?: string }

## Dependencies
- next/server
- spark-md5
- @/app/constant
- @/app/config/server
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
- `app/api/[provider]/[...path]/route.ts`: The stack description indicates the runtime is 'node', but multiple route handlers explicitly specify `export const runtime = 'edge'` (e.g., app/api/[provider]/[...path]/route.ts, app/api/artifacts/route.ts, app/api/config/route.ts, app/api/google.ts, app/api/tencent/route.ts, app/api/upstash/[action]/[...key]/route.ts, app/api/webdav/[...path]/route.ts).

## Open questions
- Why are several provider route handlers marked with runtime = 'edge' (such as Google, Tencent, artifacts, config) while the shared provider dispatcher handles all other providers under the dynamic route's runtime?
- Should non-OpenAI endpoints sanitize or inspect Content-Encoding headers in the same manner as the OpenAI/proxy routes to prevent compression mismatch issues with reverse proxies or browsers?
