# Module: app/utils [AI]

Provides core utilities for the application, including chat response streaming, multimodal payload preprocessing, model configuration and sorting, cloud synchronization (WebDAV and Upstash), persistence storage adapters (IndexedDB with Zustand), cryptographic signing for cloud providers, and audio/TTS playback.

## Key files
- `app/utils/chat.ts`: Handles chat response streaming animation, tool call resolution, image compression, and multimodal content preprocessing
- `app/utils/model.ts`: Parses, sorts, validates, and manages model tables and custom provider mappings
- `app/utils/store.ts`: Creates persistent Zustand stores backed by IndexedDB storage
- `app/utils/sync.ts`: Extracts, applies, and merges application state across chat sessions, masks, prompts, and settings for remote syncing
- `app/utils/stream.ts`: Provides a custom fetch wrapper that supports Tauri native streaming bridge when running in desktop mode
- `app/utils/cloud/index.ts`: Factory for creating cloud synchronization clients for Upstash and WebDAV
- `app/utils/tencent.ts`: Constructs TC3-HMAC-SHA256 authentication headers for Tencent Hunyuan chat completions

## Public interface
- createTTSPlayer
- trackConversationGuideToCPaymentClick
- trackAuthorizationPageButtonToCPaymentClick
- trackAuthorizationPageBannerToCPaymentClick
- trackSettingsPageGuideToCPaymentClick
- getAccessToken
- compressImage
- preProcessImageContentBase
- preProcessImageContent
- preProcessImageContentForAlibabaDashScope
- cacheImageToBase64Image
- base64Image2Blob
- uploadImage
- removeImage
- stream
- deepClone
- ensure
- ProviderType
- SyncClients
- createSyncClient
- createUpstashClient
- createWebDavClient
- cloudflareAIGatewayUrl
- prettyObject
- chunks
- sign
- hex
- hash
- hashWithSecret
- useAllModels
- indexedDBStorage
- merge
- getModelProvider
- collectModelTable
- collectModelTableWithDefaultModel
- collectModels
- collectModelsWithDefaultModel
- isModelAvailableInServer
- isGPT4Model
- isModelNotavailableInServer
- MsEdgeTTS
- ProsodyOptions
- VOLUME
- RATE
- PITCH
- OUTPUT_FORMAT
- omit
- pick
- createPersistStore
- fetch
- getNonFunctionFileds
- getLocalAppState
- setLocalAppState
- mergeAppState
- mergeWithUpdate
- getHeader
- estimateTokenLength

## Dependencies
- @next/third-parties/google
- @fortaine/fetch-event-source
- idb-keyval
- zustand
- zustand/middleware
- react
- buffer
- crypto
- stream

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
- In app/utils/sync.ts, mergeWithUpdate assigns `const remoteUpdateTime = localState.lastUpdateTime ?? 1;` referencing `localState` instead of `remoteState.lastUpdateTime`.
