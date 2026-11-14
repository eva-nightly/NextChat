# Module: app/api [AI]

Provides Edge-based Next.js route handlers and proxy adapters for routing requests to various LLM providers (OpenAI, Anthropic, Google, DeepSeek, Azure, Alibaba, Baidu, Tencent, etc.), authenticating user access codes or injecting server API keys, filtering unauthorized models, storing shared artifacts via Cloudflare KV, and proxying sync backups via WebDAV and Upstash.

## Key files
- `app/api/[provider]/[...path]/route.ts`: Dynamic Next.js Edge route dispatcher delegating API requests to provider-specific proxy handlers based on the path parameter.
- `app/api/auth.ts`: Authentication middleware logic that validates access codes or user-supplied keys and injects system API keys per ModelProvider.
- `app/api/common.ts`: Core OpenAI and Azure forwarding proxy that applies Cloudflare AI Gateway URLs, enforces custom model filtering, and strips buffering/auth headers.
- `app/api/config/route.ts`: Route returning non-sensitive server configuration and feature flags to the client.
- `app/api/artifacts/route.ts`: Cloudflare KV-backed endpoint for saving and retrieving code/chat artifacts.
- `app/api/webdav/[...path]/route.ts`: Validated reverse proxy for WebDAV backup and synchronization storage.
- `app/api/upstash/[action]/[...key]/route.ts`: Reverse proxy for Upstash Redis cloud backup operations.
- `app/api/openai.ts`: OpenAI endpoint handler filtering model list endpoints based on server configuration.
- `app/api/tencent/route.ts`: Tencent Hunyuan model route handler with request signature header injection.

## Public interface
- GET / POST /api/[provider]/[...path]
- GET / POST /api/artifacts
- GET / POST /api/config
- GET / POST /api/tencent
- GET / POST / OPTIONS /api/upstash/[action]/[...key]
- GET / PUT / OPTIONS /api/webdav/[...path]
- auth(req: NextRequest, modelProvider: ModelProvider): { error: boolean; msg?: string }
- requestOpenai(req: NextRequest): Promise<Response>

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
- `app/api/[provider]/[...path]/route.ts`: The scan stack specifies runtime as 'node', but route handlers explicitly export `runtime = 'edge'`.

## Open questions
- Proxy handlers enforce a hardcoded 10-minute timeout via AbortController; could this cut off long-running streaming or reasoning requests?
- WebDAV and Upstash endpoints strictly restrict methods and target hostnames; are additional storage backends planned or supported?
