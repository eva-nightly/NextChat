# Module: app/client [AI]

Provides unified client-side LLM provider abstractions, factory creation, request serialization, streaming handlers, and streaming controller lifecycle management across diverse AI platforms (OpenAI, Anthropic, Google Gemini, Alibaba, Baidu Ernie, ByteDance Doubao, DeepSeek, ChatGLM, iFlytek Spark, Moonshot, Tencent Hunyuan, SiliconFlow, XAI, and 302.AI).

## Key files
- `app/client/api.ts`: Defines the abstract LLMApi class, ClientApi provider factory, common data interfaces (ChatOptions, RequestMessage, LLMConfig), and authorization header helpers.
- `app/client/controller.ts`: Manages AbortController instances for active chat request streams via ChatControllerPool.
- `app/client/platforms/openai.ts`: ChatGPTApi implementation for OpenAI and Azure OpenAI endpoints, handling streaming, DALL-E image generation, TTS speech generation, and reasoning models.
- `app/client/platforms/anthropic.ts`: ClaudeApi implementation adapting messages, vision payloads, and tool calls to Anthropic's message APIs.
- `app/client/platforms/google.ts`: GeminiProApi implementation handling Google Gemini content formatting, safety settings, and multimodal inputs.
- `app/client/platforms/alibaba.ts`: QwenApi implementation adapting requests to Alibaba DashScope SSE protocols.
- `app/client/platforms/baidu.ts`: ErnieApi implementation formatting messages and streaming responses for Baidu BCE/Ernie endpoints.
- `app/client/platforms/bytedance.ts`: DoubaoApi implementation for ByteDance model endpoints.
- `app/client/platforms/deepseek.ts`: DeepSeekApi implementation for DeepSeek chat and reasoning streams.
- `app/client/platforms/glm.ts`: ChatGLMApi implementation supporting ChatGLM text, CogView image generation, and CogVideo video generation.
- `app/client/platforms/iflytek.ts`: SparkApi implementation handling iFlytek Spark WebSocket/SSE streaming endpoints.
- `app/client/platforms/moonshot.ts`: MoonshotApi implementation for Moonshot AI model requests.
- `app/client/platforms/siliconflow.ts`: SiliconflowApi implementation for SiliconFlow models and dynamic model listing.
- `app/client/platforms/tencent.ts`: HunyuanApi implementation for Tencent Hunyuan with payload key pascal-casing.
- `app/client/platforms/xai.ts`: XAIApi implementation for xAI model chat and streaming endpoints.
- `app/client/platforms/ai302.ts`: Ai302Api implementation supporting 302.AI API endpoints and model listings.

## Public interface
- class LLMApi
- class ClientApi
- const ChatControllerPool
- function getHeaders(ignoreHeaders?: boolean)
- function getBearerToken(apiKey: string, noBearer?: boolean)
- function validString(x: string): boolean
- class ChatGPTApi
- class ClaudeApi
- class GeminiProApi
- class ErnieApi
- class DoubaoApi
- class QwenApi
- class HunyuanApi
- class MoonshotApi
- class SparkApi
- class DeepSeekApi
- class XAIApi
- class ChatGLMApi
- class SiliconflowApi
- class Ai302Api

## Dependencies
- @fortaine/fetch-event-source
- lodash-es/isArray
- lodash-es/isObject
- lodash-es/mapKeys
- lodash-es/mapValues
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
- Most provider implementations currently leave the speech() method unimplemented and usage() returning zero stubs; are these planned for expansion or intended to be OpenAI-only?
- Direct API token exchanges and third-party API proxying differ between desktop/app mode and browser web mode—are CORS and credentials fully handled across all self-hosted and cloud proxy deployments?
