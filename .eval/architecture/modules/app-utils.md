# Module: app/utils [AI]

Provides core utilities and helper functions across the application for LLM streaming and multimodal payload handling, model configuration and provider resolution, state persistence via IndexedDB, cloud synchronization (WebDAV and Upstash Redis), audio/TTS playback, cryptographic request signing, and analytics tracking.

## Key files
- `app/utils/chat.ts`: Handles chat streaming animations, tool execution orchestration, multimodal image compression, base64 caching, and upload handling.
- `app/utils/model.ts`: Parses custom model strings, resolves provider prefixes, aggregates model tables, and verifies model availability.
- `app/utils/cloud/index.ts`: Factory for creating synchronization clients (WebDAV and Upstash) for remote configuration and chat backup.
- `app/utils/cloud/upstash.ts`: Implements chunked backup and restore syncing against Upstash Redis endpoints.
- `app/utils/cloud/webdav.ts`: Implements backup file syncing and connectivity checks against WebDAV servers.
- `app/utils/sync.ts`: Extracts non-function app state and merges remote state with local Zustand store states across chat sessions, masks, and configurations.
- `app/utils/store.ts`: Wraps Zustand store creation with automatic IndexedDB persistence, hydration tracking, and update timestamps.
- `app/utils/indexedDB-storage.ts`: Provides an IndexedDB-backed StateStorage implementation with fallback to safeLocalStorage.
- `app/utils/stream.ts`: Polyfills standard fetch streaming over Tauri IPC channels when running in a desktop environment.
- `app/utils/tencent.ts`: Constructs TC3-HMAC-SHA256 authorization headers for Tencent Hunyuan ChatCompletions API requests.
- `app/utils/ms_edge_tts.ts`: Implements WebSocket client for Microsoft Edge Read Aloud text-to-speech synthesis.
- `app/utils/audio.ts`: Provides Web Audio API playback controls for decoded ArrayBuffer speech audio.
- `app/utils/cloudflare.ts`: Rewrites API URLs to route through Cloudflare AI Gateway for Azure OpenAI, OpenAI, and Anthropic.
- `app/utils/hmac.ts`: Provides pure JavaScript SHA-256 hashing and HMAC signing without requiring Web Crypto APIs.
- `app/utils/token.ts`: Heuristically calculates token length approximations for ASCII and Unicode text.
- `app/utils/auth-settings-events.ts`: Dispatches Google Analytics conversion tracking events for payment guides and buttons.
- `app/utils/hooks.ts`: Exports React hooks like useAllModels for accessing merged model configurations.
- `app/utils/clone.ts`: Exports object cloning (deepClone) and property existence assertion (ensure).
- `app/utils/format.ts`: Formats objects as markdown JSON blocks and chunks large text buffers by byte limits.
- `app/utils/merge.ts`: Recursively deep merges properties between source and target objects.
- `app/utils/object.ts`: Provides omit and pick utility functions for object property filtering.
- `app/utils/baidu.ts`: Requests OAuth access tokens from Baidu authentication services using client credentials.

## Public interface
- createTTSPlayer(): TTSPlayer
- trackConversationGuideToCPaymentClick(): void
- trackAuthorizationPageButtonToCPaymentClick(): void
- trackAuthorizationPageBannerToCPaymentClick(): void
- trackSettingsPageGuideToCPaymentClick(): void
- getAccessToken(clientId: string, clientSecret: string): Promise<{ access_token: string; expires_in: number; error?: number }>
- compressImage(file: Blob, maxSize: number): Promise<string>
- preProcessImageContentBase(content: RequestMessage['content'], transformImageUrl: (url: string) => Promise<{ [key: string]: any }>): Promise<any>
- preProcessImageContent(content: RequestMessage['content']): Promise<MultimodalContent[] | string>
- preProcessImageContentForAlibabaDashScope(content: RequestMessage['content']): Promise<any>
- cacheImageToBase64Image(imageUrl: string): Promise<string>
- base64Image2Blob(base64Data: string, contentType: string): Blob
- uploadImage(file: Blob): Promise<string>
- removeImage(imageUrl: string): Promise<Response>
- stream(chatPath: string, requestPayload: any, headers: any, tools: any[], funcs: Record<string, Function>, controller: AbortController, parseSSE: (text: string, runTools: any[]) => string | undefined, processToolMessage: (requestPayload: any, toolCallMessage: any, toolCallResult: any[]) => void, options: any): void
- deepClone<T>(obj: T): T
- ensure<T extends object>(obj: T, keys: Array<[keyof T][number]>): boolean
- createSyncClient<T extends ProviderType>(provider: T, config: SyncClientConfig[T]): SyncClient
- createUpstashClient(store: SyncStore): UpStashClient
- createWebDavClient(store: SyncStore): WebDavClient
- cloudflareAIGatewayUrl(fetchUrl: string): string
- prettyObject(msg: any): string
- chunks(s: string, maxBytes?: number): Generator<string, void, unknown>
- sign(inputKey: string | Uint8Array, inputData: string | Uint8Array): Uint8Array
- hex(bin: Uint8Array): string
- hash(str: string): string
- hashWithSecret(str: string, secret: string): string
- useAllModels(): LLMModel[]
- indexedDBStorage: IndexedDBStorage
- merge(target: any, source: any): void
- getModelProvider(modelWithProvider: string): [string, string?]
- collectModelTable(models: readonly LLMModel[], customModels: string): Record<string, any>
- collectModelTableWithDefaultModel(models: readonly LLMModel[], customModels: string, defaultModel: string): Record<string, any>
- collectModels(models: readonly LLMModel[], customModels: string): any[]
- collectModelsWithDefaultModel(models: readonly LLMModel[], customModels: string, defaultModel: string): any[]
- isModelAvailableInServer(customModels: string, modelName: string, providerName: string): boolean
- isGPT4Model(modelName: string): boolean
- isModelNotavailableInServer(customModels: string, modelName: string, providerNames: string | string[]): boolean
- MsEdgeTTS: class
- omit<T extends object, U extends (keyof T)[]>(obj: T, ...keys: U): Omit<T, U[number]>
- pick<T extends object, U extends (keyof T)[]>(obj: T, ...keys: U): Pick<T, U[number]>
- createPersistStore<T extends object, M>(state: T, methods: (set: any, get: any) => M, persistOptions: any): UseBoundStore<StoreApi<T & M & MakeUpdater<T>>>
- fetch(url: string, options?: RequestInit): Promise<Response>
- getLocalAppState(): AppState
- setLocalAppState(appState: AppState): void
- mergeAppState(localState: AppState, remoteState: AppState): AppState
- mergeWithUpdate<T extends { lastUpdateTime?: number }>(localState: T, remoteState: T): T
- getHeader(payload: any, SECRET_ID: string, SECRET_KEY: string): Promise<Record<string, string>>
- estimateTokenLength(input: string): number

## Dependencies
- @next/third-parties/google
- @fortaine/fetch-event-source
- zustand
- zustand/middleware
- idb-keyval
- buffer
- crypto
- stream
- react
- heic2any

## AI touchpoints [AI]
- `app/utils/cloudflare.ts`
- `app/utils/model.ts`
- `app/utils/sync.ts`
- `app/utils/chat.ts`
- `app/utils/ms_edge_tts.ts`
- `app/utils/tencent.ts`
- `app/utils/token.ts`

## Open questions
- _none_
