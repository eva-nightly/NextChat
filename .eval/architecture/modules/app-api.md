# Module: app/api [AI]

Provides server-side API proxying, access authentication, model filtering, and remote storage sync for various LLM providers (OpenAI, Azure, Anthropic, Google Gemini, Alibaba, Baidu, ByteDance, DeepSeek, GLM, iFlytek, Moonshot, SiliconFlow, Stability, Tencent, xAI, 302.AI) as well as WebDAV, Upstash, and Cloudflare KV artifacts.

## Key files
- `app/api/[provider]/[...path]/route.ts`: Dynamic Next.js Edge route dispatcher routing LLM provider requests to dedicated proxy handlers
- `app/api/auth.ts`: Validates user access codes or injects configured server-side provider API keys
- `app/api/common.ts`: Core proxy logic for OpenAI and Azure OpenAI endpoints, managing custom model filters, organization headers, and Cloudflare AI gateway routing
- `app/api/config/route.ts`: Serves public client configuration including model availability, access restrictions, and feature flags
- `app/api/artifacts/route.ts`: Stores and retrieves code/artifact data in Cloudflare KV storage
- `app/api/webdav/[...path]/route.ts`: Proxies client WebDAV sync requests with endpoint validation and path whitelisting
- `app/api/upstash/[action]/[...key]/route.ts`: Proxies client Redis get/set backup requests to Upstash endpoints
- `app/api/tencent/route.ts`: Dedicated route handler and request signer for Tencent Hunyuan LLM

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
- `app/api/azure.ts`

## Where the code disagrees with the stack profile
- `app/api/[provider]/[...path]/route.ts`: The stack states runtime is 'node', but route handlers in app/api explicitly specify 'export const runtime = "edge";'

## Open questions
- Why is the Tencent route mounted at its own dedicated route (`app/api/tencent/route.ts`) rather than being handled under `app/api/[provider]/[...path]/route.ts` like other providers?
