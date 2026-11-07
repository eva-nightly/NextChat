# Module: app/client [AI]

Provides the client-side API abstraction and multi-provider LLM integrations (OpenAI, Anthropic, Google Gemini, Baidu, Alibaba, ByteDance, Tencent, DeepSeek, Moonshot, iFlytek, xAI, GLM, SiliconFlow, and 302.AI) for streaming chat, speech, tool calling, and session abort management.

## Key files
- `app/client/api.ts`: Defines the core LLMApi abstract class, ClientApi factory, shared types, headers/tokens resolution, and conversation sharing helper.
- `app/client/controller.ts`: Manages AbortController instances for active streaming chat requests across sessions.
- `app/client/platforms/openai.ts`: Implements OpenAI and Azure client handlers, DALL-E image generation, speech synthesis, and reasoning/thinking model payloads.
- `app/client/platforms/anthropic.ts`: Implements Claude API client handling message streaming, vision preprocessing, and tool execution.
- `app/client/platforms/google.ts`: Implements Google Gemini API streaming chat, multimodal payloads, and function declarations.
- `app/client/platforms/alibaba.ts`: Implements Alibaba DashScope Qwen chat API integration with SSE streaming and tool calling.
- `app/client/platforms/baidu.ts`: Implements Baidu Ernie API client using EventSource streaming with text animation.
- `app/client/platforms/bytedance.ts`: Implements ByteDance Doubao API integration supporting streaming and reasoning extraction.
- `app/client/platforms/deepseek.ts`: Implements DeepSeek chat API integration with reasoning content parsing and tool support.
- `app/client/platforms/glm.ts`: Implements Zhipu ChatGLM integration supporting chat, CogView image generation, and CogVideo video generation.
- `app/client/platforms/tencent.ts`: Implements Tencent Hunyuan chat API with key capitalization formatting and SSE streaming.
- `app/client/platforms/xai.ts`: Implements xAI Grok API client for streaming chat completions.
- `app/client/platforms/iflytek.ts`: Implements iFlytek Spark API streaming with EventSource.
- `app/client/platforms/moonshot.ts`: Implements Moonshot API integration for streaming chat requests.
- `app/client/platforms/siliconflow.ts`: Implements SiliconFlow model listing and chat completions API.
- `app/client/platforms/ai302.ts`: Implements 302.AI API client with reasoning parsing and model listing.

## Public interface
- ClientApi: Factory class instantiating the appropriate LLMApi platform implementation based on ModelProvider
- LLMApi: Abstract base class defining chat(), speech(), usage(), and models() contract
- ChatControllerPool: Singleton registry for managing and aborting active streaming request AbortControllers
- getHeaders(ignoreHeaders?: boolean): Generates HTTP request headers based on active session config and provider credentials
- getBearerToken(apiKey: string, noBearer?: boolean): Formats Bearer authorization token strings

## Dependencies
- @fortaine/fetch-event-source
- nanoid
- lodash-es
- ../constant
- ../store
- ../config/client
- ../utils
- ../utils/chat
- ../utils/stream
- ../utils/cloudflare
- ../utils/model
- ../utils/format
- ../utils/baidu
- ../../locales

## AI touchpoints [AI]
- `app/client/api.ts`
- `app/client/platforms/ai302.ts`
- `app/client/platforms/anthropic.ts`
- `app/client/platforms/deepseek.ts`
- `app/client/platforms/glm.ts`
- `app/client/platforms/google.ts`
- `app/client/platforms/iflytek.ts`
- `app/client/platforms/moonshot.ts`
- `app/client/platforms/openai.ts`
- `app/client/platforms/siliconflow.ts`
- `app/client/platforms/xai.ts`
- `app/client/platforms/alibaba.ts`
- `app/client/platforms/baidu.ts`
- `app/client/platforms/bytedance.ts`
- `app/client/platforms/tencent.ts`

## Open questions
- Several providers (Baidu, Alibaba, ByteDance, Tencent, DeepSeek, xAI, Moonshot, iFlytek) implement models() and usage() returning empty arrays or zeroes rather than querying provider endpoints.
- Baidu access token generation (getAccessToken) is bypassed in web mode due to CORS, relying solely on backend proxy routing.
