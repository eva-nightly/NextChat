# Module: app/api [AI]

Provides server-side and edge API route handlers that proxy chat and model completion requests to various AI model providers (OpenAI, Azure, Anthropic, Google, DeepSeek, etc.) while enforcing server-side authentication, model access rules, header sanitization, streaming optimization, configuration exposure, and data persistence (Cloudflare KV, WebDAV, Upstash).

## Key files
- `app/api/[provider]/[...path]/route.ts`: Edge routing entrypoint that dispatches dynamic model provider API requests to their respective provider handlers or default proxy
- `app/api/auth.ts`: Validates user access codes / API keys and injects configured server-side provider API keys
- `app/api/common.ts`: Shared OpenAI and Azure request proxying logic, including Cloudflare AI Gateway integration, timeout handling, and model filtering
- `app/api/config/route.ts`: Public config route that serves non-sensitive server runtime configuration to the client
- `app/api/artifacts/route.ts`: Stores and retrieves shared artifact snippets using Cloudflare KV storage
- `app/api/webdav/[...path]/route.ts`: Secured WebDAV proxy endpoint for client data backup and sync
- `app/api/upstash/[action]/[...key]/route.ts`: Proxy endpoint for Upstash Redis KV storage actions (get/set)
- `app/api/tencent/route.ts`: Route handler proxying Tencent Hunyuan API requests with signature headers

## Public interface
- GET / POST app/api/[provider]/[...path]/route.ts
- GET / POST app/api/config/route.ts
- GET / POST app/api/artifacts/route.ts
- GET / POST app/api/tencent/route.ts
- GET / POST / OPTIONS app/api/upstash/[action]/[...key]/route.ts
- GET / PUT / OPTIONS app/api/webdav/[...path]/route.ts
- auth(req: NextRequest, modelProvider: ModelProvider)
- requestOpenai(req: NextRequest)

## Dependencies
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

## Where the code disagrees with the stack profile
- `app/api/[provider]/[...path]/route.ts`: Route handlers declare edge runtime (export const runtime = 'edge') instead of Node.js runtime

## Open questions
- Should error handling return consistent structured JSON errors across all provider handlers instead of mixing string messages and prettyObject responses?
- Why are some provider routes structured under dynamic [provider]/[...path] while Tencent is isolated under its own app/api/tencent/route.ts directory?
