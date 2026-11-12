# Module: app/client [AI]

Provides a unified client-side LLM provider abstraction, request formatting, streaming handler integration, and message lifecycle controller across OpenAI, Anthropic, Google, DeepSeek, and various other AI platforms.

## Key files
- `app/client/api.ts`: Defines core LLM interfaces (LLMApi, ChatOptions, RequestMessage), helper functions (getHeaders, getBearerToken), and the ClientApi factory routing requests to provider-specific implementations.
- `app/client/controller.ts`: Manages AbortController instances for active chat streaming requests in ChatControllerPool.
- `app/client/platforms/openai.ts`: Implements ChatGPTApi for OpenAI and Azure models, handling text chat, reasoning models (o1/o3/gpt-5), DALL-E image generation, and TTS speech.
- `app/client/platforms/anthropic.ts`: Implements ClaudeApi for Anthropic models, managing role alternation, multimodal content, and tool calls.
- `app/client/platforms/google.ts`: Implements GeminiProApi for Google Gemini models, formatting multipart vision data, safety settings, and function calling.
- `app/client/platforms/deepseek.ts`: Implements DeepSeekApi handling chat completions, thinking/reasoning deltas, and tool executions.
- `app/client/platforms/alibaba.ts`: Implements QwenApi for Alibaba DashScope models with multimodal and tool-use capabilities.
- `app/client/platforms/baidu.ts`: Implements ErnieApi for Baidu Qianfan models over Server-Sent Events (SSE) with smooth animated streaming.
- `app/client/platforms/tencent.ts`: Implements HunyuanApi for Tencent models, converting payloads and consuming SSE streams.
- `app/client/platforms/glm.ts`: Implements ChatGLMApi supporting chat, CogView image generation, and CogVideo video generation.
- `app/client/platforms/bytedance.ts`: Implements DoubaoApi for ByteDance LLM chat endpoints.
- `app/client/platforms/iflytek.ts`: Implements SparkApi for iFlytek models with animated SSE stream parsing.
- `app/client/platforms/moonshot.ts`: Implements MoonshotApi for Moonshot Kimi chat completions.
- `app/client/platforms/siliconflow.ts`: Implements SiliconflowApi for SiliconFlow model chat completions and dynamic model listing.
- `app/client/platforms/xai.ts`: Implements XAIApi for xAI Grok chat completions.
- `app/client/platforms/ai302.ts`: Implements Ai302Api for 302.AI proxy models and dynamic model listing.

## Public interface
- export class ClientApi
- export abstract class LLMApi
- export class ChatGPTApi implements LLMApi
- export class ClaudeApi implements LLMApi
- export class GeminiProApi implements LLMApi
- export class ErnieApi implements LLMApi
- export class DoubaoApi implements LLMApi
- export class QwenApi implements LLMApi
- export class HunyuanApi implements LLMApi
- export class MoonshotApi implements LLMApi
- export class SparkApi implements LLMApi
- export class DeepSeekApi implements LLMApi
- export class XAIApi implements LLMApi
- export class ChatGLMApi implements LLMApi
- export class SiliconflowApi implements LLMApi
- export class Ai302Api implements LLMApi
- export const ChatControllerPool
- export function getHeaders(ignoreHeaders?: boolean): Record<string, string>
- export function getBearerToken(apiKey: string, noBearer?: boolean): string
- export function validString(x: string): boolean
- export interface ChatOptions
- export interface SpeechOptions
- export interface LLMConfig
- export interface RequestMessage
- export interface LLMModel
- export interface LLMUsage

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
- _none_
