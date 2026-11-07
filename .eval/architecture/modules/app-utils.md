# Module: app/utils [AI]

Provides core utility functions and helpers across the application, covering chat streaming and tool execution, LLM model catalog resolution, multimodal image handling, cloud data synchronization (WebDAV/Upstash), persistent state management with IndexedDB, audio/TTS processing, provider-specific request signing (Tencent, Baidu), and Tauri desktop runtime bridges.

## Key files
- `app/utils/chat.ts`: Handles multimodal image compression/caching/uploading and manages the core LLM streaming loop with tool calling, SSE parsing, and token animation.
- `app/utils/model.ts`: Parses custom model configuration strings, merges default and server models, computes model tables, and provides availability and GPT-4 checks.
- `app/utils/sync.ts`: Coordinates synchronization and merging of local and remote application states across chat sessions, masks, prompts, and settings.
- `app/utils/cloud/index.ts`: Factory and dispatcher for initializing cloud storage sync providers (Upstash Redis and WebDAV).
- `app/utils/cloud/upstash.ts`: Client for syncing application state to Upstash Redis using chunked payloads to adhere to size limits.
- `app/utils/cloud/webdav.ts`: Client for backing up and syncing application state to WebDAV servers.
- `app/utils/store.ts`: Zustand persistence wrapper configuring hydration tracking and IndexedDB storage backing.
- `app/utils/indexedDB-storage.ts`: Zustand StateStorage implementation backed by idb-keyval with fallback to localStorage.
- `app/utils/stream.ts`: HTTP fetch wrapper supporting Tauri IPC stream events for desktop builds with standard fetch fallback.
- `app/utils/tencent.ts`: Generates TC3-HMAC-SHA256 signature authentication headers for Tencent Cloud Hunyuan API requests.
- `app/utils/baidu.ts`: Fetches OAuth access tokens for Baidu LLM APIs.
- `app/utils/cloudflare.ts`: Rewrites AI gateway endpoint URLs when proxying requests through Cloudflare AI Gateway.
- `app/utils/audio.ts`: Web Audio API player for handling decoded audio buffers and TTS playback.
- `app/utils/ms_edge_tts.ts`: WebSocket client implementing speech synthesis through Microsoft Edge Read Aloud TTS service.
- `app/utils/token.ts`: Estimates token counts based on ASCII and Unicode character heuristic weighting.
- `app/utils/hmac.ts`: Pure JavaScript implementation of SHA-256 and HMAC-SHA256 for cryptographic signing without SubtleCrypto dependencies.
- `app/utils/hooks.ts`: React hook providing memoized aggregation of configured and accessible LLM models.
- `app/utils/auth-settings-events.ts`: Google Analytics event tracking triggers for conversion and payment touchpoints.
- `app/utils/clone.ts`: Utilities for deep cloning objects and validating required properties.
- `app/utils/format.ts`: Formatting utilities including JSON markdown code block formatting and byte chunk generation.
- `app/utils/merge.ts`: Recursive object property merger.
- `app/utils/object.ts`: TypeScript-typed pick and omit helpers for object keys.

## Public interface
- stream(chatPath, requestPayload, headers, tools, funcs, controller, parseSSE, processToolMessage, options)
- compressImage(file, maxSize): Promise<string>
- preProcessImageContent(content): Promise<MultimodalContent[] | string>
- preProcessImageContentForAlibabaDashScope(content)
- cacheImageToBase64Image(imageUrl): Promise<string>
- uploadImage(file): Promise<string>
- removeImage(imageUrl)
- collectModels(models, customModels): LLMModel[]
- collectModelsWithDefaultModel(models, customModels, defaultModel): LLMModel[]
- collectModelTable(models, customModels)
- collectModelTableWithDefaultModel(models, customModels, defaultModel)
- getModelProvider(modelWithProvider): [string, string?]
- isModelAvailableInServer(customModels, modelName, providerName): boolean
- isModelNotavailableInServer(customModels, modelName, providerNames): boolean
- isGPT4Model(modelName): boolean
- useAllModels(): LLMModel[]
- createSyncClient(provider, config): SyncClient
- createUpstashClient(store): UpStashClient
- createWebDavClient(store): WebDavClient
- getLocalAppState(): AppState
- setLocalAppState(appState)
- mergeAppState(localState, remoteState): AppState
- mergeWithUpdate(localState, remoteState)
- createPersistStore(state, methods, persistOptions)
- indexedDBStorage: IndexedDBStorage
- fetch(url, options): Promise<Response>
- cloudflareAIGatewayUrl(fetchUrl): string
- getHeader(payload, SECRET_ID, SECRET_KEY): Promise<Record<string, string>>
- getAccessToken(clientId, clientSecret): Promise<{ access_token: string, expires_in: number, error?: number }>
- createTTSPlayer(): TTSPlayer
- MsEdgeTTS
- estimateTokenLength(input): number
- hash(str): string
- hashWithSecret(str, secret): string
- sign(inputKey, inputData)
- deepClone(obj)
- ensure(obj, keys)
- prettyObject(msg): string
- chunks(s, maxBytes)
- merge(target, source)
- omit(obj, ...keys)
- pick(obj, ...keys)
- trackConversationGuideToCPaymentClick()
- trackAuthorizationPageButtonToCPaymentClick()
- trackAuthorizationPageBannerToCPaymentClick()
- trackSettingsPageGuideToCPaymentClick()

## Dependencies
- @fortaine/fetch-event-source
- @next/third-parties/google
- idb-keyval
- zustand
- zustand/middleware
- react
- heic2any

## AI touchpoints [AI]
- `app/utils/cloudflare.ts`
- `app/utils/model.ts`
- `app/utils/sync.ts`
- `app/utils/chat.ts`
- `app/utils/tencent.ts`
- `app/utils/baidu.ts`
- `app/utils/token.ts`
- `app/utils/ms_edge_tts.ts`

## Open questions
- _none_
