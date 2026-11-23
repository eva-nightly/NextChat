# Module: app/api [AI]

Server-side API proxy, authentication, and routing layer that validates user access codes, injects server API keys, enforces model restrictions, and proxies streaming chat and inference requests to various LLM providers (OpenAI, Azure, Anthropic, Google Gemini, DeepSeek, etc.) alongside backup/artifact persistence endpoints.

## Key files
- `app/api/[provider]/[...path]/route.ts`: Dynamic Next.js Edge route dispatcher that routes incoming client model requests to provider-specific proxy handlers.
- `app/api/auth.ts`: Authentication helper that verifies client access codes against server config hashes or injects provider-specific system API keys when user keys are omitted.
- `app/api/common.ts`: Shared OpenAI and Azure forwarding engine that applies Cloudflare AI Gateway URL rewriting, org headers, and custom model availability filtering.
- `app/api/config/route.ts`: Public server configuration route exposing client-safe settings such as authentication requirements and model availability.
- `app/api/artifacts/route.ts`: Cloudflare KV storage handler for saving and fetching hashed code/artifact data.
- `app/api/webdav/[...path]/route.ts`: SSRF-protected WebDAV proxy for backing up and synchronizing user conversation data.
- `app/api/tencent/route.ts`: Tencent Hunyuan model gateway providing custom request header signing.

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
- GET /api/webdav/[...path]
- PUT /api/webdav/[...path]
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
- `app/api/[provider]/[...path]/route.ts`: Stack specifies runtime as 'node', but the route handlers explicitly set 'export const runtime = "edge";'.

## Open questions
- Are long-lived upstream streaming connections terminated cleanly on edge worker abort timeouts across all provider handlers?
