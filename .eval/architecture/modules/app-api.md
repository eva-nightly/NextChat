# Module: app/api [AI]

Provides Edge API route handlers and proxy endpoints to authenticate, validate, filter, and stream requests between client chat interfaces and various LLM/AI model providers, alongside supporting endpoints for configuration, Cloudflare KV artifacts storage, Upstash Redis caching, and WebDAV synchronization.

## Key files
- `app/api/[provider]/[...path]/route.ts`: Dynamic catch-all Edge route dispatcher routing LLM API calls to provider-specific handler functions.
- `app/api/auth.ts`: Access control and authentication helper validating user access codes and injecting configured server-side provider API keys.
- `app/api/common.ts`: Shared proxy forwarding engine for OpenAI and Azure OpenAI endpoints, handling custom model filtering, streaming headers, and Cloudflare AI Gateway routing.
- `app/api/config/route.ts`: Public configuration endpoint delivering non-sensitive server settings and model availability flags to the frontend.
- `app/api/artifacts/route.ts`: Cloudflare KV storage endpoint for persisting and fetching generated code artifacts.
- `app/api/tencent/route.ts`: Edge route handler for Tencent Hunyuan model proxying with custom authorization header generation.
- `app/api/upstash/[action]/[...key]/route.ts`: Proxy endpoint allowing validated get and set actions against Upstash Redis instances.
- `app/api/webdav/[...path]/route.ts`: SSRF-protected WebDAV proxy facilitating sync operations for backup files.

## Public interface
- GET/POST /api/[provider]/[...path]
- GET/POST /api/config
- GET/POST /api/artifacts
- GET/POST /api/tencent
- GET/POST/OPTIONS /api/upstash/[action]/[...key]
- GET/PUT/OPTIONS /api/webdav/[...path]
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

## Where the code disagrees with the stack profile
- `app/api/[provider]/[...path]/route.ts`: Stack specifies server runtime as node, but route handlers explicitly declare export const runtime = 'edge'

## Open questions
- Why is the Tencent route mounted at its own separate /api/tencent/route.ts while other providers are handled through the catch-all /api/[provider]/[...path]/route.ts dispatcher?
- Why are custom model filtering checks parsing the request body as text and cloning it in memory on Edge runtime, which could cause latency on large multimodal payloads?
