# Module: app/client [AI]

Provides client-side API abstractions, abort controller management, and multi-provider LLM adapters (including OpenAI, Azure, Google Gemini, Anthropic Claude, Baidu Ernie, ByteDance Doubao, Alibaba Qwen, Tencent Hunyuan, Moonshot, iFlytek Spark, DeepSeek, xAI, ChatGLM, SiliconFlow, and 302.AI) for streaming chat, speech generation, and model metadata querying.

## Key files
- `app/client/api.ts`: Defines core LLM interfaces (LLMApi, ChatOptions, LLMConfig), request/response types, ClientApi factory class, header resolution (getHeaders), and conversation sharing functionality.
- `app/client/controller.ts`: Implements ChatControllerPool to track, abort, and clean up active streaming AbortController instances across sessions.
- `app/client/platforms/openai.ts`: Implements ChatGPTApi handling OpenAI and Azure chat completions, reasoning model adjustments (o1/o3/gpt-5), DALL-E image generation, and text-to-speech.
- `app/client/platforms/anthropic.ts`: Implements ClaudeApi handling Anthropic Claude chat requests, vision/multimodal block mapping, refusal handling, and tool execution.
- `app/client/platforms/google.ts`: Implements GeminiProApi formatting multimodal input parts and safety settings for Google Gemini chat endpoints.
- `app/client/platforms/alibaba.ts`: Implements QwenApi for Alibaba DashScope chat streaming and tool calling.
- `app/client/platforms/baidu.ts`: Implements ErnieApi with custom message sequencing, token fetching, and animated SSE stream parsing.
- `app/client/platforms/bytedance.ts`: Implements DoubaoApi for ByteDance chat and vision inference.
- `app/client/platforms/deepseek.ts`: Implements DeepSeekApi handling DeepSeek chat requests and thinking/reasoning stream chunk separation.
- `app/client/platforms/glm.ts`: Implements ChatGLMApi dispatching to chat, image (cogview), or video (cogvideo) generation endpoints.
- `app/client/platforms/iflytek.ts`: Implements SparkApi for iFlytek Spark chat streaming with smooth text animation.
- `app/client/platforms/moonshot.ts`: Implements MoonshotApi for Moonshot AI chat completions.
- `app/client/platforms/siliconflow.ts`: Implements SiliconflowApi supporting model listing, thinking chunk streams, and tool calling.
- `app/client/platforms/tencent.ts`: Implements HunyuanApi for Tencent Hunyuan models with key capitalization and SSE stream handling.
- `app/client/platforms/xai.ts`: Implements XAIApi for xAI model inference.
- `app/client/platforms/ai302.ts`: Implements Ai302Api for 302.AI proxy chat streaming and model discovery.

## Public interface
- LLMApi (abstract class)
- ClientApi (class)
- ChatControllerPool
- getHeaders(ignoreHeaders?: boolean)
- getBearerToken(apiKey: string, noBearer?: boolean)
- validString(x: string)
- ChatGPTApi
- GeminiProApi
- ClaudeApi
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

## Dependencies
- @/app/config/client
- @/app/constant
- @/app/store
- @/app/utils
- @/app/utils/chat
- @/app/utils/stream
- @/app/utils/cloudflare
- @/app/utils/format
- @/app/utils/baidu
- @/app/utils/model
- @/app/typing
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
- `app/client/platforms/alibaba.ts`
- `app/client/platforms/baidu.ts`
- `app/client/platforms/bytedance.ts`
- `app/client/platforms/tencent.ts`

## Open questions
- _none_
