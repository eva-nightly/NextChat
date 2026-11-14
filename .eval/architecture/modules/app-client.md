# Module: app/client [AI]

Provides the unified client-side LLM interface, abort controller pooling, and provider-specific adapter classes to handle streaming, chat completions, speech, and tool invocation across multiple AI model backends.

## Key files
- `app/client/api.ts`: Defines the abstract LLMApi class, ClientApi dispatcher factory, headers/token helpers, and common chat/speech data types.
- `app/client/controller.ts`: Manages an in-memory pool of AbortController instances keyed by session and message ID to allow cancellation of active streaming requests.
- `app/client/platforms/ai302.ts`: Client adapter implementing LLMApi for 302.AI API endpoints with streaming and tool call parsing.
- `app/client/platforms/alibaba.ts`: Client adapter implementing LLMApi for Alibaba DashScope / Qwen API endpoints.
- `app/client/platforms/anthropic.ts`: Client adapter implementing LLMApi for Anthropic Claude chat completions and streaming.
- `app/client/platforms/baidu.ts`: Client adapter implementing LLMApi for Baidu Ernie Bot endpoints using Server-Sent Events.
- `app/client/platforms/bytedance.ts`: Client adapter implementing LLMApi for ByteDance Doubao API.
- `app/client/platforms/deepseek.ts`: Client adapter implementing LLMApi for DeepSeek chat models.
- `app/client/platforms/glm.ts`: Client adapter implementing LLMApi for ChatGLM chat, image generation, and video generation endpoints.
- `app/client/platforms/google.ts`: Client adapter implementing LLMApi for Google Gemini Pro models.
- `app/client/platforms/iflytek.ts`: Client adapter implementing LLMApi for iFlytek Spark models using SSE.
- `app/client/platforms/moonshot.ts`: Client adapter implementing LLMApi for Moonshot AI endpoints.
- `app/client/platforms/openai.ts`: Client adapter implementing LLMApi for OpenAI and Azure OpenAI APIs, covering chat, DALLE image generation, and TTS speech synthesis.
- `app/client/platforms/siliconflow.ts`: Client adapter implementing LLMApi for SiliconFlow models and dynamic model listing.
- `app/client/platforms/tencent.ts`: Client adapter implementing LLMApi for Tencent Hunyuan models using uppercase payload formatting and SSE.
- `app/client/platforms/xai.ts`: Client adapter implementing LLMApi for xAI Grok API endpoints.

## Public interface
- ClientApi
- LLMApi
- ChatControllerPool
- getBearerToken
- validString
- getHeaders
- ROLES
- Models
- TTSModels
- Ai302Api
- QwenApi
- ClaudeApi
- ErnieApi
- DoubaoApi
- DeepSeekApi
- ChatGLMApi
- GeminiProApi
- SparkApi
- MoonshotApi
- ChatGPTApi
- SiliconflowApi
- HunyuanApi
- XAIApi

## Dependencies
- @/app/store
- @/app/constant
- @/app/config/client
- @/app/utils
- @/app/utils/chat
- @/app/utils/stream
- @/app/utils/cloudflare
- @/app/utils/format
- @/app/utils/baidu
- @/app/utils/model
- @/app/typing
- @/app/locales
- @fortaine/fetch-event-source
- lodash-es/mapKeys
- lodash-es/mapValues
- lodash-es/isArray
- lodash-es/isObject
- nanoid

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
- `app/client/platforms/baidu.ts`
- `app/client/platforms/bytedance.ts`
- `app/client/platforms/alibaba.ts`
- `app/client/platforms/tencent.ts`

## Open questions
- Several adapter files (anthropic.ts, api.ts, baidu.ts, glm.ts, google.ts, openai.ts, siliconflow.ts) were truncated in the source view, leaving some methods like speech or error parsing partially unexamined.
- The speech method throws 'Method not implemented' for most non-OpenAI provider classes; should fallback or provider-specific speech synthesis be integrated?
- Many provider adapters return an empty array for models() rather than fetching dynamically or using DEFAULT_MODELS.
