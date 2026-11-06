# Module: app/client [AI]

Provides the unified client-side LLM provider abstraction, request streaming, tool-calling pipelines, cancellation controller management, and platform-specific API adapters for talking to diverse AI model providers.

## Key files
- `app/client/api.ts`: Defines the abstract LLMApi base class, common interfaces (ChatOptions, RequestMessage, LLMConfig), ClientApi factory, and request authorization header generation.
- `app/client/controller.ts`: Manages AbortController instances in ChatControllerPool to stop active streaming responses per session and message.
- `app/client/platforms/openai.ts`: ChatGPTApi adapter handling OpenAI and Azure chat completions, streaming, DALL-E image generation, and TTS speech generation.
- `app/client/platforms/anthropic.ts`: ClaudeApi adapter formatting multi-block prompts, enforcing alternating message constraints, and streaming responses from Anthropic.
- `app/client/platforms/google.ts`: GeminiProApi adapter formatting messages for Google Gemini, supporting vision inline data, tool calling, and SSE streaming.
- `app/client/platforms/alibaba.ts`: QwenApi adapter for Alibaba DashScope Qwen chat and streaming requests.
- `app/client/platforms/deepseek.ts`: DeepSeekApi adapter handling message sequencing, reasoning stream chunk parsing, and tool execution for DeepSeek models.
- `app/client/platforms/baidu.ts`: ErnieApi adapter formatting Baidu Qianfan odd-length message requirements and handling SSE streaming via fetchEventSource.
- `app/client/platforms/bytedance.ts`: DoubaoApi adapter handling ByteDance chat completions and thinking-process streaming.
- `app/client/platforms/glm.ts`: ChatGLMApi adapter for Zhipu AI models, routing requests to chat, CogView image generation, or CogVideo video generation.
- `app/client/platforms/tencent.ts`: HunyuanApi adapter converting request parameters to capitalized casing for Tencent Hunyuan models with SSE streaming.
- `app/client/platforms/iflytek.ts`: SparkApi adapter handling iFlytek Spark chat streaming with smooth text animation.
- `app/client/platforms/moonshot.ts`: MoonshotApi adapter managing chat requests and tool integration for Moonshot AI models.
- `app/client/platforms/siliconflow.ts`: SiliconflowApi adapter handling chat completions, thinking streaming, and dynamic model listing for SiliconFlow.
- `app/client/platforms/ai302.ts`: Ai302Api adapter managing chat completions, reasoning tokens, and model listing for 302.AI.
- `app/client/platforms/xai.ts`: XAIApi adapter managing chat completions and streaming for xAI Grok models.

## Public interface
- class ClientApi
- abstract class LLMApi
- ChatControllerPool
- getBearerToken(apiKey: string, noBearer?: boolean): string
- validString(x: string): boolean
- getHeaders(ignoreHeaders?: boolean): Record<string, string>
- class ChatGPTApi implements LLMApi
- class ClaudeApi implements LLMApi
- class GeminiProApi implements LLMApi
- class QwenApi implements LLMApi
- class DeepSeekApi implements LLMApi
- class ErnieApi implements LLMApi
- class DoubaoApi implements LLMApi
- class ChatGLMApi implements LLMApi
- class HunyuanApi implements LLMApi
- class SparkApi implements LLMApi
- class MoonshotApi implements LLMApi
- class SiliconflowApi implements LLMApi
- class Ai302Api implements LLMApi
- class XAIApi implements LLMApi

## Dependencies
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
- Most platform adapters throw 'Method not implemented.' for speech() and return empty arrays for models() or usage(); is text-to-speech planned for non-OpenAI providers?
- ClientApi methods config(), prompts(), and masks() in app/client/api.ts are currently empty stubs.
