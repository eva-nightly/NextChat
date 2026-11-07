# Module: app/client [AI]

Provides the client-side LLM provider abstraction and adapter layer, routing chat, speech, model listing, and tool-calling requests across multiple AI backends (including OpenAI, Azure, Anthropic, Google Gemini, DeepSeek, Qwen, Baidu Ernie, and others) while managing request streaming and cancellation controllers.

## Key files
- `app/client/api.ts`: Defines core LLM interfaces, request/response data contracts, authorization header generators, and the ClientApi factory that instantiates platform adapters based on the configured ModelProvider.
- `app/client/controller.ts`: Implements ChatControllerPool, maintaining active AbortController instances per session and message to allow cancelling streaming requests.
- `app/client/platforms/openai.ts`: Implements ChatGPTApi for OpenAI and Azure models, handling text chat, reasoning models (o1/o3/gpt-5 parameter adjustments), DALL-E image generation, speech-to-text, and tool execution.
- `app/client/platforms/anthropic.ts`: Implements ClaudeApi for Anthropic models, adapting message alternation rules, multimodal base64 image structures, and tool call schemas.
- `app/client/platforms/google.ts`: Implements GeminiProApi for Google Gemini models, transforming messages to inline parts and function declaration payloads.
- `app/client/platforms/deepseek.ts`: Implements DeepSeekApi supporting reasoning_content extraction in streaming chat responses.
- `app/client/platforms/alibaba.ts`: Implements QwenApi for DashScope/Qwen models, managing DashScope-specific SSE headers and multimodal payload structures.
- `app/client/platforms/baidu.ts`: Implements ErnieApi for Baidu Qianfan models, managing token authentication and custom SSE streaming via fetchEventSource.
- `app/client/platforms/glm.ts`: Implements ChatGLMApi supporting chat completion, CogView image generation, and CogVideo generation.

## Public interface
- ClientApi
- LLMApi
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
- ChatOptions
- LLMConfig
- RequestMessage
- SpeechOptions
- LLMModel
- LLMUsage

## Dependencies
- @fortaine/fetch-event-source
- nanoid
- lodash-es
- @/app/constant
- @/app/store
- @/app/config/client
- @/app/utils
- @/app/utils/chat
- @/app/utils/stream
- @/app/utils/cloudflare
- @/app/utils/format
- @/app/utils/model
- @/app/utils/baidu
- @/app/typing

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
