# Module: app/client [AI]

Provides a unified client-side LLM adapter layer and API client for dispatching streaming and non-streaming chat completions, speech synthesis, image/video generation, and tool calls across multiple AI providers (OpenAI, Anthropic, Google, DeepSeek, Baidu, Alibaba, Tencent, ByteDance, and others), while managing active stream abort controllers.

## Key files
- `app/client/api.ts`: Defines core abstractions (LLMApi, ClientApi), request/response interfaces (ChatOptions, LLMConfig), and authorization header resolution utilities across providers.
- `app/client/controller.ts`: Manages AbortController instances in ChatControllerPool to track, abort, and cancel active message streams.
- `app/client/platforms/openai.ts`: Implements ChatGPTApi for OpenAI and Azure providers, handling chat completions, tool execution, DALL-E image generation, and text-to-speech.
- `app/client/platforms/anthropic.ts`: Implements ClaudeApi for Anthropic Claude models, handling prompt mapping, vision attachments, and tool use streaming.
- `app/client/platforms/google.ts`: Implements GeminiProApi for Google Gemini models, supporting multimodal input, tool declarations, and safety settings.
- `app/client/platforms/glm.ts`: Implements ChatGLMApi for Zhipu ChatGLM, handling chat completions, CogView image generation, and CogVideo generation.
- `app/client/platforms/deepseek.ts`: Implements DeepSeekApi for DeepSeek models with reasoning/thinking stream extraction.
- `app/client/platforms/alibaba.ts`: Implements QwenApi for Alibaba DashScope / Qwen models.
- `app/client/platforms/baidu.ts`: Implements ErnieApi for Baidu Qianfan / Wenxin models.
- `app/client/platforms/bytedance.ts`: Implements DoubaoApi for ByteDance Doubao models.
- `app/client/platforms/tencent.ts`: Implements HunyuanApi for Tencent Hunyuan models.
- `app/client/platforms/iflytek.ts`: Implements SparkApi for iFlytek Spark models.
- `app/client/platforms/moonshot.ts`: Implements MoonshotApi for Moonshot Kimi models.
- `app/client/platforms/xai.ts`: Implements XAIApi for xAI Grok models.
- `app/client/platforms/siliconflow.ts`: Implements SiliconflowApi for SiliconFlow model gateway.
- `app/client/platforms/ai302.ts`: Implements Ai302Api for 302.AI aggregator models.

## Public interface
- ClientApi
- LLMApi
- ChatControllerPool
- ChatGPTApi
- ClaudeApi
- GeminiProApi
- ErnieApi
- DoubaoApi
- QwenApi
- HunyuanApi
- MoonshotApi
- SparkApi
- DeepSeekApi
- XAIApi
- ChatGLMApi
- SiliconflowApi
- Ai302Api
- getBearerToken
- getHeaders
- validString

## Dependencies
- @fortaine/fetch-event-source
- nanoid
- lodash-es/mapKeys
- lodash-es/mapValues
- lodash-es/isArray
- lodash-es/isObject
- @/app/constant
- @/app/store
- @/app/config/client
- @/app/utils
- @/app/utils/chat
- @/app/utils/stream
- @/app/utils/format
- @/app/utils/baidu
- @/app/utils/cloudflare
- @/app/typing
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
- Most provider platforms (Anthropic, Gemini, Qwen, Baidu, Doubao, etc.) throw 'Method not implemented' for speech() instead of providing TTS capabilities or returning a standard fallback.
- Multiple platform implementations (DeepSeek, Doubao, Moonshot, Spark, Tencent, xAI) return an empty array for models() instead of dynamic model discovery.
